\# Auditoría cruzada — UTEC Space Manager \- Gestor de Espacios de UTEC

\#\# 1\. Datos de la auditoría

| Campo | Información |  
|---|---|  
| Equipo auditor | ClassTeam |  
| Equipo auditado | G3/UTEC Space Manager |  
| Sistema | Gestor de Espacios de UTEC |  
| Fecha | 2026-10-14 |  
| Ambiente autorizado | https\://usm-utec.up.railway.app/ |  
| Versión / commit | Octubre 2026 |  
| Navegador y dispositivo | Chrome |  
| Alcance | Login,registro, gestion de espacio, gestion de evento, gestion de inventario, pruebas de ux, gestion de tutorias|

\#\# 2\. Resumen ejecutivo  
\*\*Objetivo:\*\* evaluar la usabilidad, las validaciones funcionales, la seguridad de acceso y la consistencia de las operaciones de pago en un ambiente de pruebas.

\*\*Resultado general:\*\*   
En general la aplicación funciona correctamente, solo encaramos detalles menores que no influyen en el uso común de la aplicación.Los principales hallazgos que hicimos fue en campos que permiten números exagerados, y en campos de fecha que se permiten con fecha anterior a la actual. 

| Severidad | Cantidad |  
|---|---:|  
| Crítica | \[0\] |  
| Alta | \[1\] |  
| Media | \[5\] |  
| Baja | \[5\] |

\#\# 3\. Funcionalidades revisadas

\- \[ X \] Inicio de sesión y cierre de sesión.  
\- \[ X \] Registro con usuario UTEC y externo (Google).  
\- \[ X \] Creación de reservas de salones.  
\- \[ X \] Visualización de Calendario.  
\- \[ X \] Creación de Eventos.  
\- \[ X \] Creación de Espacios.  
\- \[ X \] Dashboard de Estadísticas.  
\- \[ X \] Gestión de Inventario

\#\# 4\. Hallazgos

\#\# H-01 — Imposibilidad de aprobar una reserva desde el usuario administrador (A)

\* \*\*Categoría:\*\* Funcionalidad / gestión de reservas.  
\* \*\*Severidad sugerida:\*\* Alta (validar impacto real).  
\* \*\*Descripción:\*\* Tras realizar una reserva, no fue posible aprobarla desde el usuario administrador A.  
\* \*\*Precondiciones:\*\* Disponer de un usuario con permisos para crear reservas y un usuario administrador.  
\* \*\*Pasos para reproducir:\*\*  
  1\. Iniciar sesión con un usuario de prueba.  
  2\. Crear una reserva.  
  3\. Iniciar sesión con el usuario administrador A.  
  4\. Acceder al apartado de gestión de reservas e intentar aprobar la reserva.  
