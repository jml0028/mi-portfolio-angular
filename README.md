Mi Portfolio Angular
Este proyecto es la migración de un portfolio estático a una aplicación Angular. El objetivo fue transformar una estructura HTML, CSS y JavaScript tradicional a una arquitectura modular y escalable usando Angular, manteniendo el mismo contenido y funcionalidad.

Contenido del Proyecto
El portfolio cuenta con las siguientes secciones:

Inicio: Página principal con una bienvenida y descripción.
Sobre Mí: Información personal, habilidades y programas utilizados.
Proyectos: Galería de proyectos con descripciones.
Contacto: Formulario para enviar mensajes.
Además, se creó un header compartido con navegación mediante Angular Router.

Pasos Realizados
Creación del Proyecto Angular:

Se generó un nuevo proyecto con el siguiente comando:

ng new mi-portfolio --standalone false
Se eligieron las configuraciones por defecto y se ingresó al directorio del proyecto:

cd mi-portfolio
Generación de Componentes:

Se crearon los componentes necesarios para la estructura de la aplicación:

ng generate component header
ng generate component home
ng generate component about
ng generate component projects
ng generate component contact
Configuración del Enrutado (Routing):

Se creó el archivo src/app/app-routing.module.ts con las rutas correspondientes a cada componente.
Se importó este módulo en src/app/app.module.ts para habilitar el enrutado.
Integración del Contenido:

Se migró el contenido de los archivos HTML originales a los templates de los componentes:

Home (Inicio): Contenido basado en el archivo index.html.
About (Sobre Mí): Contenido basado en el archivo aboutme.html.
Projects (Proyectos): Contenido basado en el archivo projects.html.
Contact (Contacto): Contenido basado en el archivo contact.html.
Se actualizaron las rutas de imágenes para que apunten a src/assets/images.

Aplicación de Estilos Globales:

Se trasladó el contenido de style.css al archivo src/styles.css para mantener los estilos globales.

Inclusión de Librerías Externas:

Se incluyó Bootstrap (y scripts opcionales como jQuery y Popper) en el archivo src/index.html para mantener la apariencia original del portfolio.

Integración de Funcionalidad Adicional (app.js):

El código JavaScript que controla efectos de scroll (contenido en app.js) se puede integrar de dos formas:

Como script externo, copiándolo a src/assets/js/app.js y enlazándolo en index.html.
O migrándolo a un servicio o componente Angular (usando, por ejemplo, el hook ngAfterViewInit).
Estructura del Proyecto
La estructura relevante del proyecto es la siguiente:

mi-portfolio/
├── src/
│   ├── app/
│   │   ├── app.component.html         // Incluye <app-header> y <router-outlet>
│   │   ├── app.module.ts              // Declara los componentes y el routing
│   │   ├── app-routing.module.ts      // Configuración de rutas
│   │   ├── header/
│   │   │   └── header.component.html  // Menú de navegación con routerLink
│   │   ├── home/
│   │   │   └── home.component.html    // Página de inicio (basada en index.html)
│   │   ├── about/
│   │   │   └── about.component.html   // Página "Sobre Mí" (basada en aboutme.html)
│   │   ├── projects/
│   │   │   └── projects.component.html // Página de proyectos (basada en projects.html)
│   │   └── contact/
│   │       └── contact.component.html  // Página de contacto (basada en contact.html)
│   ├── assets/
│   │   ├── images/                    // Imágenes utilizadas en el portfolio
│   │   └── js/
│   │       └── app.js (opcional)      // Código JavaScript para efectos (opcional)
│   ├── index.html                     // Incluye Bootstrap y enlaces a styles.css y scripts
│   └── styles.css                     // Estilos globales (contenido original de style.css)
├── package.json
└── ...
Cómo Ejecutar la Aplicación
Instalar Dependencias:
npm install

Ejecutar en Modo Desarrollo:
ng serve
Abre tu navegador en http://localhost:4200.

Consideraciones Adicionales
Imágenes: Asegúrate de colocar todas las imágenes en la carpeta src/assets/images.
Código JavaScript: Si decides integrar el código de app.js directamente en Angular, adapta la lógica a los ciclos de vida de los componentes para evitar manipulaciones directas del DOM.
Librerías Externas: El uso de Bootstrap, jQuery y Popper se mantiene para preservar el diseño original, pero considera alternativas más integradas a Angular (como Angular Material) en futuros proyectos.
Conclusión
Esta migración a Angular permite aprovechar una arquitectura modular y escalable, mejorando el mantenimiento y la evolución del proyecto sin perder la estética y funcionalidad original del portfolio.

