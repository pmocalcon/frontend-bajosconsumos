# Frontend estático para Vercel

- Este directorio contiene capturas estáticas del template `templates/index.html` generadas con `generate_static_front.py`. Las páginas son: `index.html`, `prepare.html`, `monthly.html`, `bimonthly.html` y `quarterly.html`, más los assets en `static/`.
- El archivo `vercel.json` enruta `/?selected_option=...` hacia el HTML correspondiente y sirve los assets desde `vercel-frontend/static`.
- Las acciones de los formularios siguen apuntando a las mismas rutas (`/step0`, `/step1`, etc.). Configura en Vercel un rewrite/proxy hacia tu backend real para mantener la conexión (por ejemplo, enrutar `/step.*` y `/select_option` al host donde corre Flask).
- Si cambias el template original o los assets, vuelve a ejecutar `python generate_static_front.py` para refrescar los HTML y, si modificaste `static/`, copia los cambios a `vercel-frontend/static`.
