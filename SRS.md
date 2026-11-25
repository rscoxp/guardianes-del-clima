# Especificación de Requerimientos de Software (SRS)
## Guardianes del Clima

## 1. Introducción

### 1.1 Propósito
Este documento define los requerimientos funcionales y no funcionales de **Guardianes del Clima**, un juego educativo para niños sobre el cuidado del medio ambiente.

### 1.2 Alcance
El juego permite a una niña protagonista superar cinco misiones ecológicas en distintos escenarios. En cada misión el jugador resuelve una pregunta o actividad, recibe retroalimentación inmediata y avanza al completarla correctamente. Al terminar las cinco misiones se convierte en Guardián o Guardiana del Clima.

### 1.3 Definiciones
| Término | Significado |
|---|---|
| Misión | Reto ecológico que el jugador debe resolver en un escenario |
| Escenario | Pantalla con fondo y objetos relacionados con la misión |
| Actividad | Pregunta o acción que el jugador debe realizar para avanzar |
| Progreso | Estado de las misiones completadas y pendientes |

## 2. Descripción general

### 2.1 Perspectiva del producto
Juego independiente, de uso individual, con interfaz gráfica sencilla y flujo lineal de cinco misiones.

### 2.2 Usuarios
Niños en edad escolar. Pueden ser acompañados por un docente o familiar.

### 2.3 Restricciones y suposiciones
- Textos con palabras simples y fáciles de leer.
- No se solicita información personal innecesaria.
- Se asume que el juego se usa en un dispositivo compatible con la plataforma elegida por el equipo.

## 3. Requerimientos funcionales

| ID | Descripción | Prioridad | Criterio de aceptación |
|---|---|---|---|
| RF-01 | El sistema debe permitir iniciar una partida desde una pantalla principal. | Alta | Al presionar "Jugar" en la pantalla principal, se muestra la introducción o la primera misión. |
| RF-02 | El juego debe explicar brevemente la misión de la protagonista y el objetivo de convertirse en Guardiana del Clima. | Media | Antes de la primera misión se muestra un texto breve con el objetivo del juego. |
| RF-03 | El juego debe mostrar los escenarios correspondientes a las misiones ecológicas. | Alta | Cada misión carga su escenario propio (fondo y elementos). |
| RF-04 | Cada escenario debe presentar objetos relacionados con la tarea que el jugador debe resolver. | Alta | El escenario muestra al menos los objetos necesarios para resolver la actividad. |
| RF-05 | El juego debe incluir cinco misiones relacionadas con acciones de cuidado del medio ambiente. | Alta | Existen exactamente cinco misiones jugables, cada una sobre un tema ecológico distinto. |
| RF-06 | El juego debe presentar una pregunta o actividad que el jugador debe resolver para avanzar. | Alta | Cada misión muestra una pregunta o actividad y no permite avanzar sin resolverla. |
| RF-07 | El sistema debe identificar si la respuesta o acción del jugador es correcta o incorrecta. | Alta | Ante una respuesta correcta o incorrecta, el sistema la clasifica sin errores. |
| RF-08 | Si la respuesta es correcta, se muestra un mensaje positivo; si es incorrecta, se permite intentarlo de nuevo. | Alta | Respuesta correcta: aparece mensaje de felicitación. Respuesta incorrecta: aparece mensaje de ánimo y se puede reintentar sin límite. |
| RF-09 | El jugador debe poder pasar al siguiente escenario tras completar correctamente la misión actual. | Alta | Al completar la misión, se habilita el botón "Siguiente" que lleva al escenario siguiente. |
| RF-10 | El juego debe indicar qué misiones ha completado el jugador y cuáles faltan. | Media | Un indicador visible (por ejemplo, 3 de 5 estrellas) refleja el progreso actual. |
| RF-11 | Al completar las cinco misiones, el juego debe mostrar un mensaje de felicitación indicando que el jugador se convirtió en Guardián o Guardiana del Clima. | Alta | Tras la quinta misión se muestra la pantalla final con el mensaje de felicitación. |
| RF-12 | El juego debe permitir comenzar una nueva partida desde el inicio. | Media | Desde la pantalla final, el botón "Jugar de nuevo" reinicia el progreso a la misión 1. |

## 4. Requerimientos no funcionales

| ID | Descripción | Prioridad | Criterio de aceptación |
|---|---|---|---|
| RNF-01 | **Usabilidad:** la interfaz debe ser sencilla y fácil de entender para niños. | Alta | En una prueba con al menos 3 niños, cada uno inicia y completa una misión sin ayuda. |
| RNF-02 | **Usabilidad:** instrucciones, preguntas y mensajes deben usar palabras simples y fáciles de leer. | Alta | Los textos usan oraciones cortas y vocabulario de nivel escolar básico, revisado por el equipo o un docente. |
| RNF-03 | **Rendimiento:** las pantallas y acciones deben responder rápidamente. | Alta | El cambio de pantalla y la respuesta a una acción tardan menos de 2 segundos. |
| RNF-04 | **Fiabilidad:** el juego debe validar las respuestas de forma consistente y evitar errores que impidan avanzar. | Alta | En las pruebas, la misma respuesta produce siempre el mismo resultado y no hay bloqueos al avanzar. |
| RNF-05 | **Accesibilidad visual:** el texto debe ser legible y los elementos importantes deben distinguirse claramente. | Media | El texto principal tiene tamaño grande y contraste alto con el fondo; los botones se distinguen a simple vista. |
| RNF-06 | **Privacidad:** el juego no debe solicitar información personal innecesaria; si guarda datos, solo los necesarios. | Alta | No existen campos de datos personales y solo se almacena el progreso de la partida. |
| RNF-07 | **Portabilidad y disponibilidad:** debe funcionar en las plataformas para las que se diseñe y, si es posible, sin conexión permanente a Internet. | Media | Las funciones principales se ejecutan en la plataforma objetivo y sin conexión durante una partida completa. |
| RNF-08 | **Mantenibilidad:** el diseño debe permitir agregar o modificar misiones y preguntas sin reconstruir todo el juego. | Media | Una misión o pregunta nueva se agrega modificando solo datos o configuración, sin cambiar el núcleo del juego. |
