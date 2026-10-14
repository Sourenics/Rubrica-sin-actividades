# Historial de cambios

Cambios de la app agrupados por cada fusión en `main`, que es lo que publica GitHub Pages. Lo más reciente va arriba.

## 2026-10-14 · Atención «más o menos»

### Añadido
- **«Más o menos» en «Hoy»:** cuarta opción, entre «Atiende» y «No», para quien atiende solo a ratos. El recuento del día tiene una casilla más para ellos.
- **Actitud automática:** cada día «más o menos» cuenta como el 35 % de un día atento.
- **Informes y exportaciones:**
  - la ficha de evaluación y el PDF indican cuántos días fueron «más o menos»;
  - el resumen de asistencia muestra sus fechas;
  - el Excel completo añade las columnas «Días más o menos» y «Fechas más o menos».

### Cambiado
- **Botones de atención en el móvil:** cada uno ocupa el ancho de su texto para que los cuatro quepan en una línea, también en el iPhone.

## 2026-10-14 · Versión en Claude con datos sincronizados ([#6](https://github.com/Sourenics/Rubrica-sin-actividades/pull/6))

### Añadido
- **Versión en Claude:** la app se publica también como artifact privado de Claude. Allí los datos se guardan en la cuenta y se sincronizan entre el Mac y el iPhone. GitHub Pages sigue funcionando igual, con los datos en cada navegador.
- **`CLAUDE.md`:** recoge la forma de trabajar del proyecto y cómo mantener a la par GitHub Pages y la versión en Claude.

### Cambiado
- **Rúbricas importadas:** cada una se guarda en su propio documento en lugar de ir todas dentro del perfil del profesor. En Claude cada documento admite 256 KB, así que dentro del perfil cabían unas 20 rúbricas; ahora no hay límite práctico.
- **Conversión automática:** las rúbricas guardadas con la versión anterior y las de las copias de seguridad antiguas se convierten solas.

## 2026-10-14 · Fondo con más vida en el PC ([#5](https://github.com/Sourenics/Rubrica-sin-actividades/pull/5))

### Cambiado
- **Fondo:** manchas de color muy suaves detrás de la cuadrícula, en modo claro y oscuro.
- **Pantallas anchas:**
  - una línea de margen doble, como la de las libretas, junto al contenido;
  - dibujos a trazo en los márgenes con motivos de Geografía e Historia: globo terráqueo, brújula, columna clásica, reloj de arena, chincheta de mapa, libro abierto, lápiz, regla, estrella y marca de verificación.
  - Los dibujos son muy tenues y se mueven con un vaivén lento, que se desactiva si el sistema pide reducir el movimiento. En el móvil no aparecen.

## 2026-10-14 · Rúbricas propias desde Excel ([#4](https://github.com/Sourenics/Rubrica-sin-actividades/pull/4))

### Añadido
- **Rúbricas importadas** en *Ajustes → Unidades → Rúbricas*:
  - **Plantilla:** «Descargar plantilla» genera un Excel con la rúbrica predeterminada, una hoja «Castellano», otra «Valencià» y una de instrucciones.
  - **Importación:** «Importar rúbrica (Excel)» muestra una vista previa con los idiomas, los niveles, los criterios con su peso y el criterio de atención diaria.
  - **Biblioteca:** las rúbricas guardadas se pueden volver a exportar en Excel o borrar.
- **Rúbrica por unidad:** se elige al crear la unidad y la predeterminada sigue siendo la opción por defecto. Cada unidad guarda su propia copia, y una unidad que ya tiene notas no puede cambiar de rúbrica.
- **Cualquier número de niveles:** la evaluación, la tabla de notas, el Excel completo, la exportación a iDoceo y los PDF funcionan con cualquier escala (por ejemplo, de 1 a 4). Cada criterio puntúa sobre el nivel más alto.
- **Atención diaria:** una rúbrica importada puede tener un criterio que se rellena solo con la atención registrada en «Hoy», como la actitud de la predeterminada.
- **Informes en valenciano:** usan la hoja «Valencià» de la rúbrica importada.

### Cambiado
- **Formato único:** el importador solo acepta la plantilla de la app. Si un archivo no la sigue, explica qué falla: falta la hoja, la cabecera está mal, un nivel no tiene puntuación o las hojas tienen criterios distintos.

### Corregido
- **Casillas en iPhone:** en modo oscuro salían como cuadrados negros.

## 2026-10-13 · Copias de seguridad, fecha y grupos de cualquier curso ([#3](https://github.com/Sourenics/Rubrica-sin-actividades/pull/3))

### Añadido
- **Nuevo grupo desde la cabecera:** opción «＋ Nuevo grupo…» en el selector de grupo.
- **Renombrar grupos:** el nombre del grupo actual se puede cambiar en *Ajustes → Grupos*.

### Cambiado
- **Cualquier curso:** la app ya no habla solo de «3º ESO» y el grupo de ejemplo se llama «Grupo de ejemplo».
- **README:** explica el uso desde GitHub Pages y cómo pasar los datos entre dispositivos.

### Corregido
- **Copia de seguridad:** al cargarla, las unidades no aparecían hasta cargarla una segunda vez.
- **Fecha de «Hoy» en el móvil:** las flechas y el campo de fecha quedaban desalineados.

## 2026-10-13 · README ([#2](https://github.com/Sourenics/Rubrica-sin-actividades/pull/2))

### Añadido
- `README.md`, con el uso de la app, la rúbrica, los informes, iDoceo, los datos y la privacidad.

## 2026-10-13 · Rediseño e informes en PDF ([#1](https://github.com/Sourenics/Rubrica-sin-actividades/pull/1))

### Añadido
- **Informes en PDF:**
  - por alumno (desde su ficha) o de todo el grupo;
  - con la nota, cada criterio con su nivel y su descripción, la atención en clase y las observaciones;
  - en castellano o valenciano según el grupo;
  - con interruptores para el aviso de nota incompleta, los datos del profesor y la impresión a doble cara.
  - Ocupan una página siempre que quepa.
- **Observaciones por alumno** en la ficha de evaluación. También salen en el Excel completo.
- **Selector de tema:** automático, claro u oscuro.
- **Tabla de notas** con las celdas coloreadas por nivel y la leyenda de criterios con su peso.

### Cambiado
- **Nuevo aspecto visual:**
  - cabecera y barra inferior translúcidas, avatares con iniciales, contadores en tarjetas;
  - barra de progreso en la ficha y criterios numerados;
  - sombras suaves y respuesta al pulsar.
- **iPhone:** los campos tienen 16 px para que Safari no amplíe la página. En «Hoy», los botones Atiende / No / Falta van debajo del nombre.
- **iDoceo:** las instrucciones están adaptadas al uso en el MacBook.

### Corregido
- **Tabla de notas:** la columna de nombres se reducía a una letra por línea.
- **Plurales** incorrectos («1 faltas», «1 de 1 días»…).
- **Casilla de iDoceo:** «Dejar su nota en blanco» quedaba descolocada.

## 2026-10-13 · Versión inicial

- Primera versión de la app subida al repositorio.
