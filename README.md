#  Actividad 5

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap_5-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white)

##  Integrantes del Equipo
*  **Gonzalez Valentin Adrian** 
*  **Martinez Miguel Leonardo Daniel**
*  **Grupo 7SC** 

---

##  Descripción Breve
Este proyecto es un sistema web simulado para la gestión escolar. Cuenta con una interfaz de inicio de sesión segura, validación estricta de contraseñas en tiempo real y un panel principal (Dashboard). Destaca por su diseño responsivo, la implementación de un menú lateral (sidebar) y modales personalizados desarrollados desde cero con una estética inspirada en terminales de consola.

---

##  Explicación y Documentación

### Framework CSS
La estructura principal del proyecto está construida sobre **Bootstrap 5.3.0** (implementado vía CDN). Esto nos permitió:
* Utilizar el sistema de grillas para la responsividad.
* Implementar componentes nativos como el *Offcanvas* (Sidebar) y formularios flotantes.

**CSS Personalizado:** Adicionalmente, creamos el archivo `componente.css` con **CSS Puro**. Aquí utilizamos variables de entorno (`:root`) para diseñar un sistema de **modales reutilizables** con un tema oscuro (estilo consola), sombras suaves y animaciones de entrada/salida para no depender al 100% de los modales de Bootstrap.

###  Flujo del Login
1. El usuario accede a `login.html`.
2. Al escribir su contraseña, el sistema evalúa en tiempo real 5 requisitos de seguridad (mayúsculas, minúsculas, números, caracteres especiales y longitud).
3. Al presionar "Acceder", el evento `submit` es interceptado.
4. Si las credenciales son válidas, se simula el inicio de sesión y se redirige a `index.html`.

###  Paso de Usuario (Login ➔ Navbar)
Para mantener la persistencia de los datos en el frontend, utilizamos el **Web Storage API**:
* Al hacer login exitoso, el correo/nombre del usuario se guarda utilizando `localStorage.setItem('usuario', correo)`.
* Al cargar el Dashboard (`index.html`), un script lee este dato con `localStorage.getItem('usuario')` y lo inyecta dinámicamente en el DOM, actualizando el texto del Navbar.

###  Métodos Principales Utilizados

| Método / Herramienta | Función en el Proyecto |
| :--- | :--- |
| `document.getElementById()` | Captura de inputs, botones y validadores en el DOM. |
| `addEventListener()` | Escucha de eventos `submit` en formularios y `input` para validación en tiempo real. |
| `localStorage` | Persistencia de sesión simulada entre páginas HTML. |
| **Expresiones Regulares (Regex)** | Validación estricta de la contraseña y aseguramiento de que el **Número de Control** tenga exactamente 6 dígitos. |
| `classList.toggle() / add()` | Manipulación de clases para mostrar/ocultar modales y cambiar el color de los *badges* de contraseña. |

---

##  Proceso de Creación (Paso a Paso)

1. **Estructura del Login:** Iniciamos maquetando `login.html`. Usamos las *cards* de Bootstrap y agregamos los *badges* debajo del input de contraseña. En JavaScript, vinculamos cada badge a una validación Regex para que se iluminaran en verde al cumplirse.
   
2. **Dashboard y Navbar:** Creamos `index.html`. Implementamos un `navbar` superior y programamos la lógica para que el botón de perfil muestre el nombre del usuario logueado rescatado del `localStorage`.

3. **Menú Lateral (Sidebar):** Integramos el componente `Offcanvas` de Bootstrap. Lo conectamos a un botón de "Hamburguesa" en el Navbar para que se despliegue lateralmente, conteniendo las opciones del sistema como "Captura de Usuarios".

4. **Formulario y Número de Control:** Diseñamos el formulario de captura. Para el campo "Número de Control", implementamos lógica en JS que bloquea letras y valida que la longitud sea estrictamente de 6 dígitos numéricos antes de permitir el guardado.

5. **El Modal Estilo Consola:** Para las alertas (éxito, error), evitamos los `alert()` nativos. Maquetamos un modal flotante oscuro usando `position: fixed` y `z-index`. En JS, creamos una función que recibe el título y el mensaje, y muestra este modal de forma dinámica.

---

##  Capturas de Pantalla del Flujo Funcional

### 1. Pantalla de Login y Validación en tiempo real
> Muestra el formulario y el cómo de la contraseña cambian de color su caudro de texto.
<img width="1916" height="867" alt="image" src="https://github.com/user-attachments/assets/094d5b90-e233-46d5-ab3e-269b6f72f691" />

<img width="1918" height="862" alt="image" src="https://github.com/user-attachments/assets/6e54504a-86e4-450a-9322-00d2d5f30802" />

<img width="1918" height="876" alt="image" src="https://github.com/user-attachments/assets/16b4b9e8-79a3-433c-b7f2-37218dbbe1d8" />

### 2. Dashboard: Navbar y Sidebar desplegado
> Muestra el menú lateral activo y el nombre del usuario dinámico en la parte superior derecha.
<img width="1918" height="865" alt="image" src="https://github.com/user-attachments/assets/06e71d39-56f0-4c0f-814a-6369fc5d89fc" />


### 3. Captura de Alumnos: Validación de Número de Control
> Evidencia de la validación de 6 dígitos en el formulario.
<img width="1918" height="867" alt="image" src="https://github.com/user-attachments/assets/950ae527-7149-4564-ada5-828a9995bf88" />

<img width="1918" height="863" alt="image" src="https://github.com/user-attachments/assets/23b52dea-def2-47bd-9ece-6731776efee4" />

### 4. Modal Reutilizable (Estética de Consola)
> Demostración de nuestro modal personalizado CSS.
 <img width="1917" height="871" alt="image" src="https://github.com/user-attachments/assets/1abbf696-218c-4955-95b7-4c3dac084409" />

---
*
