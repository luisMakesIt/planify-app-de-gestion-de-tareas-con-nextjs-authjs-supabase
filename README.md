# Planify

Aplicación web para gestionar espacios de trabajo y tareas, construida con **Next.js 14**, **Auth.js**, **Supabase**, **Redux Toolkit** y **Tailwind CSS**.

<p align="center">
  <img src="docs/assets/planify-login.png" alt="Pantalla de inicio de sesión de Planify" width="100%" />
</p>

## Resumen

Planify centraliza tareas en espacios de trabajo. El flujo principal permite autenticación con Google, creación de espacios, carga de tareas y visualización de listas con formularios validados.

## Características

- Inicio de sesión con Google mediante Auth.js.
- Persistencia y adaptador de autenticación con Supabase.
- Gestión de espacios de trabajo.
- Gestión de tareas por espacio.
- Estado global con Redux Toolkit.
- Formularios con React Hook Form y Zod.
- UI con Tailwind CSS y componentes estilo shadcn/ui.

## Stack

- Next.js 14.2.2
- React 18
- TypeScript
- Auth.js / NextAuth v5 beta
- Supabase
- Redux Toolkit
- Tailwind CSS
- Zod

## Variables de Entorno

Creá un archivo `.env.local` en la raíz del proyecto:

```bash
AUTH_SECRET=your-auth-secret
NEXT_PUBLIC_SUPABASE_URL=your-supabase-url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-supabase-anon-key
SUPABASE_SERVICE_ROLE_KEY=your-supabase-service-role-key
AUTH_GOOGLE_ID=your-google-client-id
AUTH_GOOGLE_SECRET=your-google-client-secret
SUPABASE_JWT_SECRET=your-supabase-jwt-secret
```

## Instalación

```bash
npm ci
npm run dev
```

Abrí `http://localhost:3000`.

## Validación Local

Para actualizar la imagen del README se levantó la app localmente en `http://127.0.0.1:3014` con variables de entorno locales de prueba y se capturó la pantalla de inicio de sesión.

Validación realizada:

```bash
npm ci
npm run dev -- --hostname 127.0.0.1 --port 3014
```

`npm run build` compila el código, pero falla en la fase de lint por issues existentes:

- `components/SkeletonBreadCrumbs.tsx`: comillas sin escapar (`react/no-unescaped-entities`).
- `app/spaces/page.tsx`: warning de dependencia faltante en `useEffect`.

## Estructura Relevante

```text
app/              # App Router de Next.js
components/       # UI, auth, spaces y tasks
redux/            # Store y slices
services/         # Servicios de auth, espacios y tareas
schemas/          # Validaciones Zod
lib/              # Supabase client, utils y manejo de errores
```
