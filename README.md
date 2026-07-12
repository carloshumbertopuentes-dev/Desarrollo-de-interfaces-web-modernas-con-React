¡Bienvenido al repositorio del proyecto **Colegio San Marcos**! Esta plataforma es una solución informática diseñada para la gestión escolar y el control de alumnos. El proyecto está estructurado con una arquitectura desacoplada, contando con un **Backend (API REST)** y un **Frontend** para la interfaz de usuario.

---

## 📝 Descripción del Proyecto

La plataforma del **Colegio San Marcos** permite la administración ágil de la información escolar. Cuenta con un sistema de autenticación seguro y módulos específicos para el control de alumnos.

*   **Backend (API):** Construido con **Node.js** y **Express (v5)**, utilizando **Prisma ORM** para interactuar con una base de datos **PostgreSQL**. Implementa seguridad mediante tokens **JWT** y encriptación de contraseñas con **bcryptjs**.
*   **Frontend:** Interfaz de usuario moderna construida con **Vite** y **HTML5** (preconfigurada con herramientas de optimización como **Rolldown** y **Oxlint** para asegurar la calidad del código).

---

## 📋 Requisitos Previos

Antes de proceder con la instalación, asegúrate de tener instalado en tu entorno local:

1.  **Node.js** (Versión LTS 20.x o 22.x recomendada).
2.  **PostgreSQL** (Instancia local o en la nube para el funcionamiento del Backend).
3.  **Git** (Para la clonación y control de versiones).

---

## 🚀 Instrucciones de Instalación

El proyecto se divide en dos secciones principales. Sigue los pasos a continuación para configurar cada una de ellas:

### ⚙️ 1. Configuración del Backend (API)

1. Navega al directorio del backend (donde se encuentra el archivo `index.js`).
2. Instala las dependencias necesarias:
   ```bash
   npm install
3.	Configura el entorno y las migraciones de la base de datos (ver sección Variables de Entorno).
4.	Ejecuta las migraciones de Prisma para crear las tablas en PostgreSQL:
Bash
npx prisma migrate dev
5.	Inicia el servidor en modo desarrollo:
Bash
npm run dev
El servidor backend correrá por defecto en: http://localhost:3000
💻 2. Configuración del Frontend
1.	Navega al directorio colegio_san_marcos_frontend.
2.	Instala todas las dependencias del cliente:
Bash
npm install
3.	Inicia el servidor de desarrollo de Vite:
Bash
npm run dev
La aplicación frontend estará disponible en la URL provista por Vite (usualmente http://localhost:5173).
🔑 Configuración de Variables de Entorno (.env)
El Backend requiere de un archivo .env en la raíz de su directorio para operar correctamente. Se incluye un archivo .env.example como plantilla.
⚠️ Nota de Seguridad: El archivo .env real contiene credenciales sensibles y está estrictamente excluido en el .gitignore para evitar que se suba al control de versiones.
Explicación de las Variables (.env.example)
•	PORT: Especifica el puerto en el que escuchará el servidor Express (Ej: 3000). Si no se define, se usará el puerto 3000 por defecto.
•	DATABASE_URL: La URI de conexión obligatoria para PostgreSQL. Requerida por Prisma.
o	Formato: postgresql://<USUARIO>:<CONTRASEÑA>@<HOST>:<PUERTO>/<NOMBRE_BD>?schema=public
•	JWT_SECRET: Llave secreta utilizada por jsonwebtoken para firmar y verificar de manera segura los tokens de sesión de los usuarios.
•	API_KEY: Clave de acceso estática para validar peticiones externas o de servicios integrados si fuese necesario.
🛠️ Ejemplos de Uso (API Endpoints)
El Backend expone las siguientes rutas principales bajo la URL base http://localhost:3000:
🔐 Módulo de Autenticación (/api/auth)
•	POST /api/auth/register : Registra a un nuevo usuario/administrador en el sistema. Las contraseñas se almacenan encriptadas.
•	POST /api/auth/login : Autentica al usuario y devuelve un token JWT válido para consumir rutas protegidas.
🎓 Módulo de Alumnos (/api/alumnos)
•	GET /api/alumnos : Obtiene el listado completo de los alumnos registrados.
•	POST /api/alumnos : Registra un nuevo alumno en la base de datos a través de Prisma.
•	GET / PUT / DELETE /api/alumnos/:id : Operaciones CRUD específicas para un alumno mediante su ID único.
📦 Tecnologías y Herramientas Destacadas
•	Express 5.x: Framework web rápido y minimalista para Node.js.
•	Prisma ORM: Herramienta de última generación para el modelado de datos y consultas tipadas.
•	Vite: Entorno de desarrollo rápido para el Frontend.
•	Oxlint & Rolldown: Herramientas de alto rendimiento para el análisis estático (linting) y empaquetado del lado del cliente.
📄 Licencia y Créditos
•	Licencia: x
