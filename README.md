# Rúbrica del cuaderno

Aplicación web para evaluar el cuaderno del alumnado con una rúbrica: la predeterminada, de 8 criterios, o una propia importada desde Excel. Sirve para cualquier curso: se crea un grupo por cada clase (2º, 3º, 4º de ESO o lo que haga falta). Permite:

- registrar cada día la atención en clase;
- calcular la nota de cada unidad;
- generar informes en PDF por alumno;
- pasar las notas a iDoceo.

Toda la app está en un único archivo, `index.html`. No hay que instalar nada ni compilar nada.

## Funciones

- **Hoy:** cada día se marca a cada alumno como «Atiende», «Más o menos» (atiende a ratos), «No» (no atiende) o «Falta». Un botón marca como «atiende» a todos los que queden sin marcar.
- **Evaluar:** ficha por alumno con los criterios de la rúbrica de la unidad.
  - Al tocar un nivel se ve su descripción.
  - La ficha también tiene un campo de observaciones para el informe.
  - El criterio de atención diaria (en la rúbrica predeterminada, la actitud) se rellena solo a partir de la atención registrada en «Hoy», mientras no se le ponga un valor a mano.
- **Notas:** tabla de la unidad con cada criterio coloreado por nivel, la nota final y las faltas. Incluye:
  - un resumen de asistencia del grupo, con las fechas de las faltas, de los días «más o menos» y de los días sin atender;
  - los informes en PDF;
  - la exportación a iDoceo y a Excel.
- **Ajustes:**
  - grupos: crear y renombrar. También se crean desde el selector de grupo de arriba, con «＋ Nuevo grupo…»;
  - alumnado de cada grupo: importar la lista desde iDoceo, pegarla o añadir alumnos a mano. Los que se añaden después se colocan por orden alfabético de apellidos, y «Ordenar por apellidos» ordena una lista que no lo esté;
  - unidades: cada una con su rúbrica (la predeterminada o una importada), con o sin ficha de repaso y actividades voluntarias;
  - rúbricas: importar rúbricas desde Excel y descargar la plantilla;
  - copia de seguridad;
  - tema claro u oscuro;
  - evaluación de prueba: rellena al azar la asistencia, las notas y las observaciones del grupo para probar la app. Antes de hacerlo avisa de que sustituye los datos del grupo y pide confirmación, igual que «Borrar grupo».

## La rúbrica predeterminada y el cálculo de la nota

Es la rúbrica del cuaderno que trae la app y la que se usa si no eliges otra.

| Nº | Criterio | Peso |
|---|---|---|
| 1 | Copia completa del esquema | 20 % |
| 2 | Estructura y jerarquía del esquema | 10 % |
| 3 | Anotaciones de la explicación | 15 % |
| 4 | Cuaderno al día | 15 % |
| 5 | Identificación: fecha y título | 10 % |
| 6 | Letra y legibilidad | 10 % |
| 7 | Limpieza y resaltado | 10 % |
| 8 | Actitud durante la explicación | 10 % |

- Cada criterio puntúa de 0 (Nulo) a 4 (Excelente). La nota sobre 10 es la media ponderada de los criterios puntuados.
- **Nota provisional:** si faltan criterios por puntuar, la nota se calcula solo con los ya evaluados y se marca como provisional.
- **Ficha de repaso** (opcional por unidad): se añaden «Entrega de la ficha» (5 %) y «Actividades de la ficha» (15 %), y los 8 criterios pasan al 80 % de su peso. Si no se entrega la ficha, sus actividades cuentan 0.
- **Actividades voluntarias** (opcional por unidad): suman hasta +0,5 o +1 punto extra. La nota nunca pasa de 10.
- **Actitud automática:** se calcula según el porcentaje de días que el alumno atiende, contando solo los días registrados. Un día «más o menos» cuenta como el 35 % de un día atento, y las faltas no cuentan. Por ejemplo, con un día «atiende» y otro «más o menos», el porcentaje es (1 + 0,35) / 2 = 67,5 %, es decir, Regular (2).

  | Días atento | Nivel |
  |---|---|
  | 90 % o más | Excelente (4) |
  | 75 % o más | Bueno (3) |
  | 50 % o más | Regular (2) |
  | 25 % o más | Deficiente (1) |
  | Menos del 25 % | Nulo (0) |

