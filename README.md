# Panel del Taller

App web para gestión de operarios, órdenes de trabajo, fichajes y control de horas.

## Archivos del proyecto

```
taller-app/
├── index.html      ← App completa
├── manifest.json   ← Configuración PWA (instalar en móvil)
├── sw.js           ← Service Worker (funciona sin conexión)
└── README.md       ← Este archivo
```

## Cómo personalizar

### Cambiar nombres y PINs de operarios

Abre `index.html` y busca la sección `DATOS` (línea ~130).

Cada operario tiene este formato:
```js
{ id: 'op1', nombre: 'Miguel Sánchez', rol: 'Operario de metal', iniciales: 'MS', pin: '1234', esEncargado: false }
```

Cambia `nombre`, `rol`, `iniciales` y `pin` por los datos reales.

El encargado tiene su propio acceso con `pin: '0000'` — cámbialo también.

### Añadir más operarios

Copia un bloque de operario dentro de la línea correspondiente:
```js
{ id: 'op7', nombre: 'Nuevo Trabajador', rol: 'Su rol', iniciales: 'NT', pin: '9999', esEncargado: false }
```

⚠️ El `id` debe ser único (op7, op8, etc.)

## Cómo subir a GitHub y publicar en Vercel

### Paso 1 — Crear cuenta en GitHub
1. Ve a https://github.com
2. Clic en "Sign up" y crea una cuenta gratuita

### Paso 2 — Crear repositorio
1. Clic en el "+" arriba a la derecha → "New repository"
2. Nombre: `taller-app`
3. Selecciona "Public"
4. Clic en "Create repository"

### Paso 3 — Subir los archivos
1. En la página del repositorio clic en "uploading an existing file"
2. Arrastra los 4 archivos: index.html, manifest.json, sw.js, README.md
3. Clic en "Commit changes"

### Paso 4 — Publicar con Vercel
1. Ve a https://vercel.com
2. Clic en "Sign Up" → "Continue with GitHub"
3. Clic en "Add New Project"
4. Selecciona tu repositorio `taller-app`
5. Clic en "Deploy"

En 1 minuto tendrás una URL como: `taller-app.vercel.app`

### Paso 5 — Instalar en el móvil como app
**Android:**
1. Abre la URL en Chrome
2. Menú (3 puntos) → "Añadir a pantalla de inicio"
3. Confirma → ya tienes el icono en el móvil

**iPhone:**
1. Abre la URL en Safari
2. Botón compartir → "Añadir a pantalla de inicio"
3. Confirma

## Accesos por defecto

| Perfil      | PIN  |
|-------------|------|
| Encargado   | 0000 |
| Miguel S.   | 1234 |
| Carlos R.   | 2345 |
| Antonio L.  | 3456 |
| Pedro M.    | 4567 |
| Juan G.     | 5678 |
| Rafael T.   | 6789 |

⚠️ Cambia todos los PINs antes de usar en producción.

## Funcionalidades

- Login con PIN por operario
- Panel de encargado con todas las líneas
- Panel personal por trabajador
- Fichaje de entrada/salida
- Órdenes de trabajo con horas estimadas vs ejecutadas
- Barra de progreso por OT (verde/naranja/rojo)
- Resumen semanal con exportación a CSV
- Funciona sin conexión (PWA)
- Se instala como app en móvil y tablet
