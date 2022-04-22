# PoCConcetradorLogEventosProcesos
Prueba de concepto de concentrador de log de eventos de procesos utilizando herramientas LowCode

Las organizaciones anhelan la transparencia y trazabilidad de sus procesos, sin embargo, en general se quedan sólo con las buenas intenciones para alcanzarlo.

Esta prueba de concepto, muestra como utilizando herramientas LowCode de la suite PowerPlatform es posible construir un concetrador de datos de eventos de procesos que se consume mediante una API (servicio web utilizando protocolo HTTP y mensaje JSON)

El ejercicio incluye una sencilla aplicación en PowerApps que genera datos de eventos, los cuales son enviados al concetrador de log. Los eventos enviados son el inicio de una actividad (al hacer clic) en botón "Editar" la actividad y el evento de fin de la misma al hacer "Guardar".

Desde la aplicación de PowerApps se invocan o llaman a 2 flujos de Power Automate ("EdiciónActividad") y ("GuardaActividad") para enviar los parámetros de los eventos de inicio y fin de la actividad.

Desde los 2 flujos anteriores, a su vez se llama a un tercer flujo (API) "RegistroEvento" que es flujo que almacena los registros de eventos del proceso (los de inicio y fin) y; en el caso de que sea un evento de fin, busca a su correspondiente evento de inicio y le añade en el campo fecha hora (TimeStamp) "Fin".

En este repositorio, está el respaldo de la aplicación (AppEjemploDatosEvento) realizada en PowerApps, los 3 flujos anteriores de PowerAutomate, así como también las 4 tablas de datos y su estructura (notar que muchas de las columnas son añadidas por defecto por la herramienta) construidas en Dataverse: tabla Ejecutivo para definir quienes participan del proceso; tabla actividades para indicar las actividades del proceso; tabla Caso para almacenar datos del caso y; tabla Evento para almancenar los registros de eventos (que en su conjunto sería el Log de proceso).

También se comparte el archivo de ejemplo de log de proceso, que puede ser visualizado en cualquier herramienta de minería de procesos y el flujo del proceso diseñado en notación BPMN, que puede ser utilizado para análisis de comparación con el proceso descubierto, así como realizar análisis de conformidad.
Cualquier duda, sobre la reconstrucción de esta prueba de concepto o consulta relacionada con minería de procesos, BPM será muy bienvenida para compartir experiencias.

https://www.linkedin.com/in/gonzalo-rodrigo-z%C3%BA%C3%B1iga-lara-99356540/

gonzalozuniga@yahoo.com