## Rúbricas importadas desde Excel

Además de la predeterminada, puedes usar tus propias rúbricas. Se importan en *Ajustes → Unidades → Rúbricas* y se eligen al crear cada unidad.

**Flujo de trabajo**
1. Pulsa «Descargar plantilla». Genera un Excel con la rúbrica predeterminada ya rellena y una hoja de instrucciones.
2. Adáptala a mano o con Claude (por ejemplo, en un proyecto donde guardes tus rúbricas), **manteniendo su estructura**.
3. Impórtala con «Importar rúbrica (Excel)», revisa la vista previa y guárdala.
4. Cualquier rúbrica guardada se puede volver a exportar en Excel con su botón «Excel».

**Formato de la plantilla** (la app solo acepta este; si un archivo no lo sigue, dice qué falla):
- **Hojas:** «Castellano» y «Valencià», con los mismos criterios y niveles en el mismo orden. Cada una se usa para los informes en su idioma. Si solo hay una, sirve para los dos idiomas. Las demás hojas, como «Instrucciones», se ignoran.
- **Primera fila:** «Criterio | Peso (%) | Atención diaria» (en valenciano, «Criteri | Pes (%) | Atenció diària») y, desde la columna D, un nivel por columna con su puntuación entre paréntesis, por ejemplo «Excelente (4)». Puede haber tantos niveles como quieras, con un mínimo de dos.
- **Una fila por criterio:** nombre, peso y una descripción por nivel.
- **Peso:** si lo dejas vacío en todos los criterios, pesan lo mismo; si no suman 100, se ajustan.
- **Atención diaria:** «Sí» en el criterio que se rellena solo con la atención registrada en «Hoy», como la actitud. Como mucho uno.
- **De qué hoja se toman los datos:** el peso y la atención diaria salen de la hoja «Castellano».
- **Nombre:** la rúbrica toma el nombre del archivo; se puede cambiar en la vista previa.

**Cómo se usa**
- **Nota:** cada criterio puntúa sobre el nivel más alto de su rúbrica (3 sobre 4 cuenta el 75 % de su peso).
- **Cada unidad guarda su propia copia** de la rúbrica. Borrar una rúbrica de la biblioteca no afecta a las unidades que la usan, y una unidad que ya tiene notas no puede cambiar de rúbrica.
- **Espacio:** cada rúbrica ocupa unos pocos KB, así que caben cientos. Las rúbricas importadas entran en la copia de seguridad.

## Informes en PDF

Se generan desde la propia app:

- **PDF de un alumno:** desde su ficha, en «Evaluar».
- **PDF del grupo:** desde «Notas».

Cada informe recoge la nota (final o provisional), el nivel y la descripción de cada criterio, la atención en clase y las observaciones. Si no hay observaciones, el PDF deja un recuadro rayado para escribirlas a mano.

- **Extensión:** una página siempre que quepa. Solo pasa a dos si hace falta, y nunca se recorta información.
- **Idioma:** castellano o valenciano, por grupo. En valenciano también se traduce la rúbrica: la predeterminada ya está traducida y las importadas usan su hoja «Valencià».
- **Interruptores:**
  - **Aviso de nota incompleta:** indica qué criterios faltan por evaluar.
  - **Datos del profesor:** nombre, materia y grupo en la cabecera. Se editan en la misma tarjeta.
  - **Imprimir a doble cara:** cada alumno empieza en una hoja nueva. Si su informe ocupa una sola página, se añade un reverso en blanco.

