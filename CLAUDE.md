# Instrucciones para Claude

## Forma de trabajar
- **Idioma:** todo en castellano: textos de la app, commits, PR, README y CHANGELOG.
- **Rama:** se trabaja en `dev`, partiendo siempre del último `main`. Los cambios llegan a `main` por PR, y la fusión la hace el propietario.
- **Documentación:** cada cambio actualiza el `README.md` y el `CHANGELOG.md`, con una entrada por fusión: fecha, título, enlace a la PR y apartados «Añadido / Cambiado / Corregido».
- **Pruebas:** antes de subir cambios, se prueban en el navegador con el grupo de ejemplo, en móvil y en PC, en modo claro y oscuro.

## Dos versiones de la misma app, siempre a la par
- **GitHub Pages:** publica `main` tal cual. Los datos se guardan en cada navegador.
- **Artifact privado de Claude:** https://claude.ai/artifact/RN8V8vcjv59Mjgm6Pym97k. Los datos se guardan en la cuenta de Claude y se sincronizan entre dispositivos.

Las dos versiones tienen las mismas funciones. Cuando se fusione una PR en `main`, hay que volver a publicar el artifact en el mismo enlace, así:

1. **Contenido:** lo que hay entre `<body>` y `</body>` de `index.html`, porque Claude añade su propia cabecera.
2. **Publicación:** con el parámetro `url` del enlace de arriba. Así se actualiza el mismo artifact y no se crea otro.
3. **Capacidades:** `db`, `user` y `downloads`. No se cambian.

La app detecta sola dónde se ejecuta, así que no hace falta código distinto para cada versión.

## Datos y formatos
- **Rúbricas importadas:** solo se acepta la plantilla de la app («Descargar plantilla»). No hay que adaptar el importador a otros modelos de Excel.
- **Almacenamiento en Claude:**
  - todo va en `data/users/<id>/…`;
  - grupos (`<gid>`), unidades (`<gid>/units/<uid>`), perfil (`profile`) y rúbricas (`rubric-<id>`) son documentos separados;
  - cada documento admite 256 KB.
