# Heleta — Sistema Frontend y Backend

Resumen breve del proyecto que contiene la interfaz de usuario (Frontend) y la API/servicios (Backend).

## Estructura del repositorio

- Backend/: servidor, rutas y lógica del API.
- Frontend/: aplicación Next.js (app router) con interfaces y componentes.

## Tecnologías principales

- Backend: Node.js, Express, PostgreSQL (pg), JWT, dotenv.
- Frontend: Next.js, React, TailwindCSS, shadcn-ui.

## Backend

Descripción

El Backend expone una API REST usando Express. Gestiona autenticación, inventario, productos, ventas y reportes.

Ubicación principal

- Código de arranque: Backend/src/server.js
- Configuración de BD: Backend/src/config/database.js
- Rutas: Backend/routes/ (auth.js, inventario.js, productos.js, reportes.js, ventas.js)
- Middleware: Backend/src/middleware/auth.js

Requisitos

- Node 18+ y PostgreSQL

Variables de entorno (ejemplo)

- PORT=3001
- DATABASE_URL=postgres://user:password@host:port/dbname
- JWT_SECRET=tu_secreto

Instalación y ejecución

1. Ir a la carpeta Backend.
2. Instalar dependencias:

```
npm install
```

3. Ejecutar en desarrollo:

```
npm run dev
```

Comandos disponibles (según Backend/package.json)

- `dev`: nodemon src/server.js
- `start`: node src/server.js

Rutas principales

- /api/auth — autenticación (login/registro)
- /api/inventario — operaciones sobre inventario
- /api/productos — CRUD de productos
- /api/ventas — registrar/listar ventas
- /api/reportes — generación de reportes (PDF)

Notas

- Asegúrate de crear un archivo .env con las variables necesarias antes de iniciar.

## Frontend

Descripción

Aplicación Next.js (app router) que consume la API del Backend. Contiene páginas para login, dashboard, inventario, productos, reportes, usuarios y ventas.

Ubicación principal

- App: Frontend/app/
- Componentes UI: Frontend/components/ui/
- Código de cliente para llamadas API: Frontend/lib/api.ts

Requisitos

- Node 18+

Instalación y ejecución

1. Ir a la carpeta Frontend.
2. Instalar dependencias:

```
npm install
```

3. Ejecutar en desarrollo:

```
npm run dev
```

Comandos disponibles (según Frontend/package.json)

- `dev`: next dev
- `build`: next build
- `start`: next start
- `lint`: eslint

Integración con Backend

- Configura la URL base de la API en Frontend/lib/api.ts o mediante variables de entorno usadas por la aplicación.

## Desarrollo local (rápido)

1. Iniciar la base de datos PostgreSQL.
2. Configurar .env en Backend con DATABASE_URL y JWT_SECRET.
3. Levantar Backend:

```
cd Backend
npm run dev
```

4. Levantar Frontend en otro terminal:

```
cd Frontend
npm run dev
```