El grupo aparece con el nombre que tiene en la app. Para que salga «3º C», el grupo tiene que llamarse así.

## Trabajar con iDoceo (en el Mac)

1. **Importar la lista:** en iDoceo, exporta el cuaderno de la clase en CSV y súbelo en *Ajustes → Alumnado*. Se toman los nombres en el mismo orden; las notas del archivo no se importan. Los alumnos que añadas después se colocan en su sitio por apellido. Si usas la app en el iPhone, pásate antes el archivo por AirDrop o iCloud Drive.
2. **Pasar la nota:** en *Notas → Pasar la nota a iDoceo*, descarga el CSV o el Excel. Los nombres van en la primera columna, escritos igual que en tu clase, y la nota en una columna nueva. Luego impórtalo en esa clase de iDoceo, en el Mac. Solo se emparejan los nombres idénticos.
3. **Rúbricas incompletas:** se puede elegir si esos alumnos salen con la nota en blanco o con la nota provisional.

## Dónde se guardan los datos

- **En GitHub Pages (sourenics.github.io) o abriendo `index.html` directamente:** los datos se guardan solo en ese navegador y en ese dispositivo (`localStorage`). La app muestra un aviso en este modo.
  - El PC y el iPhone **no comparten datos**: cada uno tiene los suyos.
  - Si se borran los datos del navegador, se pierden.
- **Dentro de Claude (publicada como artifact):** los datos se guardan en tu cuenta de Claude, son privados (ni siquiera los ve quien comparta el enlace) y **se sincronizan entre dispositivos**: lo que haces en el Mac aparece en el iPhone si abres la app con la misma cuenta. Es la opción recomendada si usas la app en más de un dispositivo.
  - Se abre desde el enlace privado del artifact, en el navegador o en la app de Claude, con la sesión iniciada.
  - Usarla no gasta cuota de Claude: la app no le hace preguntas al modelo, solo guarda datos.
  - Cada grupo, unidad y rúbrica importada es un documento propio. El límite es de 25 000 documentos por artifact y 256 KB por documento.

En los dos casos conviene descargar de vez en cuando una **copia de seguridad** (*Ajustes → Copia de seguridad*). Es un archivo JSON con todos los grupos, unidades, notas, asistencia, observaciones, datos del profesor y rúbricas importadas.

Para **pasar los datos de un dispositivo a otro**:
1. En el primero, descarga la copia de seguridad.
2. En el segundo, cárgala con «Cargar copia».

Los grupos de la copia sustituyen a los mismos grupos si ya existen; el resto no se toca. Así se pasan también los datos de GitHub Pages a la versión de Claude.

## Versión en Claude

El mismo `index.html` se publica como artifact de Claude, sin la cabecera del documento (`<!doctype>`, `<head>`), que la pone Claude, y con las capacidades `db`, `user` y `downloads`. La app detecta dónde se está ejecutando:

- **Dentro de Claude:** guarda en la base de datos privada de la cuenta (`data/users/<id>/…`) y descarga los archivos con la confirmación de Claude.
- **Fuera de Claude:** guarda en el navegador.

El artifact no se actualiza solo con GitHub: después de cada cambio en `main` hay que volver a publicarlo en el mismo enlace.

## Dispositivos

Pensada para usarse en el **PC** y en el **iPhone**:

- En el móvil, los botones son grandes y los campos tienen el tamaño justo para que Safari no amplíe la página al tocarlos.
- En el PC, el contenido se centra y la barra de navegación flota abajo. Los márgenes llevan una línea de margen de cuaderno y dibujos tenues de Geografía e Historia, que no aparecen en el móvil.

### Icono para el Dock y la pantalla de inicio

La carpeta [`iconos`](iconos) tiene el icono de la app: un cuaderno con una marca de verificación sobre fondo azul.

