---
jupytext: 
  title: este es un titulo 
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Introducción a Angular 🅰️

Cesar Gerardo Guzman Lopez

Primero que nada configurar tu entorno de desarrollo para conocer el mundo de Angular. 🚀

## Instalación del Ambiente (Node npm) 🛠️

### Linux 🐧

¡Vamos a empezar! Para instalar Angular en Linux, primero necesitamos Node.js y npm. Puedes instalarlos usando tu gestor de paquetes favorito. Por ejemplo, en Debian, Ubuntu y similares:

```BASH
sudo apt update
sudo apt install nodejs npm
```

o fedora, Centos 8, y similares:

```BASH
sudo dnf update
sudo dnf install nodejs -y
```

### Windows 🖥️

Para instalar Angular en Windows, también necesitas Node.js y npm. Puedes descargar e instalar Node.js desde su sitio web oficial: [Node.js](https://nodejs.org/).

Después de instalar Node.js, abre una ventana de terminal (powershell) y comprobar su instalacion con

```BASH
npm --version
```

## Instalación de typescript y angular 📦

Luego, puedes instalar typescript y Angular CLI (Command Line Interface) globalmente usando npm:

en linux

```BASH
sudo npm install -g @angular/cli
sudo npm install -g typescript
```

o Windows

```BASH
npm install -g @angular/cli
npm install -g typescript

```

## Ambientes de Desarrollo de Angular: Elige tu Propia Aventura 🚀

Comienza con la elección de tu herramienta de desarrollo para Angular.

### 1. **VSCode(Recomendado): La Elección de las personas Cotidianas** 💻

Si eres un héroe cotidiano buscando una herramienta confiable y versátil, Visual Studio Code (VSCode) es tu mejor opecion, Simplemente instálalo, agrega los plugings y ¡listo!

**Pasos de Instalación:**

- Descarga VSCode [aquí](https://code.visualstudio.com/).
- Crea un projecto de angular
- instala los plugins recomendados
- ¡Abre el editor y estarás listo para empezar tu aventura Angular!

### 2. **WebStorm: La Elección de los amantes de InteliJ IDEA** 🌊

Para aquellos que prefieren adentrarse en las profundidades del código con un compañero de confianza, WebStorm es tu brújula en este vasto mar digital.

**Pasos de Instalación:**

- Descarga WebStorm [aquí](https://www.jetbrains.com/webstorm/download/).
- Sigue las instrucciones de instalación.

### 3. **Angular IDE: La Elección de Eclipse** 🌟

Para aquellos que encuentran su paz en la familiaridad de Eclipse, Angular IDE es como una suave brisa que te guiará a través de las complejidades del desarrollo Angular.

**Pasos de Instalación:**

- Descarga Angular IDE [aquí](https://www.genuitec.com/products/angular-ide/download/).
- Sigue las instrucciones de instalación y prepárate para sumergirte en el mundo de Angular dentro de Eclipse.

### 4. **Neovim: Para los Valientes Exploradores de la Terminal** ⚔️

Para aquellos que desean emprender una aventura más desafiante, Neovim es como una montaña que espera ser escalada, ofreciendo grandes recompensas a aquellos que se atrevan a dominarlo.

**Pasos de Instalación:**

- Instala Neovim en tu sistema. Puedes encontrar instrucciones específicas para tu sistema [aquí](https://github.com/neovim/neovim/wiki/Installing-Neovim).
- Prepárate para sumergirte en el mundo de Angular con Neovim como tu compañero de batalla.

### 5. **Bloc de Notas: Sin Conexión a Internet** 📝

Para aquellos que se encuentran en tierras desconocidas sin conexión a internet, el humilde Bloc de Notas es tu salvador en este mundo digitalizado.

**Pasos de Instalación:**

- ¡Abre el Bloc de Notas en tu sistema operativo!
- ¡Empieza a escribir tu código Angular con valentía y determinación!
  **Desventaja**
  No te auto completara codigo y dependiendo del editor tampoco te remarcara la sintaxis

## TypeScript, SCSS y Angular

### TypeScript 💻

**TypeScript** es un lenguaje de programación de código abierto desarrollado y mantenido por Microsoft. Es un superset de JavaScript que agrega características de tipado estático y otras características modernas al lenguaje. TypeScript se compila a JavaScript estándar y puede ser utilizado en lugar de JavaScript en el desarrollo de aplicaciones web y de otro tipo. Sus características principales incluyen:

- **Tipado Estático:** TypeScript permite la definición de tipos estáticos para variables, parámetros de función, propiedades de objetos, etc., lo que ayuda a atrapar errores en tiempo de compilación y mejorar la calidad del código. 🛠️
- **Características Modernas:** TypeScript incluye muchas características modernas de JavaScript, como soporte para clases, módulos, funciones de flecha, desestructuración, entre otros. 🔥

- **Compatibilidad con ECMAScript:** TypeScript es compatible con las especificaciones ECMAScript y puede compilar código que cumpla con versiones específicas de ECMAScript, lo que permite el uso de las últimas características de JavaScript mientras se mantiene la compatibilidad con navegadores y entornos más antiguos. 🚀

### SCSS (Sass) 🎨

**SCSS** (Sassy CSS) es una extensión del lenguaje CSS que añade características como variables, anidamiento, mixins, funciones, entre otros. SCSS es un preprocesador de CSS que se compila a CSS estándar antes de ser interpretado por el navegador. Sus características principales incluyen:

- **Variables:** SCSS permite definir variables que pueden ser reutilizadas en todo el archivo CSS, lo que facilita la gestión de estilos y la mantenibilidad del código. 🎈

- **Anidamiento:** SCSS permite anidar selectores CSS dentro de otros selectores, lo que ayuda a organizar el código de manera más legible y a evitar la repetición de código. 🌳

- **Mixins:** Los mixins permiten definir bloques de estilos reutilizables que pueden ser incluidos en múltiples selectores, lo que promueve la reutilización de código y la consistencia en el diseño. 🌀

- **Funciones:** SCSS permite definir funciones que pueden realizar cálculos, manipulaciones de cadenas y otras operaciones dentro de los estilos CSS, lo que proporciona mayor flexibilidad y capacidad de abstracción en la definición de estilos. 🛠️

### ¿Qué es Angular? 🅰️

Angular es un framework de desarrollo de aplicaciones web de código abierto y basado en TypeScript. Es mantenido por Google y una comunidad activa de desarrolladores. Angular se utiliza para construir aplicaciones web dinámicas y de una sola página (SPA) de manera eficiente y escalable.

### Características Principales:

1. **Arquitectura MVC:** Angular sigue el patrón de diseño Modelo-Vista-Controlador (MVC), lo que significa que separa la lógica de negocio, la presentación y la interacción del usuario en diferentes componentes.

2. **Componentes:** Angular utiliza una estructura de componentes para construir interfaces de usuario reutilizables y modulares. Los componentes encapsulan la lógica y la presentación de una parte específica de la aplicación.

3. **Enlace de Datos Bidireccional:** Angular ofrece enlace de datos bidireccional, lo que significa que los cambios en el modelo de datos se reflejan automáticamente en la vista y viceversa, sin necesidad de manipulación manual del DOM.

4. **Inyección de Dependencias:** Angular tiene un sistema de inyección de dependencias incorporado que facilita la gestión de dependencias entre los distintos componentes de la aplicación.

5. **Rutas y Navegación:** Angular proporciona un enrutador incorporado que permite la navegación entre diferentes vistas y la gestión de la historia del navegador de forma sencilla.

6. **Directivas:** Angular permite la creación de directivas personalizadas que extienden el comportamiento del HTML, lo que facilita la manipulación del DOM y la creación de componentes reutilizables.

7. **Herramientas Integradas:** Angular cuenta con un conjunto completo de herramientas integradas, como Angular CLI (Interface de Línea de Comandos), que facilita la creación, desarrollo, prueba y despliegue de aplicaciones Angular.

Se explorarán conceptos introductorios de Angular, un framework de desarrollo de aplicaciones web desarrollado por Google.
