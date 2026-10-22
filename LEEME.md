# Recorrido de bienvenida Sitti · Publicación en Vercel

Sitio estático: no necesita instalar dependencias ni compilar.

## Contenido de la carpeta

| Archivo | Para qué sirve |
|---|---|
| `index.html` | El recorrido completo: puerta de bienvenida, mapa 3D, Oni y Arya, "Caminar adentro" |
| `como-ingresar.mp4` | Video vertical que muestra por dónde ingresar a la sede (se ve primero al abrir la puerta) |
| `bienvenida-gerente-general.mp4` | Video de bienvenida de la gerente general, Diana Giraldo (se ve en segundo lugar) |
| `musica-fondo.mp3` | Música de fondo (suena bajita y se puede pausar) |
| `mesa-de-ayuda.mp4` | Video que se abre al elegir Mesa de ayuda |
| `experiencia-de-servicio.mp4` | Video que se abre al elegir Experiencia de servicio |
| `conexion-de-soluciones.mp4` | Video que se abre al elegir Conexión de soluciones |
| `aseguramiento-contravencional.mp4` | Video que se abre al elegir Aseguramiento |
| `cartera.mp4` | Video que se abre al elegir Cartera |
| `financiera-administrativa.mp4` | Video que se abre al elegir Financiera y administrativa |
| `notificaciones.mp4` | Video que se abre al elegir Gestión de notificaciones |
| `cad.mp4` | Video que se abre al elegir CAD · Archivo |
| `correspondencia.mp4` | Video que se abre al elegir Correspondencia |
| `radicacion.mp4` | Video que se abre al elegir Radicación |
| `sala-de-lactancia.mp4` | Video vertical que se abre al elegir Sala de lactancia |
| `vercel.json` | Configuración mínima de Vercel (caché para música y videos) |

## Opción A · Desde el navegador, con GitHub (sin instalar nada)

1. Entra a <https://github.com/new> y crea un repositorio, por ejemplo `sitti-recorrido`. Puede ser privado.
2. En el repositorio, elige **Add file → Upload files** y arrastra **todo el contenido** de esta carpeta. Guarda con **Commit changes**.
3. Entra a <https://vercel.com/new> e inicia sesión con tu cuenta de GitHub.
4. Elige **Import** junto al repositorio `sitti-recorrido`.
5. En **Framework Preset** deja **Other**. No cambies ningún comando y pulsa **Deploy**.
6. En cerca de un minuto Vercel te da un enlace del tipo `https://sitti-recorrido.vercel.app`. Ese enlace lo puede abrir cualquier persona, sin cuenta.

Cada vez que subas un cambio al repositorio, Vercel publica la nueva versión sola.

## Opción B · Con la terminal (Vercel CLI)

Requiere Node.js 18 o superior (<https://nodejs.org>). Abre una terminal en esta carpeta y ejecuta:

```bash
npx vercel
```

La primera vez te pide iniciar sesión y confirmar el proyecto; acepta los valores por defecto. Para publicar la versión definitiva:

```bash
npx vercel --prod
```

## Cómo agregar el video de otra área

1. Sube el video a la raíz del repositorio, en formato MP4 y con un nombre sin espacios. Por ejemplo: `experiencia-de-servicio.mp4`.
2. Abre `index.html`, busca el área en la lista `AREAS` (por ejemplo `id:'S'`) y agrégale la propiedad `video`:

   ```js
   {f:1,id:'S',letter:'S',name:'Experiencia de servicio', video:'experiencia-de-servicio.mp4', ...}
   ```

3. Sube los cambios. Al tocar esa área en el mapa, el video se abre y se reproduce, y en la lista aparece la marca "▶ VIDEO".

Identificadores de las áreas principales:

| Zona | Área | id |
|---|---|---|
| Naranja | Ingreso Sitti | `SEG` |
| Naranja | Mesa de ayuda | `MA` |
| Naranja | Cocineta | `COC` |
| Naranja | Experiencia de servicio | `S` |
| Naranja | Experiencia de servicio · Puestos | `P14` |
| Naranja | Taquillas · Experiencia de servicio | `TQS` |
| Naranja | Taquillas de cobro · Experiencia de servicio | `TQC` |
| Naranja | Cajeros | `CAJ` |
| Naranja | Oficina del banco | `OBC` |
| Naranja | Salida de emergencia (junto a la cocineta) | `SE` |
| Naranja | Bodega (junto a la salida de emergencia) | `BO1` |
| Naranja | Ascensor | `ASC` |
| Naranja | Escaleras de ingreso | `EM` |
| Naranja | Gerentes | `G` |
| Naranja | Lockers | `L` |
| Naranja | Centro de servicios (por la rampa) | `CSV` |
| Verde | Cobro coactivo / Gestión legal | `P106` |
| Verde | Experiencia y bienestar | `EB` |
| Verde | Coordinación jurídica y gestión de cobro | `OL` |
| Verde | Sala de reuniones | `JS` |
| Azul | Conexión de soluciones | `P3` |
| Azul | Fotodetección | `FD3` |
| Azul | Aseguramiento | `AS3` |
| Azul | Cartera | `CA` |
| Azul | Financiera y administrativa | `FA` |
| Azul | Coordinadores y líderes | `OCL` |
| Azul | CAD · Archivo | `CAD` |
| Azul | Digitalización | `DG` |
| Azul | Gestión de notificaciones | `NT` |
| Azul | Correspondencia (taquillas) | `CR` |
| Azul | Radicación | `RD` |

## Antes de compartirlo

El enlace de Vercel es público y muestra la distribución interna de la sede. Comparte el enlace solo con las personas que van a ingresar a Sitti. Si necesitas restringir el acceso, Vercel permite proteger el sitio con contraseña desde **Settings → Deployment Protection**; según el plan de Vercel, esta opción puede tener costo.