\* \*\*Resultado esperado:\*\* El administrador autorizado puede visualizar y aprobar la reserva correctamente.  
\* \*\*Resultado obtenido:\*\* No fue posible aprobar la reserva desde el usuario administrador A.  
\* \*\*Evidencia:\*\* \`\[Agregar captura o video en evidencias/H-01.png\]\`  
\* \*\*Recomendación:\*\* Verificar los permisos del administrador y el funcionamiento del proceso de aprobación de reservas.

\---

\#\# H-02 — Creación de una reserva con 300 proyectores (B)

\* \*\*Categoría:\*\* Validación de datos / reglas de negocio.  
\* \*\*Severidad sugerida:\*\* Alta (validar límites permitidos).  
\* \*\*Descripción:\*\* El sistema permite crear una reserva solicitando 300 proyectores, sin aplicar una restricción aparente sobre la cantidad.  
\* \*\*Precondiciones:\*\* Disponer de un usuario de prueba y acceso al formulario de reservas.  
\* \*\*Pasos para reproducir:\*\*  
  1\. Iniciar sesión en el sistema.  
  2\. Acceder al formulario de creación de reservas.  
  3\. Seleccionar los proyectores como recurso.  
  4\. Introducir una cantidad de 300 unidades.  
  5\. Completar los campos obligatorios y guardar la reserva.  
\* \*\*Resultado esperado:\*\* El sistema valida la cantidad solicitada según la disponibilidad del inventario y las reglas de negocio.  
\* \*\*Resultado obtenido:\*\* El sistema permite crear una reserva con 300 proyectores.  
\* \*\*Evidencia:\*\* \`\[Agregar captura en evidencias/H-02.png\]\`  
\* \*\*Recomendación:\*\* Implementar validaciones de cantidad máxima y disponibilidad de recursos.

\---

\#\# H-03 — Chatbot no funcional (M)

\* \*\*Categoría:\*\* Funcionalidad / asistente conversacional.  
\* \*\*Severidad sugerida:\*\* Media (validar impacto funcional).  
\* \*\*Descripción:\*\* El chatbot no funciona correctamente durante las pruebas realizadas.  
\* \*\*Precondiciones:\*\* Disponer de acceso al sistema y al apartado del chatbot.  
\* \*\*Pasos para reproducir:\*\*  
  1\. Acceder al sistema.  
  2\. Abrir el chatbot.  
  3\. Introducir una consulta de prueba.  
  4\. Enviar el mensaje y observar la respuesta.  
\* \*\*Resultado esperado:\*\* El chatbot procesa la consulta y proporciona una respuesta adecuada o informa de un problema.  
\* \*\*Resultado obtenido:\*\* El chatbot no funciona durante la prueba.  
\* \*\*Evidencia:\*\* \`\[Agregar captura o video en evidencias/H-03.png\]\`  
\* \*\*Recomendación:\*\* Verificar la integración del chatbot, la disponibilidad del servicio y el procesamiento de mensajes.

\---

\#\# H-04 — Búsqueda mediante inteligencia artificial no funcional (M)

\* \*\*Categoría:\*\* Funcionalidad / búsqueda inteligente.  
\* \*\*Severidad sugerida:\*\* Media (validar impacto en la búsqueda general).  
\* \*\*Descripción:\*\* La funcionalidad de búsqueda mediante inteligencia artificial no funciona durante las pruebas realizadas.  
\* \*\*Precondiciones:\*\* Disponer de acceso al sistema y a la herramienta de búsqueda con IA.  
\* \*\*Pasos para reproducir:\*\*  
  1\. Acceder al sistema.  
  2\. Abrir la herramienta de búsqueda con IA.  
  3\. Introducir una consulta de prueba.  
  4\. Ejecutar la búsqueda y observar el resultado.  
\* \*\*Resultado esperado:\*\* El sistema procesa la consulta y devuelve resultados relevantes o informa de un error.  
\* \*\*Resultado obtenido:\*\* La búsqueda mediante inteligencia artificial no funciona durante la prueba.  
\* \*\*Evidencia:\*\* \`\[Agregar captura o video en evidencias/H-04.png\]\`  
\* \*\*Recomendación:\*\* Revisar la conexión con el servicio de IA, el procesamiento de consultas y la recuperación de resultados.

\---

\#\# H-05 — Error al seleccionar un espacio al crear un elemento de inventario (B)

\* \*\*Categoría:\*\* Funcionalidad / validación de formularios / gestión de inventario.  
\* \*\*Severidad sugerida:\*\* Media (validar si bloquea la creación de elementos).  
\* \*\*Descripción:\*\* Al crear un nuevo elemento de inventario, el selector de espacio ofrece la opción «Sin asignar», pero al seleccionarla se produce un error.  
\* \*\*Precondiciones:\*\* Disponer de acceso al módulo de inventario y permisos para crear elementos.  
\* \*\*Pasos para reproducir:\*\*  
  1\. Acceder al módulo de inventario.  
  2\. Seleccionar la opción para crear un nuevo elemento.  
  3\. Completar los campos obligatorios.  
  4\. Seleccionar «Sin asignar» en el campo de espacio.  
  5\. Intentar guardar el elemento.  
\* \*\*Resultado esperado:\*\* Si «Sin asignar» es una opción válida, el sistema permite guardar el elemento sin un espacio asociado. De lo contrario, debe impedir la selección o mostrar una validación clara.  
\* \*\*Resultado obtenido:\*\* Al seleccionar «Sin asignar», el sistema genera un error.  
\* \*\*Evidencia:\*\* \`\[Agregar captura en evidencias/H-05.png\]\`  
\* \*\*Recomendación:\*\* Revisar las opciones del selector y las validaciones relacionadas con la asignación de espacios.

\---

\#\# H-06 — Creación de un elemento de inventario con mantenimiento en una fecha pasada (B)

\* \*\*Categoría:\*\* Validación de datos / gestión de inventario.  
\* \*\*Severidad sugerida:\*\* Media (validar impacto en la planificación del mantenimiento).  
\* \*\*Descripción:\*\* El sistema permite crear un elemento de inventario cuya fecha de próximo mantenimiento es anterior a la fecha actual.  
\* \*\*Precondiciones:\*\* Disponer de acceso al módulo de inventario y permisos para crear elementos.  
\* \*\*Pasos para reproducir:\*\*  
  1\. Acceder al módulo de inventario.  
  2\. Seleccionar la opción para crear un nuevo elemento.  
  3\. Completar los campos obligatorios.  
  4\. Introducir una fecha pasada como próximo mantenimiento.  
  5\. Guardar el elemento.  
\* \*\*Resultado esperado:\*\* El sistema valida la fecha de mantenimiento según las reglas establecidas y rechaza fechas pasadas cuando no estén permitidas.  
\* \*\*Resultado obtenido:\*\* El sistema permite crear el elemento con una fecha de mantenimiento pasada.  
\* \*\*Evidencia:\*\* \`\[Agregar captura en evidencias/H-06.png\]\`  
\* \*\*Recomendación:\*\* Incorporar validaciones de fechas y definir el tratamiento de los mantenimientos vencidos.

\---

\#\# H-07 — Creación de espacios sin límite de capacidad (B)

\* \*\*Categoría:\*\* Validación de datos / reglas de negocio / gestión de espacios.  
\* \*\*Severidad sugerida:\*\* Media (validar los requisitos de capacidad).  
\* \*\*Descripción:\*\* Al crear un espacio, el sistema no establece ni aplica un límite de capacidad.  
\* \*\*Precondiciones:\*\* Disponer de acceso al módulo de gestión de espacios y permisos para crear espacios.  
\* \*\*Pasos para reproducir:\*\*  
  1\. Acceder al módulo de gestión de espacios.  
  2\. Seleccionar la opción para crear un espacio.  
  3\. Completar los datos solicitados.  
  4\. Comprobar si existe un campo o una validación para establecer la capacidad máxima.  
  5\. Guardar el espacio.  
\* \*\*Resultado esperado:\*\* El sistema permite definir una capacidad máxima y garantiza que las reservas o asignaciones respeten dicho límite, según los requisitos.  
\* \*\*Resultado obtenido:\*\* No se observa un límite de capacidad al crear un espacio.  
\* \*\*Evidencia:\*\* \`\[Agregar captura en evidencias/H-07.png\]\`  
\* \*\*Recomendación:\*\* Definir la capacidad máxima permitida e implementar las validaciones correspondientes.

\---

\#\# H-08 — El formulario de creación de espacios conserva los datos anteriores (B)

\* \*\*Categoría:\*\* Interfaz de usuario / gestión del estado del formulario.  
\* \*\*Severidad sugerida:\*\* Media.  
\* \*\*Descripción:\*\* Después de crear un espacio, al iniciar la creación de otro, el formulario conserva los datos introducidos anteriormente.  
\* \*\*Precondiciones:\*\* Disponer de acceso al módulo de gestión de espacios y permisos para crear espacios.  
\* \*\*Pasos para reproducir:\*\*  
  1\. Acceder al módulo de gestión de espacios.  
  2\. Crear un espacio e introducir los datos correspondientes.  
  3\. Guardar el espacio.  
  4\. Volver a seleccionar la opción para crear un nuevo espacio.  
  5\. Comprobar los valores que aparecen en el formulario.  
\* \*\*Resultado esperado:\*\* El formulario aparece limpio o con los valores predeterminados definidos por el sistema.  
\* \*\*Resultado obtenido:\*\* El formulario mantiene los datos del espacio creado anteriormente.  
\* \*\*Evidencia:\*\* \`\[Agregar capturas antes y después en evidencias/H-08.png\]\`  
\* \*\*Recomendación:\*\* Restablecer el formulario después de una creación exitosa y comprobar que los datos anteriores no se reutilicen accidentalmente.

\---

\#\# H-09 — Creación de un evento con fecha de finalización en el pasado (M)

\* \*\*Categoría:\*\* Validación de datos / gestión de eventos.  
\* \*\*Severidad sugerida:\*\* Media.  
\* \*\*Descripción:\*\* El sistema permite crear un evento cuya fecha de finalización es anterior a la fecha actual.  
\* \*\*Precondiciones:\*\* Disponer de acceso al módulo de eventos y permisos para crear eventos.  
\* \*\*Pasos para reproducir:\*\*  
  1\. Acceder al módulo de eventos.  
  2\. Seleccionar la opción para crear un evento.  
  3\. Completar los campos obligatorios.  
  4\. Establecer una fecha de finalización pasada.  
  5\. Guardar el evento.  
\* \*\*Resultado esperado:\*\* El sistema aplica las reglas temporales definidas y rechaza fechas pasadas cuando no estén permitidas.  
\* \*\*Resultado obtenido:\*\* El sistema permite crear un evento con fecha de finalización en el pasado.  
\* \*\*Evidencia:\*\* \`\[Agregar captura en evidencias/H-09.png\]\`  
\* \*\*Recomendación:\*\* Incorporar validaciones temporales según las reglas de negocio y mostrar mensajes claros ante fechas no permitidas.

\---

\#\# H-10 — Creación de un evento con fecha de finalización anterior a la de inicio (M)

\* \*\*Categoría:\*\* Validación de datos / integridad temporal / gestión de eventos.  
\* \*\*Severidad sugerida:\*\* Alta (validar el impacto en la planificación).  
\* \*\*Descripción:\*\* El sistema permite crear un evento cuya fecha de finalización es anterior a su fecha de inicio, generando un intervalo temporal inconsistente.  
\* \*\*Precondiciones:\*\* Disponer de acceso al módulo de eventos y permisos para crear eventos.  
\* \*\*Pasos para reproducir:\*\*  
  1\. Acceder al módulo de eventos.  
  2\. Seleccionar la opción para crear un evento.  
  3\. Introducir una fecha de inicio.  
  4\. Introducir una fecha de finalización anterior a la fecha de inicio.  
  5\. Intentar guardar el evento.  
\* \*\*Resultado esperado:\*\* El sistema impide guardar el evento y muestra un mensaje indicando que la fecha de finalización debe ser igual o posterior a la fecha de inicio.  
\* \*\*Resultado obtenido:\*\* El sistema permite crear un evento con fecha de finalización anterior a la de inicio.  
\* \*\*Evidencia:\*\* \`\[Agregar captura en evidencias/H-10.png\]\`  
\* \*\*Recomendación:\*\* Implementar una validación que compare ambas fechas antes de guardar el evento y aplicar la misma regla en el backend.

\---

\#\# H-11 — Creación de tutorías en fechas pasadas (M)

\* \*\*Categoría:\*\* Validación de datos / gestión de tutorías.  
\* \*\*Severidad sugerida:\*\* Media.  
\* \*\*Descripción:\*\* El sistema permite crear tutorías con fechas anteriores a la fecha actual.  
\* \*\*Precondiciones:\*\* Disponer de acceso al módulo de tutorías y permisos para crear tutorías.  
\* \*\*Pasos para reproducir:\*\*  
  1\. Acceder al módulo de tutorías.  
  2\. Seleccionar la opción para crear una tutoría.  
  3\. Completar los campos obligatorios.  
  4\. Seleccionar una fecha pasada.  
  5\. Guardar la tutoría.  
\* \*\*Resultado esperado:\*\* El sistema valida la fecha seleccionada conforme a las reglas de programación y rechaza fechas pasadas si solo se permiten tutorías futuras.  
\* \*\*Resultado obtenido:\*\* El sistema permite crear tutorías en fechas pasadas.  
\* \*\*Evidencia:\*\* \`\[Agregar captura en evidencias/H-11.png\]\`  
\* \*\*Recomendación:\*\* Definir si se permiten tutorías históricas y, si no están permitidas, implementar una validación de fechas en la interfaz y en el backend.

\#\# 5\. Matriz consolidada

| ID | Categoría | Hallazgo o prueba | Severidad | Estado | Evidencia |  
|---|---|---|---|---|---|  
| H-01 | Funcionalidad | Imposibilidad de aprobar una reserva desde el usuario administrador | Alta | Pendiente de verificar | \[H-01\](\#h-01--imposibilidad-de-aprobar-una-reserva-desde-el-usuario-administrador-a) |  
| H-02 | Validación de datos | Creación de una reserva con 300 proyectores | Alta | Pendiente de verificar | \[H-02\](\#h-02--creación-de-una-reserva-con-300-proyectores-b) |  
| H-03 | Funcionalidad | Chatbot no funcional | Media | Pendiente de verificar | \[H-03\](\#h-03--chatbot-no-funcional-m) |  
| H-04 | Funcionalidad | Búsqueda mediante inteligencia artificial no funcional | Media | Pendiente de verificar | \[H-04\](\#h-04--búsqueda-mediante-inteligencia-artificial-no-funcional-m) |  
| H-05 | Funcionalidad | Error al seleccionar un espacio al crear un elemento de inventario | Media | Pendiente de verificar | \[H-05\](\#h-05--error-al-seleccionar-un-espacio-al-crear-un-elemento-de-inventario-b) |  
| H-06 | Validación de datos | Creación de un elemento de inventario con mantenimiento en una fecha pasada | Media | Pendiente de verificar | \[H-06\](\#h-06--creación-de-un-elemento-de-inventario-con-mantenimiento-en-una-fecha-pasada-b) |  
| H-07 | Validación de datos | Creación de espacios sin límite de capacidad | Media | Pendiente de verificar | \[H-07\](\#h-07--creación-de-espacios-sin-límite-de-capacidad-b) |  
| H-08 | Interfaz de usuario | El formulario de creación de espacios conserva los datos anteriores | Media | Pendiente de verificar | \[H-08\](\#h-08--el-formulario-de-creación-de-espacios-conserva-los-datos-anteriores-b) |  
| H-09 | Validación de datos | Creación de un evento con fecha de finalización en el pasado | Media | Pendiente de verificar | \[H-09\](\#h-09--creación-de-un-evento-con-fecha-de-finalización-en-el-pasado-m) |  
| H-10 | Validación de datos | Creación de un evento con fecha de finalización anterior a la de inicio | Alta | Pendiente de verificar | \[H-10\](\#h-10--creación-de-un-evento-con-fecha-de-finalización-anterior-a-la-de-inicio-m) |  
| H-11 | Validación de datos | Creación de tutorías en fechas pasadas | Media | Pendiente de verificar | \[H-11\](\#h-11--creación-de-tutorías-en-fechas-pasadas-m) |

\#\# 6\. Escenarios técnicos ejecutados

| Escenario | Resultado esperado | Resultado obtenido | Evidencia |  
|---|---|---|---|  
| Aprobar una reserva con usuario administrador | La reserva se aprueba y cambia de estado | No fue posible aprobar la reserva desde el usuario administrador. \*\*Severidad: Alta\*\* | \[Archivo\] |  
| Crear una reserva con 300 proyectores | El sistema rechaza la reserva por superar la disponibilidad o el límite permitido | El sistema permitió crear la reserva con 300 proyectores. \*\*Severidad: Baja\*\* | \[Archivo\] |  
| Usar el chatbot | El chatbot responde las consultas del usuario | El chatbot no funciona. \*\*Severidad: Media\*\* | \[Archivo\] |  
| Usar la búsqueda con IA | La búsqueda devuelve resultados relevantes | La búsqueda con IA no funciona. \*\*Severidad: Media\*\* | \[Archivo\] |  
| Crear un ítem de inventario y seleccionar un espacio | Solo se pueden elegir espacios válidos, y se exige asignar uno antes de guardar | Aparece la opción "sin asignar" y al guardar el sistema devuelve un error. \*\*Severidad: Baja\*\* | \[Archivo\] |  
| Crear un ítem con fecha de próximo mantenimiento en el pasado | El sistema rechaza la fecha con un mensaje de validación | El sistema permitió crear el ítem con la fecha de mantenimiento en el pasado. \*\*Severidad: Baja\*\* | \[Archivo\] |  
| Crear un espacio sin límite de capacidad | El campo de capacidad tiene un límite máximo validado | El formulario no impone ningún límite de capacidad. \*\*Severidad: Baja\*\* | \[Archivo\] |  
| Crear un espacio y luego abrir de nuevo el formulario de creación | El formulario aparece vacío | El formulario conserva los datos del espacio anterior y no se limpia. \*\*Severidad: Baja\*\* | \[Archivo\] |  
| Crear un evento con fecha de fin en el pasado | El sistema rechaza la fecha con un mensaje claro | El sistema permitió crear el evento con fecha de fin pasada. \*\*Severidad: Media\*\* | \[Archivo\] |  
| Crear un evento con fecha de fin anterior a la de inicio | El sistema rechaza el evento porque el fin debe ser posterior al inicio | El sistema permitió crear el evento con fecha de fin anterior al inicio. \*\*Severidad: Media\*\* | \[Archivo\] |  
| Crear una tutoría en una fecha pasada | El sistema rechaza fechas anteriores a la actual | El sistema permitió crear la tutoría en una fecha pasada. \*\*Severidad: Media\*\* | \[Archivo\] |

\#\# 7\. Recomendaciones priorizadas

1\. \*\*\[Prioridad alta\]\*\* Aclarar permisos vinculados a cada perfil, Equipo de Desarrollo, Mostrar en algún apartado las secciones y funcionalidades a las que puede acceder cada perfíl.  
2\. \*\*\[Prioridad media\]\*\* Tutorial o Tour durante el primer ingreso de un usuario, Equipo de Desarrollo, Durante primer ingreso de cada usuario a la plataforma mostrar un guía general de las secciones de la web.  
3\.  \*\*\[Prioridad baja\]\*\* Poder clickear celda para crear evento en esa fecha y hora, Equipo de Desarrollo, Al clickear celda se abre el formulario con la fecha clickeada ya seleccionada.

\#\# 8\. Validación con el equipo auditado

| Hallazgo | ¿Se pudo reproducir? | Respuesta del equipo | Acción acordada |  
|---|---|---|---|  
| H-01 | \[Sí / No\] | \[Comentario del equipo\] | \[Acción\] |  
| H-02 | \[Sí / No\] | \[Comentario del equipo\] | \[Acción\] |  
| H-03 | \[Sí / No / No aplica\] | \[Comentario del equipo\] | \[Acción\] |  
| H-04 | \[Sí / No / No aplica\] | \[Comentario del equipo\] | \[Acción\] |  
| H-05 | \[Sí / No\] | \[Comentario del equipo\] | \[Acción\] |  
| H-06 | \[Sí / No\] | \[Comentario del equipo\] | \[Acción\] |  
| H-07 | \[Sí / No\] | \[Comentario del equipo\] | \[Acción\] |  
| H-08 | \[Sí / No\] | \[Comentario del equipo\] | \[Acción\] |  
| H-09 | \[Sí / No\] | \[Comentario del equipo\] | \[Acción\] |  
| H-10 | \[Sí / No\] | \[Comentario del equipo\] | \[Acción\] |  
| H-11 | \[Sí / No\] | \[Comentario del equipo\] | \[Acción\] |  