| Archivo | Para qué sirve |
|---|---|
| `icono-mac-1024.png` | Dock del Mac, con la forma y la sombra de los iconos de macOS |
| `icono-1024.png` | Icono cuadrado a sangre, para cuando el sistema recorta las esquinas |
| `apple-touch-icon.png` | Lo usan Safari y el iPhone al añadir la versión de GitHub Pages al Dock o a la pantalla de inicio |
| `icono.svg` | Icono de la pestaña del navegador |

- **Versión de GitHub Pages:** al añadirla al Dock (*Safari → Archivo → Añadir al Dock*) o a la pantalla de inicio del iPhone (*Compartir → Añadir a pantalla de inicio*), sale el icono de la app sin hacer nada.
  - Ojo: la app añadida puede guardar los datos aparte de los de Safari. Si no ves tus datos, pásalos con una copia de seguridad.
- **Versión en Claude:** sale el icono de Claude, porque la página es de claude.ai y el artifact no puede cambiarlo. Se cambia a mano con `icono-mac-1024.png`:
  - **Desde la app del Dock:** ábrela y entra en los ajustes del menú con su nombre. Allí se pulsa el icono y se elige la imagen.
  - **Desde el Finder:** en la carpeta *Aplicaciones* de tu usuario (`~/Applications`), selecciona la app y abre *Archivo → Obtener información*. Arrastra la imagen sobre el icono pequeño de arriba a la izquierda.

## Privacidad

La app maneja nombres y notas del alumnado:

- **Dentro de Claude:** los datos solo se guardan en tu cuenta.
- **En el navegador:** los datos solo se guardan en ese navegador.
- **Archivos exportados:** los PDF, CSV, Excel y copias de seguridad se generan en el propio dispositivo y no se suben a ningún sitio.
- **Recursos externos:** la app solo carga las fuentes de Google Fonts y dos librerías de cdnjs. Al descargarlas no se envía ningún dato del alumnado.

## Aspectos técnicos

- **Un solo archivo:** `index.html` contiene el HTML, el CSS y el JavaScript, sin frameworks ni paso de compilación.
- **Librerías externas (cdnjs):**
  - [SheetJS](https://sheetjs.com/) 0.18.5, para leer y escribir Excel;
  - [jsPDF](https://github.com/parallax/jsPDF) 2.5.1, para los PDF. Se descarga solo la primera vez que se genera un PDF.
- **Fuentes:** Atkinson Hyperlegible y Bricolage Grotesque, de Google Fonts.
- **Dónde está cada cosa en el código:**
  - La rúbrica predeterminada en castellano está en las constantes `CRIT`, `F1`, `F2` y `VOL`, y se convierte en `DEFAULT_RUBRIC`, el mismo formato que las rúbricas importadas.
  - El importador de rúbricas es `parseRubricSheet` y `readRubricFile`; la plantilla, `downloadRubric` y `RUB_HELP`.
  - La versión en valenciano, en `VA` y `LEVELS_VA`.
  - Los textos del PDF, en `PDFT`.
  - Los datos por defecto del profesor, en `PROFILE0`.
  - Los umbrales de la actitud automática, en `ATT_THRESHOLDS`, y lo que vale un día «más o menos», en `MID_W`.
- **Probarla:** basta con abrir `index.html` en el navegador y pulsar «Probar con un grupo de ejemplo». Para tener datos con los que probar los informes y las exportaciones, usa *Ajustes → Evaluación de prueba*.
  - Rellena 10 días lectivos de asistencia por unidad, con días distintos para cada unidad, y puntúa todos los criterios salvo la actitud, que sale de la asistencia.
  - Deja un alumno sin puntuar y otro a medias, para ver las notas provisionales, y añade observaciones a algunos.
  - Está en la función `testFill`.

## Historial de cambios

Lo que ha cambiado en cada versión está en [CHANGELOG.md](CHANGELOG.md).

## Licencia

[GNU GPL v3](LICENSE).
