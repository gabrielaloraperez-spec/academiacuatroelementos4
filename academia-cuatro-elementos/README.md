# Academia de los Cuatro Reinos

Aplicación web del juego educativo (React + Vite + TypeScript + Tailwind).

## Requisitos

- Node.js 20+
- pnpm 10+

## Desarrollo local

```bash
pnpm install
pnpm dev
```

## Build de producción

```bash
pnpm build
pnpm preview
```

## Deploy en Vercel

Este repositorio tiene una sola app en `academia-cuatro-elementos/`.
Config recomendada en Vercel:

- **Root Directory:** `academia-cuatro-elementos`
- **Install Command:** `pnpm install --no-frozen-lockfile`
- **Build Command:** `pnpm run build`
- **Output Directory:** `dist`

También está versionado en `vercel.json`.

## Solución para error `404: Project not found` en Vercel

Ese error normalmente significa que el proyecto local quedó vinculado a un `projectId` viejo o a otro equipo.

Ejecuta estos pasos desde la carpeta de la app (`academia-cuatro-elementos`):

```bash
# 1) entrar en la app
cd academia-cuatro-elementos

# 2) limpiar vínculo local viejo
rm -rf .vercel

# 3) iniciar sesión y volver a enlazar
pnpm dlx vercel login
pnpm dlx vercel link

# 4) traer variables/config remota (opcional pero recomendado)
pnpm dlx vercel pull --yes --environment=production

# 5) validar build local
pnpm install
pnpm build

# 6) desplegar
pnpm dlx vercel --prod --yes
```

Si usas GitHub + Vercel Dashboard, verifica además:

1. Que el repositorio conectado sea `gabrielaloraperez-spec/academiacuatroelementos4`.
2. Que el **Root Directory** apunte a `academia-cuatro-elementos`.
3. Que el proyecto pertenezca al equipo/cuenta donde estás autenticado.
