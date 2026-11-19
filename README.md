# CARLOTIS — build web

Esta carpeta contiene la exportación HTML5 de CARLOTIS (Godot 4.7.2).

- Exportada con el preset `Web` del proyecto.
- **Sin hilos** (`variant/thread_support=false`): funciona en GitHub Pages sin
  cabeceras COOP/COEP especiales.
- Archivos principales: `index.html`, `index.js`, `index.wasm` e `index.pck`.

## Publicar en GitHub Pages

1. Crea un repo nuevo en GitHub. Para Pages gratuito tiene que ser **público**.
2. Sube **todos** los archivos de esta carpeta a la raíz del repo. Desde aquí:

   ```bash
   git init
   git add .
   git commit -m "CARLOTIS web"
   git remote add origin https://github.com/TU_USUARIO/TU_REPO.git
   git push -u origin main
   ```

3. En GitHub entra en `Settings → Pages → Build and deployment`:
   - **Source:** `Deploy from a branch`
   - **Branch:** `main` / `/root`
   - Pulsa `Save`.
4. En 1–2 minutos estará en:

   `https://TU_USUARIO.github.io/TU_REPO/`

## Actualizar el juego

Esta carpeta es solo el **resultado** ya exportado. Cuando el proyecto cambie:

- **Forma simple:** vuelve a exportar desde Godot con el preset `Web` (sobrescribiendo
  esta carpeta), haz commit y push aquí.
- **Forma automática:** añadir un GitHub Actions workflow en el repo del código fuente
  que exporte a Web y publique en Pages. Así un `push` al proyecto actualiza el link
  sin copiar archivos a mano.

## Notas

- No abras `index.html` con doble clic (`file://`); necesita un servidor HTTP.
  GitHub Pages ya lo sirve correctamente.
- El audio en web empieza tras la primera interacción del usuario.
- Si cambias el nombre del repo, cambia la URL pública.
