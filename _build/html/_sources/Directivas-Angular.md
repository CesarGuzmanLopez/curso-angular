# Tutorial: Creación y Uso de Directivas en Angular

## Introducción

En Angular, las directivas son una de las características más poderosas y flexibles. Las directivas son clases que pueden modificar el DOM y alterar el comportamiento de los elementos HTML. Existen tres tipos principales de directivas en Angular:

- **Directivas de atributo:** Cambian el comportamiento o el aspecto de un elemento, componente o cualquier otra directiva.
- **Directivas estructurales:** Alteran el DOM añadiendo o eliminando elementos.
- **Componentes:** Son directivas con una plantilla asociada.
- **Directivas personalizadas:** Son directivas creadas por el usuario.
  En este tutorial, nos enfocaremos en las directivas de atributo y estructurales.

## Prerrequisitos

Asegúrate de tener instalado lo siguiente:

- Angular CLI (Command Line Interface)

## Crear un Proyecto Angular

Si aún no tienes un proyecto Angular, crea uno con el siguiente comando:

```sh
ng new mi-proyecto
```

Navega al directorio del proyecto:

```sh
cd mi-proyecto
```

## Directivas Angular 17

### directiva @if

```HTML
<div>
  <button (click)="toggleTable()">Mostrar/Ocultar Tabla</button>
</div>

@if (showTable) {
<table>
  <tr>
    <th>Nombre</th>
    <th>Edad</th>
  </tr>
  @for ( person of people; track person.id) {
  <tr>
    <td>{{ person.nombre }}</td>
    <td>{{ person.edad }}</td>
  </tr>
  }
</table>
} @else {
<ul>
  @for ( person of people; track person.id) {
  <li>{{ person.nombre }} ({{ person.edad }} años)</li>
  }
</ul>
}

<div>
  <h3>Agregar nueva persona</h3>
  <label>
    Nombre:
    <input [(ngModel)]="newPerson.nombre" placeholder="Nombre" />
  </label>
  <label>
    Edad:
    <input [(ngModel)]="newPerson.edad" type="number" placeholder="Edad" />
  </label>
  <button (click)="addPerson()">Agregar</button>
</div>

```

en ts deveria ser algo asi

```ts
@Component({
  selector: "app-root",
  standalone: true,
  imports: [RouterOutlet, ReactiveFormsModule, FormsModule],
  templateUrl: "./app.component.html",
  styleUrl: "./app.component.css",
})
export class AppComponent {
  showTable = true;
  people = [
    { id: 1, nombre: "John", edad: 25 },
    { id: 2, nombre: "Mike", edad: 30 },
  ];
  newPerson = { nombre: "", edad: 0 };

  addPerson() {
    if (this.newPerson.nombre && this.newPerson.edad !== null) {
      const newId =
        this.people.length > 0
          ? Math.max(...this.people.map((p) => p.id)) + 1
          : 1;
      this.people.push({ id: newId, ...this.newPerson });
      this.newPerson = { nombre: "", edad: 0 };
    }
  }

  toggleTable() {
    this.showTable = !this.showTable;
  }
}
```

ejemplo de switch

```html
@switch (color) { @case ('red') {
<app-red-color />
} @case ('blue') {
<app-blue-color />
} @default {
<app-default-color />
} }
```
