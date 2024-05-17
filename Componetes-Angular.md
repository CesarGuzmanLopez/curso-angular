# Tutorial: Creación de un Componente Standalone en Angular

## Introducción

Un componente en Angular es una clase que define una vista y la lógica de la interfaz de usuario. En este tutorial, aprenderás a crear un componente standalone en Angular, es decir, un componente que no depende de un módulo.

## Prerrequisitos

Asegúrate de tener instalado lo siguiente:

- Angular CLI (Command Line Interface)

## Crear un Componente Standalone

Angular CLI facilita la creación de componentes standalone. Para crear un nuevo componente, usa el siguiente comando:

```sh
ng generate component nombre-del-componente --standalone
```

Este comando generará cuatro archivos:

    mi-componente.component.ts (lógica del componente)
    mi-componente.component.html (vista del componente)
    mi-componente.component.css (estilos del componente)
    mi-componente.component.spec.ts (pruebas del componente)

Estructura de un Componente Standalone
Archivo TypeScript (mi-componente.component.ts)

Ejecutar la Aplicación

Finalmente, para ver tu componente en acción, ejecuta la aplicación Angular con el siguiente comando:
