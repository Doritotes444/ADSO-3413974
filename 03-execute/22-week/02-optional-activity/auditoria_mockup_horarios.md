# Análisis de Brechas y Necesidades del Sistema — Mockup de Gestión de Horarios SENA

El presente análisis examina las **53 pantallas y modales** del sistema, distribuidas en siete módulos: Autenticación/Shell, Coordinador, Instructor, Aprendiz, Administrador, Back-office y Parametrización. El objetivo no es únicamente describir lo que falta visualmente en el prototipo, sino identificar situaciones reales que el sistema debería poder manejar, problemas que podrían surgir durante su operación y aspectos técnicos que afectarían su funcionamiento en un entorno institucional real.

---

## 1. Lógica de Negocio y Validación de Horarios

- **Detección tardía de conflictos:** El sistema cuenta con una pantalla para ver conflictos (13) y otra para resolverlos (14), pero el problema se detecta *después* de que el Coordinador ya realizó la asignación. Lo correcto sería que, al crear o editar un horario (10, 11), el sistema verifique automáticamente si el instructor, el ambiente, la ficha y la franja horaria están disponibles antes de confirmar la operación. Así se evitan los conflictos en lugar de acumularlos para resolverlos después.

- **Asignaciones simultáneas sin control:** Si dos Coordinadores intentan asignar el mismo instructor o ambiente a fichas distintas exactamente al mismo tiempo, el sistema no tiene ningún mecanismo para decidir cuál de las dos operaciones debe prevalecer. Esto podría generar una programación inválida sin que ninguno de los dos lo note. El sistema debería controlar estas situaciones para garantizar que el resultado final siempre sea coherente.

- **Validación incompleta del instructor al asignar:** Antes de confirmar que un instructor puede dictar una sesión, el sistema debería verificar más que su existencia en la base de datos. Es necesario revisar su jornada laboral, los horarios que ya tiene asignados, si es docente de planta o contratista y cuántas horas legales puede trabajar. Sin estas verificaciones, el sistema puede asignar más horas de las que corresponden, lo que genera problemas contractuales para la institución.

- **Falta de control sobre la carga horaria:** El sistema no muestra cuántas horas semanales lleva asignadas cada instructor mientras se construye la programación. Contar con esta información en tiempo real permitiría al Coordinador detectar desequilibrios y distribuir mejor la carga de formación antes de publicar el horario.

- **Sin modo de simulación antes de publicar:** El Coordinador no puede realizar ajustes de forma provisional para ver cómo afectan al resto de la programación antes de confirmarlos. Si cualquier cambio se aplica directamente al horario oficial, el riesgo de cometer errores con consecuencias inmediatas sobre instructores y aprendices es mucho mayor.

- **Sin historial de versiones del horario:** Cuando se realizan cambios importantes en la programación, el sistema no guarda un registro de cómo estaba configurado anteriormente. Poder consultar versiones previas y, si es necesario, recuperar una configuración anterior sería fundamental para corregir errores sin tener que reconstruir todo desde cero.

---

## 2. Gestión de Novedades y Flujos de Aprobación

- **El flujo de novedades del instructor queda incompleto:** El sistema permite al instructor registrar una excepción o novedad (pantalla 22), pero no hay un proceso definido que lleve esa solicitud al Coordinador para que la apruebe o rechace, ni se establece qué debe ocurrir con las sesiones afectadas: si se reasignan, se suspenden o se reprograman. Sin este flujo, la novedad queda registrada pero sin consecuencias reales dentro del sistema.

- **Búsqueda manual de alternativas para reprogramar:** Cuando una sesión no puede realizarse, el Coordinador debe buscar manualmente otra franja disponible, revisando por separado la disponibilidad del instructor, el ambiente, la ficha y la jornada. El sistema debería facilitar esta tarea ofreciendo opciones de reprogramación que ya cumplan todas las condiciones al mismo tiempo, reduciendo el tiempo de respuesta y evitando nuevos conflictos.

- **Los cambios entre roles no quedan relacionados en el sistema:** Cuando un instructor registra una novedad, el Coordinador toma una decisión y los aprendices se ven afectados, cada una de estas acciones debería estar vinculada dentro del sistema. Si la comunicación entre roles depende de medios externos —correos, llamadas o mensajes— no queda registro de por qué se realizó un cambio ni quién tomó la decisión.

---

## 3. Gestión de Ambientes y Recursos Físicos

- **No se verifica si el ambiente es adecuado para la formación:** Al asignar un ambiente a una sesión, el sistema no comprueba si ese espacio cumple las condiciones que requiere el programa: capacidad, tipo de espacio, equipos disponibles o software necesario. La pantalla de *Tipos de ambiente e inventario* (49) y la de *Detalle de ambiente* (16) registran esta información, pero no está vinculada al proceso de asignación. Esto puede llevar a asignar un taller de mecánica para una clase que requiere computadores, por ejemplo.

- **No se verifica el aforo antes de asignar:** Si una ficha tiene 30 aprendices y el ambiente tiene capacidad para 20, el sistema no debería permitir esa asignación sin advertirlo antes. Esta verificación automática evitaría problemas de espacio que actualmente deben detectarse de manera manual.

- **Los estados del ambiente son demasiado simples:** En la práctica, un ambiente no solo está disponible u ocupado. Puede estar en mantenimiento, tener una reserva especial, estar temporalmente bloqueado o fuera de servicio. El sistema debería reflejar estos estados e impedir automáticamente la asignación cuando corresponda.

---

## 4. Experiencia del Aprendiz y Transparencia Operativa

- **No hay registro de asistencia dentro del sistema:** Las vistas del aprendiz muestran el horario programado (*Mi horario — semana* [25] y *Detalle de clase* [27]), pero no incluyen ningún mecanismo para registrar la asistencia a cada sesión. Integrar este control directamente —mediante un código QR u otro método digital— evitaría que la asistencia se maneje de forma separada e independiente al sistema de horarios.

- **Las notificaciones no explican qué cambió:** Las pantallas de notificaciones (26 y 28) informan al aprendiz que hubo un cambio, pero no detallan qué se modificó exactamente, cuándo ocurrió ni cómo estaba antes. Para que el aprendiz pueda tomar decisiones —como reorganizar su jornada— necesita entender el alcance del cambio, no solo saber que existió.

- **El aprendiz no puede reportar inconvenientes dentro del sistema:** Si un aprendiz detecta un cruce en su horario o que no tiene ambiente asignado para una sesión, no tiene ninguna opción dentro del sistema para informarlo. Depender de canales externos aumenta el tiempo que tarda en resolverse un problema que afecta directamente su proceso de formación.

---

## 5. Seguridad, Autenticación y Control de Acceso

- **Los permisos solo se controlan en la interfaz, no en el servidor:** El sistema gestiona los roles y accesos desde la interfaz — usando módulos de rol (pantalla 4), estados globales (5) y controles de ruta —, pero estas restricciones solo existen en el navegador. Un usuario malintencionado podría modificar parámetros de la página o interceptar la comunicación con el servidor para ejecutar acciones que la interfaz no le permite. Para que la seguridad sea real, cada solicitud que llegue al servidor debe ser validada de forma independiente, sin importar lo que la interfaz muestre o bloquee.

- **No hay una política clara sobre el tiempo de vida de las sesiones:** El sistema debería definir cuánto tiempo puede durar una sesión activa antes de cerrarse automáticamente, especialmente para perfiles con permisos elevados. También debería ser posible cerrar sesiones abiertas en otros dispositivos y revocar el acceso de forma inmediata si se detecta una situación sospechosa.

- **Falta verificación adicional para acciones de alto impacto:** Los roles que pueden modificar la configuración general del sistema o publicar horarios oficiales —Administrador, Back-office y Parametrización— deberían confirmar su identidad con un paso adicional antes de ejecutar estas acciones. Esto se conoce como verificación en dos pasos o autenticación multifactor (MFA), y reduce significativamente el riesgo de cambios no autorizados.

- **Los módulos independientes no están suficientemente aislados entre sí:** El sistema está construido con módulos separados que funcionan de forma independiente dentro de una misma aplicación. Si estos módulos no tienen sus datos y sesiones correctamente aislados, un usuario con rol de aprendiz podría llegar a acceder, de forma indirecta, a información que pertenece al módulo del Coordinador o del Instructor dentro de la misma sesión del navegador.

---

## 6. Auditoría y Trazabilidad de Operaciones

- **El registro de auditoría actual es insuficiente:** El sistema cuenta con una pantalla de auditoría (39) y un modal de detalle (44), pero un registro convencional que guarda cambios en la base de datos puede ser modificado o eliminado por usuarios con privilegios elevados. Para que este historial tenga validez ante entes de control externos —como la Contraloría o una auditoría institucional— los registros deben ser inmutables, es decir, que una vez guardados no puedan alterarse ni eliminarse. Esto se complementa con mecanismos de verificación que certifican que el historial no fue manipulado.

- **Los registros no incluyen suficiente información sobre cada cambio:** Cada modificación registrada debería incluir quién la realizó, cuál era el estado anterior, cuál es el nuevo estado, en qué momento exacto ocurrió, desde qué módulo se ejecutó y, si el usuario lo indicó, el motivo del cambio. Un registro que solo guarda el valor final de un campo no permite entender qué ocurrió ni reconstruir la secuencia de decisiones.

- **No queda constancia de quién autorizó la publicación del horario:** Publicar la versión oficial de un horario tiene consecuencias directas sobre los contratos y las jornadas de los instructores. El sistema debería requerir que el responsable confirme su identidad antes de publicar, dejando constancia formal de quién autorizó esa versión. Sin este paso, no existe evidencia de responsabilidad ante una eventual reclamación.

- **El historial de auditoría no permite búsquedas específicas:** Para que el módulo de auditoría sea útil en la práctica, los responsables deben poder filtrar los registros por usuario, fecha, módulo, tipo de operación o elemento modificado. Sin estas opciones, el historial se convierte en un listado extenso que resulta imposible de consultar de manera eficiente.

---

## 7. Rendimiento, Escalabilidad y Disponibilidad

- **Las grillas de horarios pueden volverse lentas con muchos datos:** Mostrar la programación completa de un centro de formación implica visualizar simultáneamente cientos de celdas para instructores, fichas, ambientes y franjas horarias. Si el sistema intenta cargar toda esta información de una sola vez, el navegador puede volverse lento o dejar de responder, especialmente en computadores de uso institucional. Una solución es cargar únicamente la información visible en pantalla en cada momento, e ir completando el resto a medida que el usuario navega.

- **El sistema no funciona sin conexión a internet:** Instructores y aprendices consultan sus horarios en zonas del centro donde la conexión puede ser intermitente. El sistema actual requiere que el servidor esté disponible permanentemente para mostrar cualquier dato. Lo adecuado sería que el sistema guardara localmente las consultas más importantes en el dispositivo, de forma que puedan consultarse sin conexión, y sincronizara los cambios pendientes una vez esta se restablezca.

- **Un fallo en un módulo puede afectar todo el sistema:** Como el sistema está construido con módulos independientes que cargan desde una aplicación principal, si uno de ellos falla —por ejemplo, el módulo de ambientes—, puede impedir que el usuario acceda a los demás aunque funcionen correctamente. El sistema debería estar diseñado para que un fallo puntual no colapse toda la experiencia: los módulos que siguen activos deberían permanecer disponibles con las funciones que les correspondan.

- **No se confirma si los cambios fueron guardados correctamente:** Cuando un usuario crea o modifica un horario y la conexión se interrumpe en ese momento, el sistema no informa si la operación fue guardada o no. Esto puede llevar a creer que un cambio fue aplicado cuando en realidad se perdió. El sistema debería siempre confirmar explícitamente si la operación fue exitosa o advertir con claridad cuando no lo fue.

---

## 8. Reportes, Indicadores y Continuidad Operativa

- **No hay reportes sobre el uso de los recursos:** El sistema debería ofrecer informes que permitan saber qué ambientes se están usando más, qué franjas tienen mayor demanda, qué instructores tienen más horas asignadas de las que corresponden y qué fichas tienen la programación incompleta. Esta información es necesaria para la toma de decisiones administrativas y no debería depender de exportar datos a otra herramienta para analizarlos.

- **No se identifican patrones de conflicto:** El sistema resuelve conflictos de forma individual, pero no analiza si un mismo ambiente o franja horaria genera problemas de manera repetida. Detectar estos patrones permitiría al Coordinador tomar decisiones estructurales —como redistribuir el uso de un ambiente— en lugar de resolver el mismo problema continuamente.

- **No es posible exportar la información:** Los responsables administrativos deberían poder descargar reportes de horarios, asignaciones, cambios realizados y registros de auditoría en formatos que puedan usarse en otros procesos internos del centro, como informes de gestión o documentación de seguimiento.

- **No hay copias de seguridad automáticas:** Si ocurre un fallo grave mientras se está modificando la programación, no existe un mecanismo para recuperar el estado anterior del horario sin reconstruirlo manualmente. El sistema debería generar copias de seguridad periódicas y ofrecer la posibilidad de restaurar una versión anterior en caso de emergencia.

---

## Clasificación General de Brechas

| Categoría | Principales brechas identificadas |
|---|---|
| **Lógica de negocio** | Validación preventiva, asignaciones simultáneas, carga horaria, modo borrador y versionado |
| **Flujos operativos** | Novedades de instructores, reprogramación asistida y comunicación entre roles |
| **Recursos físicos** | Compatibilidad formación-ambiente, control de aforo y estados del ambiente |
| **Experiencia del aprendiz** | Asistencia integrada, notificaciones con contexto y reporte de inconsistencias |
| **Seguridad** | Permisos en el servidor, ciclo de sesiones, verificación en dos pasos y aislamiento de módulos |
| **Auditoría** | Registros inmutables, trazabilidad completa, firma en publicación oficial y búsqueda avanzada |
| **Rendimiento y disponibilidad** | Carga progresiva de datos, funcionamiento sin conexión y tolerancia a fallos |
| **Gestión administrativa** | Reportes de uso, patrones de conflicto, exportación y copias de seguridad |
