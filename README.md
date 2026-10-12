# Apoliyar — página de lanzamiento

Sitio de “Próximamente” con el logo de Apoliyar, fotografía de alojamiento frente al lago y selector español/inglés. Adaptable a celulares y computadoras.

No requiere instalaciones, comandos, base de datos ni compilación. Esta versión presenta el proyecto; no procesa reservas, pagos ni datos de visitantes.

## 1. Crear el repositorio

1. Ingresá en https://github.com y entrá a tu cuenta.
2. Abrí https://github.com/new.
3. En **Repository name**, escribí `apoliyar`.
4. Elegí **Public**. GitHub Pages está incluido para repositorios públicos en GitHub Free.
5. Dejá desactivada la opción de agregar un README: esta carpeta ya incluye uno.
6. Hacé clic en **Create repository**.

## 2. Subir los archivos

1. Descomprimí el ZIP: clic derecho → **Extraer todo**.
2. Abrí la carpeta `apoliyar-github` que aparece dentro.
3. En el repositorio vacío, hacé clic en **uploading an existing file**. Si ya tiene archivos, usá **Add file → Upload files**.
4. Arrastrá TODO EL CONTENIDO de `apoliyar-github` al navegador: `index.html`, `README.md`, `.nojekyll` y la carpeta `assets` completa.
5. No subas el ZIP ni arrastres la carpeta exterior `apoliyar-github`. El archivo `index.html` debe quedar directamente en la raíz del repositorio.
6. Escribí `Primera versión de Apoliyar` en el mensaje del cambio y presioná **Commit changes**.

Si Windows no muestra `.nojekyll`, activá **Ver → Mostrar → Elementos ocultos** en el Explorador. Es un archivo vacío que indica que el sitio no necesita procesamiento de Jekyll.

## 3. Publicar con GitHub Pages

1. Dentro del repositorio, entrá en **Settings**.
2. En el menú izquierdo, entrá en **Pages**.
3. En **Build and deployment → Source**, seleccioná **Deploy from a branch**.
4. En **Branch**, seleccioná `main` y, al lado, **/(root)**.
5. Presioná **Save**.
6. Esperá a que GitHub termine de publicar. Volvé a **Settings → Pages**: allí aparecerá **Visit site**.

La dirección inicial será `https://TU-USUARIO.github.io/apoliyar/`. Reemplazá TU-USUARIO por tu usuario real de GitHub. Si el repositorio pertenece a una organización, usá su nombre.

El código usa rutas relativas, por lo que las imágenes funcionan tanto en esta dirección como luego en apoliyar.com.

## 4. Conectar apoliyar.com

Primero comprobá que el sitio funciona en la dirección de GitHub. Después:

1. Entrá en **Settings → Pages → Custom domain**.
2. Escribí `apoliyar.com` (sin https ni barras) y presioná **Save**.
3. GitHub creará automáticamente el archivo `CNAME`. No viene incluido de antemano para que puedas probar la dirección inicial antes de configurar el dominio.
4. En el panel DNS de tu dominio, configurá los siguientes registros:

| Tipo | Nombre | Contenido / destino |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | TU-USUARIO.github.io |

`@` significa el dominio principal. El CNAME de www lleva tu usuario u organización, sin https y sin /apoliyar al final.

Si hay registros A, AAAA o CNAME anteriores para `@` o `www` apuntando a otro alojamiento, revisalos y reemplazá únicamente los que entren en conflicto. Conservá los registros de correo (MX y sus TXT) y los de otros servicios. No agregues las IP de GitHub junto a las de otro proveedor de alojamiento.

Si administrás los DNS en Cloudflare, empezá con estos registros en **DNS only / Solo DNS** (nube gris) mientras GitHub verifica el dominio y emite el certificado. Usá TTL automático.

5. Volvé a **Settings → Pages** y esperá a que la comprobación DNS termine.
6. Activá **Enforce HTTPS** cuando la opción esté disponible.
7. Probá `https://apoliyar.com` y `https://www.apoliyar.com`.

Los cambios DNS pueden tardar hasta 24 horas en propagarse. La emisión del certificado puede requerir tiempo adicional. Si GitHub muestra un problema, compartí una captura del mensaje y de los registros DNS.

Esta exportación funciona independientemente de la versión de revisión creada en ChatGPT Sites. No uses los registros A/TXT de Sites para conectar la versión de GitHub Pages.

## 5. Modificar la página más adelante

- Para cambiar textos, abrí `index.html` en GitHub, tocá el lápiz, editá y guardá con **Commit changes**. Hay textos en español e inglés; actualizá ambos cuando corresponda.
- Para cambiar imágenes, reemplazá el archivo de la carpeta `assets` conservando el mismo nombre.
- Cada cambio en `main` vuelve a publicar el sitio automáticamente.
- Para abrirlo en tu computadora antes de subirlo, hacé doble clic en `index.html` manteniendo `assets` a su lado.

## Archivos

| Archivo | Función |
|---|---|
| index.html | Página, estilos y selector de idioma |
| assets/logo.webp | Logo de Apoliyar |
| assets/lake.webp | Fotografía de fondo |
| assets/favicon.png | Icono de la pestaña |
| .nojekyll | Publicación estática sin Jekyll |
| README.md | Esta guía |

La imagen para vistas previas de enlaces apunta a `https://apoliyar.com/assets/lake.webp`; estará disponible en esa dirección cuando conectes el dominio. No hay claves, contraseñas, herramientas de ChatGPT ni dependencias externas en el paquete.

## Documentación oficial

- Subir archivos: https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository
- Activar Pages: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- Dominio propio: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site

Guía preparada el 12 de octubre de 2026.
