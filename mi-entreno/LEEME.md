# Mi entreno — instalar en el iPhone

Esta carpeta es la app entera. Solo necesita estar en una URL https para que
el iPhone la pueda instalar en la pantalla de inicio.

## Opción rápida (2 minutos, sin cuenta)

1. Entra en https://app.netlify.com/drop desde el ordenador.
2. Arrastra **la carpeta `mi-entreno` completa** (no los archivos sueltos).
3. Te da una URL del tipo `https://algo-random.netlify.app`. Cópiala.
4. Ábrela en **Safari** en el iPhone (tiene que ser Safari, no Chrome).
5. Botón Compartir → **Añadir a pantalla de inicio** → Añadir.

Ya tienes el corazón rosa en la home. Se abre a pantalla completa, sin barra
del navegador, y funciona sin conexión.

## Opción GitHub Pages

1. Crea un repo, sube el contenido de esta carpeta a la raíz.
2. Settings → Pages → Source: Deploy from a branch → `main` / `root`.
3. Espera un minuto y abre la URL en Safari → Añadir a pantalla de inicio.

## Cosas que conviene saber

- Los datos se guardan en el propio iPhone (localStorage del sitio). No se
  van si cierras la app, pero sí si borras los datos de Safari o desinstalas
  el icono. Usa **Editar → Guardar copia de mis datos** de vez en cuando.
- El aviso de fin de descanso es un sonido. iOS no permite vibración desde web.
  Mientras descansas, la pantalla intenta mantenerse encendida.
- Para actualizar la app: vuelve a arrastrar la carpeta a Netlify Drop. En el
  iPhone, cierra la app del todo y ábrela de nuevo.

## Editar el código

`app.jsx` es el fuente. Para recompilar tras un cambio:

    npm install
    npx esbuild app.jsx --bundle --minify --jsx=automatic --outfile=bundle.js
    npx tailwindcss -i src.css -o app.css --minify
