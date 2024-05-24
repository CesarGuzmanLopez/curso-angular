# Tutorial: Creacion de servidor node

## Introducción

configurar tu proyecto Node.js con Express, Multer y UUID, suponiendo que ya tienes Node.js y Angular instalados en tu computadora.

```bash
    mkdir contact-api
    cd contact-api
```

Despues

```bash
mkdir contact-api
cd contact-api
```

posteriormente instalamos las depenedencias

```bash
npm install express multer uuid
#creamos los directorios necesarios
mkdir photos
echo '[]' > contacts.json
```

```typescript
const express = require("express");
const fs = require("fs");
const multer = require("multer");
const { v4: uuidv4 } = require("uuid");
const app = express();
const port = 3000;

app.use(express.json());

// Configurar almacenamiento de multer
const storage = multer.diskStorage({
  destination: function (req, file, cb) {
    cb(null, "photos/");
  },
  filename: function (req, file, cb) {
    cb(null, file.originalname);
  },
});
const upload = multer({ storage: storage });

const file = "contacts.json";

// Función para cargar los contactos desde el archivo JSON
function loadContacts() {
  if (fs.existsSync(file)) {
    const data = fs.readFileSync(file);
    return JSON.parse(data);
  }
  return [];
}

// Función para guardar los contactos en el archivo JSON
function saveContacts(contacts) {
  fs.writeFileSync(file, JSON.stringify(contacts, null, 2));
}

// Obtener todos los contactos o uno específico si se proporciona ?id=X
app.get("/contacts", (req, res) => {
  const contacts = loadContacts();
  const contactId = req.query.id;

  if (contactId) {
    const contact = contacts.find((c) => c.id === contactId);
    if (contact) {
      res.json(contact);
    } else {
      res.status(404).json({ error: "Contacto no encontrado" });
    }
  } else {
    res.json(contacts);
  }
});

// Añadir un nuevo contacto
app.post("/contacts", (req, res) => {
  const contacts = loadContacts();
  const newContact = { ...req.body, id: uuidv4() };
  contacts.push(newContact);
  saveContacts(contacts);
  res.json({ message: "Contacto agregado con éxito" });
});

// Subir una foto de contacto
app.post("/contacts/photo", upload.single("photo"), (req, res) => {
  const contactId = req.body.id;
  const contacts = loadContacts();
  const contact = contacts.find((c) => c.id === contactId);

  if (contact) {
    contact.photo = req.file.path;
    saveContacts(contacts);
    res.json({ message: "Foto subida con éxito" });
  } else {
    res.status(404).json({ error: "Contacto no encontrado" });
  }
});

// Actualizar un contacto existente
app.put("/contacts", (req, res) => {
  const contacts = loadContacts();
  const updatedContact = req.body;
  const index = contacts.findIndex((c) => c.id === updatedContact.id);

  if (index !== -1) {
    contacts[index] = { ...contacts[index], ...updatedContact };
    saveContacts(contacts);
    res.json({ message: "Contacto actualizado con éxito" });
  } else {
    res.status(404).json({ error: "Contacto no encontrado" });
  }
});

// Modificar la foto de contacto
app.put("/contacts/photo", upload.single("photo"), (req, res) => {
  const contactId = req.body.id;
  const contacts = loadContacts();
  const contact = contacts.find((c) => c.id === contactId);

  if (contact) {
    contact.photo = req.file.path;
    saveContacts(contacts);
    res.json({ message: "Foto modificada con éxito" });
  } else {
    res.status(404).json({ error: "Contacto no encontrado" });
  }
});

// Eliminar un contacto existente
app.delete("/contacts", (req, res) => {
  const contactId = req.body.id;
  let contacts = loadContacts();
  const initialLength = contacts.length;
  contacts = contacts.filter((c) => c.id !== contactId);

  if (contacts.length < initialLength) {
    saveContacts(contacts);
    res.json({ message: "Contacto eliminado con éxito" });
  } else {
    res.status(404).json({ error: "Contacto no encontrado" });
  }
});

app.listen(port, () => {
  console.log(`Servidor escuchando en http://localhost:${port}`);
});
```

despues lo ejecutamos

```bash
node server.js

```
