# REPORTE DE AUDITORÍA, REORGANIZACIÓN Y TRAZABILIDAD — ADSO 3413974

- **Repositorio:** `https://github.com/Doritotes444/ADSO-3413974`
- **Programa:** Tecnólogo en Análisis y Desarrollo de Software (ADSO) — Código `228106`
- **Ficha:** `3413974`
- **Aprendiz:** Juan Pablo Doria Caviedes (`@Doritotes444`)
- **Directorio Principal Auditado:** `03-execute/`
- **Fuente de Verdad del Cronograma:** [`03-execute/Cronograma weeks.md`](./03-execute/Cronograma%20weeks.md)
- **Rama de Trabajo:** `auditoria-reorganizacion-adso` (creada desde `main` en el commit base `b625a92`)
- **Fecha de Auditoría:** `2026-11-21`

---

## A. Diagnóstico Inicial

Antes de la intervención, el repositorio presentaba la siguiente situación estructural y documental:

1. **Fragmentación entre la raíz y `03-execute/`:**
   - En la raíz del repositorio existían las carpetas sueltas `02-week/`, `03-week/`, `04-week/`, `05-week/` y `06-week/`.
   - El análisis forense del historial de Git demostró que en el commit `6710d6f` (`2026-03-28`), el instructor migró las semanas `03-week` a `06-week` hacia `03-execute/`. Sin embargo, copias residuales de esas carpetas permanecieron en la raíz y `02-week/` nunca fue trasladada dentro de `03-execute/`.
   - Dentro de `03-execute/` faltaban las carpetas `01-week/` y `02-week/`, comenzando la numeración en `03-week/` hasta `40-week/`.
2. **Inconsistencia en subcarpetas de sesión (`03-week` a `10-week`):**
   - Mientras que `03-week` y `11-week` a `40-week` poseían la jerarquía `01-session/01-activity/.gitkeep`, las semanas `04-week` a `10-week` solo tenían `01-session/.gitkeep`.
3. **Múltiples versiones del Cronograma:**
   - [`03-execute/Cronograma weeks.md`](./03-execute/Cronograma%20weeks.md): versión oficial y más completa (41 líneas, abarca desde `Week 2` hasta `Week 27` con fecha `21-11-2026`).
   - [`03-execute/10-week/02-optional-activity/Cronograma weeks.md`](./03-execute/10-week/02-optional-activity/Cronograma%20weeks.md): entregable histórico de la actividad de la Semana 10 (abarca de `Week 2` a `Week 9`).
   - `03-execute/17-week/02-optional-activity/Cronograma`: borrador sin extensión creado el `11/07/2026` (abarca hasta `Week 17` y deja `Week 18:` en blanco), ajeno a los entregables de asistencia de la Semana 17.
4. **Desalineación de actividades entre semanas:**
   - **Semana 05 vs. Semana 06:** El archivo `Presentación - Instrumentos de Recolección (1).pdf` estaba duplicado en `05-week` y `06-week`, cuando el cronograma asigna *Mapa de procesos* a la Semana 05 e *Instrumentos de recolección* a la Semana 06.
   - **Semana 09 vs. Semana 10:** El archivo `Reporte_Ejecutivo_LaEsquina_ES (1) (1).md` (resumen ejecutivo directo de `Lab_Analisis_v3.xlsx` del Supermercado "La Esquina") estaba ubicado en `10-week` en lugar de `09-week` (*Actividad supermercado*).
   - **Semana 21 vs. Semana 22 vs. Semana 23:**
     - El cronograma establece para la **Semana 22**: *"Subir todos los BPMN y archivos asociados a la tarea dejada"*. Sin embargo, los 12 archivos `.bpmn` (organizados por rol: `aprendiz`, `coordinador`, `director`, `instructor`, `soporte`) junto con `ER.pdf` y `MODELO_DATOS_LOGICO_GLOBAL.md` habían sido cargados en `23-week`.
     - Por su parte, el cronograma establece para la **Semana 23**: *"se realizo estrategia de pensamiento de conocimientos, ingieneria inversa, plan de contingencia y de gestion de horarios"*, cuyos entregables (`Auditoría Integral de Brechas • SENA (50 Slides).pdf` y `auditoria_mockup_horarios.md`) estaban alojados en `22-week` (y duplicados en `21-week`).
5. **Proliferación de duplicados exactos y sufijos de descarga `(1)`, `(1) (1)`, `(2)`:**
   - 10 grupos de archivos con hash SHA-256 idéntico repartidos entre la raíz y `03-execute/`.
   - Más de 18 archivos con nombres contaminados por sufijos automáticos del navegador (`(1)`, `(1) (1)`, `(2)`), dobles puntos (`README..md`, `CALIDAD..docx`), espacios antes de la extensión (`Design thinking .pdf`), errores tipográficos (`invcersa`) o ausencia de extensión (`Asistencia`).

---

## B. Cronograma Interpretado (Fuente de Verdad)

A partir de [`03-execute/Cronograma weeks.md`](./03-execute/Cronograma%20weeks.md) (complementado con las fechas reales de ejecución del historial de Git y encabezados de los documentos), se identifican las siguientes semanas y requisitos:

| Semana | Fecha Referencia | Actividad Oficial en Cronograma | Evidencias / Entregables Exigidos |
| :---: | :---: | :--- | :--- |
| **Week 01** | 14/02/2026 | Inducción y estructuración inicial del proyecto ADSO | Evidencias de inducción (19 actividades en `02-training-project/.../01-induction/`) |
| **Week 02** | 21/02/2026 | Video de desarrollar la estructura de datos y la interfaz de usuario del software | Video subido a YouTube / documento con enlace |
| **Week 03** | 07/03/2026 | Manual GitHub | Documento/manual sobre cómo utilizar GitHub y sus comandos |
| **Week 04** | 14/03/2026 | Lista de chequeo | Análisis de requisitos del sistema y cuestionario/observación de supermercado (trabajo en equipos) |
| **Week 05** | 21/03/2026 | Mapa de procesos | Infografía/presentación sobre qué son los mapas de procesos y video explicativo |
| **Week 06** | 28/03/2026 | Instrumentos de recolección | Infografía/presentación sobre instrumentos de recolección y asimilación al proyecto (*TiendApp*) |
| **Week 07** | 25/04/2026 | ¿Qué es SRS? | Tarea e infografía con información sobre Especificación de Requisitos de Software (SRS) |
| **Week 08** | Abr 2026 | Instrumentos de recolección con nuestro proyecto | Instrumentos aplicados/asimilados al proyecto formativo (*TiendApp*: encuesta y guion de entrevista) |
| **Week 09** | Abr 2026 | Actividad supermercado | Laboratorio de análisis cualitativo, cuantitativo (Excel) y reporte ejecutivo del Supermercado *"La Esquina"* |
| **Week 10** | May 2026 | Cronograma | Registro del cronograma semanal (encargados mencionados: Kevin Eduardo y Brenda Galeano) |
| **Week 11** | 09/05/2026 | Actividad SRS Supermercado | Documento SRS Supermercado *"La Esquina"* y material/video de apoyo para exposición de 3 minutos |
| **Week 12** | 16/05/2026 | ¿Qué son las TIC? | Observación/evaluación de exposiciones de compañeros, talleres TIC y proyecto base en sesión |
| **Week 13** | May 2026 | Gestión Horario Instructores | Presentación PowerPoint (5 diapositivas), documento Word de resumen y mockup interactivo |
| **Week 14** | 22/06/2026 | Implementar documentos de gestión de horarios, adaptarlos a nuestro proyecto | Repositorio/arquitectura documental adaptada al proyecto (`.zip`), presentación (*Master Blueprint*) y enlace de video |
| **Week 15** | 06/06/2026 | Trabajo Diagramas UML, `.drawio` y Word | Diagramas UML (`.drawio.svg`: Casos de Uso, Clases, UML) y documentos Word de descripción y justificación |
| **Week 16** | 04/07/2026 | Trabajo UML, USE CASE, Diagrama USE CASE y Diagrama de Clases + Asistencia SENA | Diagrama de Casos de Uso, Diagrama de Clases, especificación y Mockup de Asistencia a clase SENA |
| **Week 17** | 11/07/2026 | Mockup de Asistencia SENA (dejado 04/07/2026, entrega 11/07/2026) | Idea replanteada y mejorada de llamado de asistencia (requisitos y hoja de ruta), mockup definitivo y presentación |
| **Week 18** | 25/07/2026 | Proyecto de Asistencia de ambiente e ingeniería inversa | `.zip` del proyecto de Asistencia de ambiente + identificación del software, nuevas funciones e ingeniería inversa / Design Thinking |
| **Week 19** | Jul 2026 | Socialización de los MVP | Actividad presencial de socialización de MVPs en clase (quedaron pendientes algunos equipos) |
| **Week 20** | 01/08/2026 | Ejercicio en clase dividido en 2 grupos (1: Aeropuerto / 2: Clínica Veterinaria) | Evidencias desarrolladas en clase (Design Thinking, MoSCoW y diagrama E-R del PRD de venta y control de tiquetes aéreos) |
| **Week 21** | 08/08/2026 | Realizar MER asignados por Jesús Ariel + Ingeniería inversa a mockup de horarios | Diagramas MER y tablas Excel de los ejercicios + archivo `.md` de ingeniería inversa a `design-software-mockup` |
| **Week 22** | Ago 2026 | Subir todos los BPMN y archivos asociados a la tarea dejada | 12 modelos BPMN por rol (`aprendiz`, `coordinador`, `director`, `instructor`, `soporte`) + `ER.pdf` + `MODELO_DATOS_LOGICO_GLOBAL.md` |
| **Week 23** | Ago 2026 | Estrategia de pensamiento de conocimientos, ingeniería inversa, plan de contingencia y gestión de horarios | Presentación ejecutiva de 50 diapositivas (incluye plan de acción, contingencia/DRP y gestión de horarios) + informe de auditoría |
| **Week 24** | 12/09/2026 | Trabajo de gobernanza y realización de proyecto de Taller de Mecánica (dejado el 12 de septiembre) | Enlaces/archivos del proyecto de Taller de Mecánica Automotriz y repositorio de gobernanza |
| **Week 25** | 17/10/2026 | Subida de documentación generada sobre el trabajo entregado por el instructor (*Orderflow Engine*) | Documentación y evidencias de auditoría / preguntas de aclaración de alcance de *Orderflow Engine* |
| **Week 26** | 07/11/2026 | Escaneo de apuntes/resumen tomado de los proyectos evaluados y clase en general | Documento PDF con el escaneo de los apuntes manuscritos de evaluación de proyectos y criterios técnicos |
| **Week 27** | 21/11/2026 | Cargar archivos/diapositivas o trabajo realizado de acuerdo a E2E (*End-to-End*) | Archivos, diapositivas o trabajo sobre pruebas E2E (*End-to-End*) |
| **Weeks 28–40** | Por programar | Semanas futuras estructuradas en el repositorio | Pendientes de programación académica |

---

## C. Problemas Encontrados

### 1. Errores de Estructura y Clasificación
- **P-01:** La carpeta `02-week/` se encontraba en la raíz del repositorio en lugar de `03-execute/02-week/`.
- **P-02:** Las carpetas `03-week/`, `04-week/`, `05-week/` y `06-week/` existían duplicadas en la raíz del repositorio con copias idénticas de los archivos que ya estaban en `03-execute/03-week/` a `03-execute/06-week/`.
- **P-03:** No existían las carpetas `03-execute/01-week/` ni `03-execute/02-week/`.
- **P-04:** Las carpetas `03-execute/04-week/01-session/` a `03-execute/10-week/01-session/` carecían del subdirectorio estándar `01-activity/`.
- **P-05:** `Presentación - Instrumentos de Recolección (1).pdf` estaba ubicado en `05-week` (cuyo tema es *Mapa de procesos*) además de `06-week` (*Instrumentos de recolección*).
- **P-06:** `Reporte_Ejecutivo_LaEsquina_ES (1) (1).md` estaba ubicado en `10-week` (cuyo tema es *Cronograma*), cuando su contenido analiza directamente el archivo `Lab_Analisis_v3.xlsx` del Supermercado *"La Esquina"* de la `09-week`.
- **P-07:** En `17-week/02-optional-activity/` existía un archivo sin extensión llamado `Cronograma` con un borrador truncado hasta la Semana 17.
- **P-08:** Los entregables de la **Semana 22** (12 archivos `.bpmn`, `ER.pdf` y `MODELO_DATOS_LOGICO_GLOBAL.md`) estaban ubicados en `23-week`, mientras que los entregables de la **Semana 23** (`Auditoría Integral de Brechas • SENA (50 Slides).pdf` y `auditoria_mockup_horarios.md`, que incluyen el plan de acción, contingencia/recuperación ante desastres y gestión de horarios) estaban en `22-week`.

### 2. Duplicados Exactos Identificados (Verificados por Hash SHA-256)
Se detectaron **10 grupos de archivos duplicados bit a bit** (excluyendo `.gitkeep`):
1. **Hash `5e3059150f98` (4,351 bytes):**
   - `03-week/02-optional-activity/guia-git-terminal (1).md`
   - `03-execute/03-week/02-optional-activity/guia-git-terminal (1) (1).md`
2. **Hash `43a55cb31795` (21,095 bytes):**
   - `04-week/02-optional-activity/Guia_Observacion_Grupo4 (1).xlsx`
   - `03-execute/04-week/02-optional-activity/Guia_Observacion_Grupo4 (1) (1).xlsx`
3. **Hash `8b636db8ba91` (29,143 bytes):**
   - `04-week/02-optional-activity/informe_observacion_grupo4.docx`
   - `03-execute/04-week/02-optional-activity/informe_observacion_grupo4 (1).docx`
4. **Hash `228af2634bd6` (1,291,736 bytes — 4 copias idénticas):**
   - `05-week/02-optional-activity/Presentación - Instrumentos de Recolección (1).pdf`
   - `06-week/Presentación - Instrumentos de Recolección.pdf`
   - `03-execute/05-week/02-optional-activity/Presentación - Instrumentos de Recolección (1).pdf`
   - `03-execute/06-week/02-optional-activity/Presentación - Instrumentos de Recolección (1).pdf`
5. **Hash `412aea5fac0c` (2,486,057 bytes):**
   - `05-week/02-optional-activity/Presentación - Mapa de Procesos Organizacional.pdf`
   - `03-execute/05-week/02-optional-activity/Presentación - Mapa de Procesos Organizacional.pdf`
6. **Hash `fb60084be6b6` (29 bytes):**
   - `05-week/02-optional-activity/Video_mapadeprocesos.md`
   - `03-execute/05-week/02-optional-activity/Video_mapadeprocesos.md`
7. **Hash `079b1a07aad6` (31,610 bytes — duplicado en la misma carpeta `09-week`):**
   - `03-execute/09-week/02-optional-activity/Analisis_Cualitativo_v3.docx`
   - `03-execute/09-week/02-optional-activity/Analisis_Cualitativo_v3 (1).docx`
8. **Hash `beb2c7394f0d` (32,083 bytes — duplicado en la misma carpeta `09-week`):**
   - `03-execute/09-week/02-optional-activity/Lab_Analisis_v3.xlsx`
   - `03-execute/09-week/02-optional-activity/Lab_Analisis_v3 (1).xlsx`
9. **Hash `521e6c19ed32` (5,776,230 bytes):**
   - `03-execute/21-week/02-optional-activity/Auditoría Integral de Brechas • SENA (50 Slides) (1).pdf`
   - `03-execute/22-week/02-optional-activity/Auditoría Integral de Brechas • SENA (50 Slides).pdf`
10. **Hash `3757cd05910b` (15,562 bytes):**
    - `03-execute/21-week/02-optional-activity/ingenieria invcersa de Mockup de Gestión de Horarios SENA.md`
    - `03-execute/22-week/02-optional-activity/auditoria_mockup_horarios.md`
    *(Nota: este documento cumple doble rol como entregable `.md` de ingeniería inversa en la Semana 21 y como documento base de la exposición de 50 slides en la Semana 23, por lo que se conservó en ambas semanas con nombres normalizados).*

### 3. Problemas Técnicos y de Integridad en Archivos
- **P-09 (`sena_schedule_mockup.html` en Semana 13):** El archivo era un fragmento HTML incompleto (sin `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>` ni cierre `</html>`), utilizaba variables CSS (`--font-sans`, `--color-text-primary`, `--color-border-tertiary`, etc.) no declaradas en `:root` y clases de íconos Tabler (`ti ti-*`) sin cargar la hoja de estilos correspondiente.
- **P-10 (`INFORME_PRELIMINAR_AUDITORIA_ORDERFLOW.md` en Semana 25):** Contenía 7 enlaces Markdown con rutas locales absolutas de Windows (`file:///C:/Users/Aprendiz/...`) que resultaban en enlaces rotos fuera de la máquina local del estudiante.
- **P-11 (`comments-git.md` en Semana 03):** Error ortográfico en `"Carpeta que modifica el isntructor"`.
- **P-12 (`Asistencia` en Semana 18, `Video_mapadeprocesos.md` en Semana 05 y `repo.md` en Semana 24):** Archivos con URLs crudas sin estructura Markdown descriptiva (y `Asistencia` sin extensión `.md`).

---

## D. Correcciones Realizadas

1. **Protección con Git:** Se verificó el árbol limpio y se creó la rama de trabajo `auditoria-reorganizacion-adso` sin alterar `main`.
2. **Estandarización de `03-execute/`:**
   - Se crearon las estructuras estándar `03-execute/01-week/` y `03-execute/02-week/` con sus subdirectorios `01-session/01-activity/` y `02-optional-activity/`.
   - Se completó el subdirectorio `01-session/01-activity/.gitkeep` en las semanas `04-week` a `10-week` para que las 40 semanas de `03-execute/` tengan exactamente la misma estructura.
3. **Unificación de semanas dispersas en la raíz:**
   - Se trasladó `02-week/` desde la raíz hacia `03-execute/02-week/`.
   - Se eliminaron de la raíz las carpetas duplicadas `03-week/`, `04-week/`, `05-week/` y `06-week/` tras verificar por hash SHA-256 que sus archivos ya estaban presentes en `03-execute/`.
4. **Reubicación por correspondencia con el Cronograma:**
   - Se trasladó `Reporte_Ejecutivo_LaEsquina_ES.md` de `10-week` a `09-week` junto a los demás archivos del Supermercado *"La Esquina"*.
   - Se reubicaron los 12 diagramas `.bpmn`, `ER.pdf` y `MODELO_DATOS_LOGICO_GLOBAL.md` de `23-week` a `22-week` (*"Subir todos los BPMN y archivos asociados a la tarea dejada"*).
   - Se reubicaron `Auditoría Integral de Brechas • SENA (50 Slides).pdf` y `auditoria_mockup_horarios.md` a `23-week` (*"estrategia de pensamiento de conocimientos, ingieneria inversa, plan de contingencia y de gestion de horarios"*).
5. **Eliminación segura de duplicados exactos:**
   - Se eliminaron las copias redundantes con sufijo `(1)` dentro de `05-week`, `09-week` y `21-week`, así como el borrador truncado `17-week/02-optional-activity/Cronograma`.
6. **Normalización de nombres de archivos:**
   - Se limpiaron todos los sufijos `(1)`, `(1) (1)`, `(2)`, dobles puntos (`..`), espacios previos a la extensión y errores ortográficos en nombres de archivos.
7. **Corrección técnica de entregables:**
   - Se completó la estructura HTML5, variables `:root` y hoja de estilos de íconos en [`sena_schedule_mockup.html`](./03-execute/13-week/02-optional-activity/sena_schedule_mockup.html).
   - Se corrigieron los enlaces rotos `file:///C:/...` en [`INFORME_PRELIMINAR_AUDITORIA_ORDERFLOW.md`](./03-execute/25-week/02-optional-activity/INFORME_PRELIMINAR_AUDITORIA_ORDERFLOW.md).
   - Se formatearon en Markdown estructurado [`Video_mapadeprocesos.md`](./03-execute/05-week/02-optional-activity/Video_mapadeprocesos.md), [`Asistencia.md`](./03-execute/18-week/02-optional-activity/Asistencia.md) y [`repo.md`](./03-execute/24-week/02-optional-activity/repo.md).

---

## E. Archivos Trasladados y Renombrados (`git mv` / `git rm`)

| Ruta Anterior | Ruta Nueva / Acción | Motivo Técnico / Académico |
| :--- | :--- | :--- |
| `02-week/02-optional-activity/CONSTRUIR PROTOTIPO DE SOFTWARE SEGÚN ANÁLISIS FUNCIONAL Y REQUISITOS DE CALIDAD..docx` | `03-execute/02-week/02-optional-activity/CONSTRUIR PROTOTIPO DE SOFTWARE SEGÚN ANÁLISIS FUNCIONAL Y REQUISITOS DE CALIDAD.docx` | Reubicación de Semana 02 dentro de `03-execute/` y eliminación de doble punto `..docx` |
| `03-week/02-optional-activity/guia-git-terminal (1).md` | Eliminado (duplicado exacto en `03-execute/03-week/`) | Carpeta residual en raíz tras migración del commit `6710d6f` |
| `04-week/02-optional-activity/Guia_Observacion_Grupo4 (1).xlsx` | Eliminado (duplicado exacto en `03-execute/04-week/`) | Carpeta residual en raíz tras migración del commit `6710d6f` |
| `04-week/02-optional-activity/informe_observacion_grupo4.docx` | `03-execute/04-week/02-optional-activity/informe_observacion_grupo4.docx` | Unificación en `03-execute/04-week/` con nombre limpio sin `(1)` |
| `05-week/02-optional-activity/Presentación - Mapa de Procesos Organizacional.pdf` | Eliminado (duplicado exacto en `03-execute/05-week/`) | Carpeta residual en raíz |
| `05-week/02-optional-activity/Video_mapadeprocesos.md` | Eliminado (duplicado exacto en `03-execute/05-week/`) | Carpeta residual en raíz |
| `05-week/02-optional-activity/Presentación - Instrumentos de Recolección (1).pdf` | Eliminado (duplicado exacto de Semana 06) | Carpeta residual en raíz y actividad perteneciente a Semana 06 |
| `03-execute/05-week/02-optional-activity/Presentación - Instrumentos de Recolección (1).pdf` | Eliminado (conservado en `03-execute/06-week/`) | Corresponde a la Semana 06 (*Instrumentos de recolección*) |
| `06-week/Presentación - Instrumentos de Recolección.pdf` | `03-execute/06-week/02-optional-activity/Presentación - Instrumentos de Recolección.pdf` | Unificación en `03-execute/06-week/` con nombre limpio sin `(1)` |
| `03-execute/03-week/02-optional-activity/guia-git-terminal (1) (1).md` | `03-execute/03-week/02-optional-activity/guia-git-terminal.md` | Normalización de nombre (eliminación de `(1) (1)`) |
| `03-execute/04-week/02-optional-activity/Guia_Observacion_Grupo4 (1) (1).xlsx` | `03-execute/04-week/02-optional-activity/Guia_Observacion_Grupo4.xlsx` | Normalización de nombre (eliminación de `(1) (1)`) |
| `03-execute/06-week/02-optional-activity/TiendApp_Instrumentos_Fase1 (1).docx` | `03-execute/06-week/02-optional-activity/TiendApp_Instrumentos_Fase1.docx` | Normalización de nombre (eliminación de `(1)`) |
| `03-execute/08-week/02-optional-activity/TiendApp_Encuesta_Validacion (1) (1).docx` | `03-execute/08-week/02-optional-activity/TiendApp_Encuesta_Validacion.docx` | Normalización de nombre (eliminación de `(1) (1)`) |
| `03-execute/08-week/02-optional-activity/TiendApp_Guion_Entrevista_UX (1).docx` | `03-execute/08-week/02-optional-activity/TiendApp_Guion_Entrevista_UX.docx` | Normalización de nombre (eliminación de `(1)`) |
| `03-execute/09-week/02-optional-activity/Analisis_Cualitativo_v3 (1).docx` | Eliminado (duplicado exacto de `Analisis_Cualitativo_v3.docx`) | Duplicado bit a bit (`SHA-256: 079b1a07aad6`) en la misma carpeta |
| `03-execute/09-week/02-optional-activity/Lab_Analisis_v3 (1).xlsx` | Eliminado (duplicado exacto de `Lab_Analisis_v3.xlsx`) | Duplicado bit a bit (`SHA-256: beb2c7394f0d`) en la misma carpeta |
| `03-execute/10-week/02-optional-activity/Reporte_Ejecutivo_LaEsquina_ES (1) (1).md` | `03-execute/09-week/02-optional-activity/Reporte_Ejecutivo_LaEsquina_ES.md` | Reubicado a Semana 09 (*Actividad supermercado La Esquina*) y nombre normalizado |
| `03-execute/10-week/02-optional-activity/Cronograma weeks (1).md` | `03-execute/10-week/02-optional-activity/Cronograma weeks.md` | Normalización de nombre (entregable histórico de Semana 10) |
| `03-execute/13-week/02-optional-activity/SGH_Resumen_Simple (1).docx` | `03-execute/13-week/02-optional-activity/SGH_Resumen_Simple.docx` | Normalización de nombre (eliminación de `(1)`) |
| `03-execute/16-week/02-optional-activity/Mock Up (1).pdf` | `03-execute/16-week/02-optional-activity/Mock Up.pdf` | Normalización de nombre (eliminación de `(1)`) |
| `03-execute/17-week/02-optional-activity/Cronograma` | Eliminado (borrador incompleto hasta S17) | Reemplazado por la fuente de verdad `03-execute/Cronograma weeks.md` |
| `03-execute/17-week/02-optional-activity/control_asistencia_requisitos (1).txt` | `03-execute/17-week/02-optional-activity/control_asistencia_requisitos.txt` | Normalización de nombre (eliminación de `(1)`) |
| `03-execute/18-week/02-optional-activity/Análisis Design Thinking - Control de Asistencia SENA (1).pdf` | `03-execute/18-week/02-optional-activity/Análisis Design Thinking - Control de Asistencia SENA.pdf` | Normalización de nombre (eliminación de `(1)`) |
| `03-execute/18-week/02-optional-activity/design_thinking_asistencia (1).docx` | `03-execute/18-week/02-optional-activity/design_thinking_asistencia.docx` | Normalización de nombre (eliminación de `(1)`) |
| `03-execute/18-week/02-optional-activity/Asistencia` | `03-execute/18-week/02-optional-activity/Asistencia.md` | Adición de extensión `.md` y formato descriptivo |
| `03-execute/20-week/02-optional-activity/Design thinking .pdf` | `03-execute/20-week/02-optional-activity/Design thinking.pdf` | Eliminación de espacio en blanco antes de `.pdf` |
| `03-execute/20-week/02-optional-activity/entidad relación PRD — Venta y control de tiquetes aéreos.drawio (1).svg` | `03-execute/20-week/02-optional-activity/entidad relación PRD — Venta y control de tiquetes aéreos.drawio.svg` | Normalización de nombre (eliminación de `(1)`) |
| `03-execute/21-week/02-optional-activity/ingenieria invcersa de Mockup de Gestión de Horarios SENA.md` | `03-execute/21-week/02-optional-activity/ingenieria_inversa_Mockup_Gestion_Horarios_SENA.md` | Corrección ortográfica (`invcersa` -> `inversa`) y estandarización |
| `03-execute/21-week/02-optional-activity/Auditoría Integral de Brechas • SENA (50 Slides) (1).pdf` | Eliminado de S21 (conservado en `23-week`) | Duplicado exacto (`SHA-256: 521e6c19ed32`) |
| `03-execute/23-week/02-optional-activity/{aprendiz,coordinador,director,instructor,soporte}/*.bpmn` | `03-execute/22-week/02-optional-activity/{aprendiz,coordinador,director,instructor,soporte}/*.bpmn` | Reubicación de los 12 procesos BPMN a la Semana 22 según el cronograma |
| `03-execute/23-week/02-optional-activity/ER.pdf` | `03-execute/22-week/02-optional-activity/ER.pdf` | Reubicación del diagrama E-R asociado a los procesos BPMN a la Semana 22 |
| `03-execute/23-week/02-optional-activity/MODELO_DATOS_LOGICO_GLOBAL.md` | `03-execute/22-week/02-optional-activity/MODELO_DATOS_LOGICO_GLOBAL.md` | Reubicación del modelo lógico derivado de los 12 BPMN a la Semana 22 |
| `03-execute/22-week/02-optional-activity/Auditoría Integral de Brechas • SENA (50 Slides).pdf` | `03-execute/23-week/02-optional-activity/Auditoría Integral de Brechas • SENA (50 Slides).pdf` | Reubicación a Semana 23 (*ingeniería inversa, plan de contingencia y gestión de horarios*) |
| `03-execute/22-week/02-optional-activity/auditoria_mockup_horarios.md` | `03-execute/23-week/02-optional-activity/auditoria_mockup_horarios.md` | Reubicación a Semana 23 junto con la presentación de 50 diapositivas |
| `02-training-project/01-phase/README..md` | `02-training-project/01-phase/README.md` | Eliminación de doble punto `..md` |
| `02-training-project/.../TGS_Presentacion_OVA (1).html` | `02-training-project/.../TGS_Presentacion_OVA.html` | Normalización de nombre (eliminación de `(1)`) |
| `02-training-project/.../Guia_Aprendizaje_TIC/Sistema_Gestion_Biblioteca_UML (2).docx` | `02-training-project/.../Guia_Aprendizaje_TIC/Sistema_Gestion_Biblioteca_UML.docx` | Normalización de nombre (eliminación de `(2)`) |
| `02-training-project/.../Guia_Aprendizaje_TIC/TecnoMarket_ModeladoFuncional (2).docx` | `02-training-project/.../Guia_Aprendizaje_TIC/TecnoMarket_ModeladoFuncional.docx` | Normalización de nombre (eliminación de `(2)`) |

---

## F. Archivos Corregidos Técnicamente

| Archivo | Problema Encontrado | Solución Aplicada |
| :--- | :--- | :--- |
| [`03-execute/13-week/02-optional-activity/sena_schedule_mockup.html`](./03-execute/13-week/02-optional-activity/sena_schedule_mockup.html) | Fragmento HTML sin `<!DOCTYPE html>`, `<head>`, `<body>` ni cierre `</html>`; variables CSS `--font-sans`, `--color-text-*`, `--color-border-*` indefinidas; íconos Tabler (`ti-*`) sin stylesheet. | Se envolvió en un documento HTML5 completo y válido, se declararon las variables CSS en `:root` y se vinculó el CDN oficial de `@tabler/icons-webfont`. |
| [`03-execute/25-week/02-optional-activity/INFORME_PRELIMINAR_AUDITORIA_ORDERFLOW.md`](./03-execute/25-week/02-optional-activity/INFORME_PRELIMINAR_AUDITORIA_ORDERFLOW.md) | 7 hipervínculos apuntaban a rutas locales de Windows (`file:///C:/Users/Aprendiz/...`) inaccesibles en GitHub o en otros entornos. | Se transformaron las referencias locales en bloques de código en línea (`C:\Users\Aprendiz\...`), eliminando enlaces rotos sin alterar el contenido del informe. |
| [`03-execute/03-week/01-session/01-activity/comments-git.md`](./03-execute/03-week/01-session/01-activity/comments-git.md) | Error tipográfico en `"Carpeta que modifica el isntructor"`. | Se corrigió a `"Carpeta que modifica el instructor"`. |
| [`03-execute/05-week/02-optional-activity/Video_mapadeprocesos.md`](./03-execute/05-week/02-optional-activity/Video_mapadeprocesos.md) | Contenía únicamente una URL sin título ni contexto. | Se estructuró con encabezado Markdown conservando intacto el enlace `https://youtu.be/1CbaUaBcvUQ`. |
| [`03-execute/18-week/02-optional-activity/Asistencia.md`](./03-execute/18-week/02-optional-activity/Asistencia.md) | Archivo sin extensión con una sola línea URL. | Se renombró a `Asistencia.md` y se documentó el enlace de despliegue en Vercel (`https://ejemplo-sigma.vercel.app/`). |
| [`03-execute/24-week/02-optional-activity/repo.md`](./03-execute/24-week/02-optional-activity/repo.md) | Contenía dos URLs sueltas sin descripción. | Se añadieron títulos descriptivos para cada repositorio externo (`sistema-taller-automotriz` y `ejemplo`). |
| [`README.md`](./README.md) | Contenía únicamente la tarjeta de perfil básica sin descripción del programa, estructura ni tabla de semanas. | Se actualizó con la documentación completa en español, tabla de 40 semanas, enlaces relativos verificados y estado real de cada actividad, preservando el bloque `CONFIG` y perfil original. |

---

## G. Actividades Pendientes o Parciales según el Cronograma

1. **Semana 18 (`PARCIAL`):**
   - **Requisito del cronograma:** *"Se debe subir el .zip de el proyecto de Asistencia de ambiente el que era de tarea para presentar y el de identificar ya el software y ver que se puede anexar funciones nuevas en pocas palabras, Desing inversa."*
   - **Estado actual:** Están completos todos los entregables de ingeniería inversa, Design Thinking, inventario de casos de uso, matriz MoSCoW, presentación interactiva HTML y enlace a la app desplegada (`Asistencia.md`). Falta únicamente adjuntar el archivo `.zip` del proyecto de código fuente.
2. **Semana 24 (`PARCIAL`):**
   - **Requisito del cronograma:** *"Se debe subir trabajo de governanza y realizacion de proyecto de Taller de mecanica que dejo jesus ariel el 12 de septiembre."*
   - **Estado actual:** Existe el archivo [`repo.md`](./03-execute/24-week/02-optional-activity/repo.md) que apunta a los repositorios externos `https://github.com/Tomasberserk/sistema-taller-automotriz.git` y `https://github.com/Tomasberserk/ejemplo.git`. Si el instructor requiere que los archivos o el `.zip` de dichos repositorios estén alojados dentro de esta carpeta, deben agregarse.
3. **Semana 25 (`PARCIAL`):**
   - **Requisito del cronograma:** *"17-10-2026 se debe realizar la devida subida de documentacion generada el dia de hoy de acuerdo al trabajo entregado del instructor, todo archivo o evidencia generada que cuente como evidencia para esta semana"*.
   - **Estado actual:** Se cuenta con [`5_PREGUNTAS_ORDERFLOW_ENGINE.pdf`](./03-execute/25-week/02-optional-activity/5_PREGUNTAS_ORDERFLOW_ENGINE.pdf) y el [`INFORME_PRELIMINAR_AUDITORIA_ORDERFLOW.md`](./03-execute/25-week/02-optional-activity/INFORME_PRELIMINAR_AUDITORIA_ORDERFLOW.md) (donde se documenta el bloqueo de acceso a los repositorios de *Orderflow Engine* en la Fase 1). Queda pendiente cargar la auditoría completa cuando el material de *Orderflow Engine* esté disponible.
4. **Semana 27 (`PENDIENTE`):**
   - **Requisito del cronograma:** *"21-11-2026 Se debe cargar los archivos/diapositivas o trabajo que se halla realizado de acuerdo a lo E2E End-two-End."*
   - **Estado actual:** No se han subido archivos aún en [`03-execute/27-week/02-optional-activity/`](./03-execute/27-week/02-optional-activity/).
5. **Semanas 28 a 40 (`PENDIENTE`):**
   - Carpetas preparadas en el repositorio para futuras semanas académicas.

---

## H. Casos Ambiguos y Contradicciones Registradas

1. **Contradicción entre `00-planning/index.html` (`app.js`) y `03-execute/Cronograma weeks.md`:**
   - La landing page en `00-planning/` contiene un *roadmap* gamificado genérico de 18 semanas (Fundamentos, Requisitos, BD, POO, Spring Boot, React, Testing, Docker).
   - Por el contrario, `03-execute/Cronograma weeks.md` registra las actividades reales ejecutadas semana a semana por la ficha `3413974` (Semanas 02 a 27).
   - **Decisión aplicada:** Conforme a las reglas de auditoría, `03-execute/Cronograma weeks.md` prevalece como fuente de verdad para organizar `03-execute/`, mientras que `00-planning/` se conserva intacto como material de planeación curricular inicial del instructor.
2. **Semana 19 (`REQUIERE REVISIÓN`):**
   - El cronograma indica: *"Se realizo socializacion de los MVP los cuales quedaron pendientes algunos"*. Al tratarse de una actividad sincrónica de exposición en clase, la carpeta `19-week` no posee archivos. Requiere confirmación del aprendiz/instructor sobre si debe subirse algún acta o captura.
3. **Semana 20 (Ejercicio en 2 grupos — Aeropuerto vs. Clínica Veterinaria):**
   - El cronograma indica que el grupo se dividió en dos (Ejercicio 1: Aeropuerto; Ejercicio 2: Clínica Veterinaria). Los tres archivos presentes en `20-week` corresponden al **Ejercicio 1 (Aeropuerto — Venta y control de tiquetes aéreos)**, que fue el subgrupo asignado al aprendiz.
4. **Documento de Ingeniería Inversa / Auditoría de Brechas del Mockup de Horarios (Semanas 21 y 23):**
   - El archivo Markdown de análisis de las 53 pantallas y 31 brechas del mockup de horarios fue subido originalmente tanto en `21-week` (`ingenieria invcersa de Mockup de Gestión de Horarios SENA.md`) como en `22-week` (`auditoria_mockup_horarios.md`). Dado que la Semana 21 exige explícitamente *"hacer un .md de aquello"* y la Semana 23 aborda *"estrategia de pensamiento de conocimientos, ingieneria inversa, plan de contingencia y de gestion de horarios"* (junto con el PDF de 50 diapositivas), se conservó el archivo `.md` en `21-week` y junto a su presentación de 50 diapositivas en `23-week`.

---

## I. Matriz Completa de Seguimiento por Semana

| Semana | Fechas / Ref. | Actividades Programadas | Evidencias Exigidas | Archivos Encontrados | Ubicación Anterior | Ubicación Correcta Final | Estado Real |
| :---: | :---: | :--- | :--- | :--- | :--- | :--- | :---: |
| **01** | Feb 2026 | Inducción SENA | Evidencias de inducción | 19 evidencias de inducción | `02-training-project/.../01-induction/` | `02-training-project/.../01-induction/` y `03-execute/01-week/` | **COMPLETO** |
| **02** | 21/02/2026 | Video estructura de datos e interfaz de usuario | Video en YouTube | `CONSTRUIR PROTOTIPO DE SOFTWARE...docx` (`youtu.be/MLSoil_8ZeU`) | `02-week/02-optional-activity/` | `03-execute/02-week/02-optional-activity/` | **COMPLETO** |
| **03** | 07/03/2026 | Manual GitHub | Manual de comandos Git/GitHub | `comments-git.md`, `guia-git-terminal.md` | `03-week/` y `03-execute/03-week/` | `03-execute/03-week/` | **COMPLETO** |
| **04** | 14/03/2026 | Lista de chequeo y requisitos supermercado | Guía e informe de observación en equipo | `Guia_Observacion_Grupo4.xlsx`, `informe_observacion_grupo4.docx` | `04-week/` y `03-execute/04-week/` | `03-execute/04-week/02-optional-activity/` | **COMPLETO** |
| **05** | 21/03/2026 | Mapa de procesos | Infografía/presentación y video | `Presentación - Mapa de Procesos Organizacional.pdf`, `Video_mapadeprocesos.md` | `05-week/` y `03-execute/05-week/` | `03-execute/05-week/02-optional-activity/` | **COMPLETO** |
| **06** | 28/03/2026 | Instrumentos de recolección | Infografía y aplicación al proyecto | `Presentación - Instrumentos de Recolección.pdf`, `TiendApp_Instrumentos_Fase1.docx` | `05-week/`, `06-week/` y `03-execute/06-week/` | `03-execute/06-week/02-optional-activity/` | **COMPLETO** |
| **07** | 25/04/2026 | ¿Qué es SRS? | Tarea e infografía sobre SRS | `infografia_sobre_srs_202604250743.pdf` | `03-execute/07-week/02-optional-activity/` | `03-execute/07-week/02-optional-activity/` | **COMPLETO** |
| **08** | Abr 2026 | Instrumentos de recolección con nuestro proyecto | Encuesta y entrevista UX del proyecto | `TiendApp_Encuesta_Validacion.docx`, `TiendApp_Guion_Entrevista_UX.docx` | `03-execute/08-week/02-optional-activity/` | `03-execute/08-week/02-optional-activity/` | **COMPLETO** |
| **09** | Abr 2026 | Actividad supermercado | Análisis cualitativo, cuantitativo y reporte ejecutivo | `Analisis_Cualitativo_v3.docx`, `Lab_Analisis_v3.xlsx`, `Reporte_Ejecutivo_LaEsquina_ES.md` | `09-week/` (con duplicados) y `10-week/` | `03-execute/09-week/02-optional-activity/` | **COMPLETO** |
| **10** | May 2026 | Cronograma | Documento de cronograma semanal | `Cronograma weeks.md` | `03-execute/10-week/02-optional-activity/` | `03-execute/10-week/02-optional-activity/` | **COMPLETO** |
| **11** | 09/05/2026 | Actividad SRS Supermercado | Documento SRS y video exposición | `SRS_LaEsquina_v2.docx`, `Inventario_TiendApp.mp4` | `03-execute/11-week/02-optional-activity/` | `03-execute/11-week/02-optional-activity/` | **COMPLETO** |
| **12** | 16/05/2026 | ¿Qué son las TIC? y exposiciones | Evaluación de compañeros, proyecto base y talleres TIC | `InformeObservacionSintetizacion_JuanDoria.docx`, `ObservacionDeSintetizacion-JuanDoria.pdf`, `design-software/` | `03-execute/12-week/` y `Guia_Aprendizaje_TIC/` | `03-execute/12-week/` y `Guia_Aprendizaje_TIC/` | **COMPLETO** |
| **13** | May 2026 | Gestión Horario Instructores | PPTX 5 slides, Word y Mockup HTML | `SGH_Presentacion.pptx`, `SGH_Resumen_Simple.docx`, `sena_schedule_mockup.html` | `03-execute/13-week/02-optional-activity/` | `03-execute/13-week/02-optional-activity/` | **COMPLETO** |
| **14** | 22/06/2026 | Implementar documentos de gestión de horarios adaptados | `.zip` documental, PDF Blueprint y enlace de video | `Laboratorio_Sena_Poblado.zip`, `The_Master_Blueprint.pdf`, `Video Link.docx` | `03-execute/14-week/02-optional-activity/` | `03-execute/14-week/02-optional-activity/` | **COMPLETO** |
| **15** | 06/06/2026 | Trabajo Diagramas UML, `.drawio` y Word | 3 diagramas `.drawio.svg` y 3 documentos `.docx` | `Descripcion PRS-SHEDULE.docx`, `Draw Casos de uso.drawio.svg`, `Draw Clases.drawio.svg`, `Draw UML.drawio.svg`, `Plantilla Justificacion de Clases.docx`, `Plantilla casos de uso.docx` | `03-execute/15-week/02-optional-activity/` | `03-execute/15-week/02-optional-activity/` | **COMPLETO** |
| **16** | 04/07/2026 | Trabajo UML, Use Case, Clases y Asistencia SENA | Diagramas de casos de uso y clases, requisitos y mockup | `CONTROL DE ASISTENCIA.txt`, `Diagrama de Clases.jpeg`, `Diagramas de caso de uso.jpeg`, `Mock Up.pdf` | `03-execute/16-week/02-optional-activity/` | `03-execute/16-week/02-optional-activity/` | **COMPLETO** |
| **17** | 11/07/2026 | Mockup de Asistencia SENA (entrega 11/07/2026) | Idea replanteada, mockup mejorado y presentación | `Hoja_de_Ruta_SGA_Fase1_v2_simplificada.docx`, `Presentación - Hoja de Ruta Técnica Fase 1.pdf`, `control_asistencia_requisitos.txt`, `mockupdef.pdf` | `03-execute/17-week/02-optional-activity/` | `03-execute/17-week/02-optional-activity/` | **COMPLETO** |
| **18** | 25/07/2026 | `.zip` proyecto Asistencia e ingeniería inversa | `.zip` del proyecto + documentos de ingeniería inversa y Design Thinking | `Análisis Design Thinking...pdf`, `Asistencia.md`, `INGENIERIA_INVERSA.md`, `INVENTARIO.md`, `MOSCOW_OPERATIVO.md`, `design_thinking_asistencia.docx`, `presentacion.html` (falta `.zip`) | `03-execute/18-week/02-optional-activity/` | `03-execute/18-week/02-optional-activity/` | **PARCIAL** |
| **19** | Jul 2026 | Socialización de los MVP | Actividad en clase | Sin archivos locales | `03-execute/19-week/` | `03-execute/19-week/` | **REQUIERE REVISIÓN** |
| **20** | 01/08/2026 | Ejercicio en clase (Grupo 1: Aeropuerto) | Design Thinking, MoSCoW y E-R | `Design thinking.pdf`, `MoSCoW.jpeg`, `entidad relación PRD — Venta y control de tiquetes aéreos.drawio.svg` | `03-execute/20-week/02-optional-activity/` | `03-execute/20-week/02-optional-activity/` | **COMPLETO** |
| **21** | 08/08/2026 | Realizar MER + `.md` ingeniería inversa a mockup | MER1, MER2, tablas Excel e informe `.md` | `ExcelTablasProblema1.xlsx`, `ExcelTablasProblema2.xlsx`, `MER1.jpeg`, `MER2.jpeg`, `ingenieria_inversa_Mockup_Gestion_Horarios_SENA.md` | `03-execute/21-week/02-optional-activity/` | `03-execute/21-week/02-optional-activity/` | **COMPLETO** |
| **22** | Ago 2026 | Subir todos los BPMN y archivos asociados | Diagramas BPMN y modelo de datos | 12 archivos `.bpmn` (5 roles), `ER.pdf`, `MODELO_DATOS_LOGICO_GLOBAL.md` | `03-execute/23-week/02-optional-activity/` | `03-execute/22-week/02-optional-activity/` | **COMPLETO** |
| **23** | Ago 2026 | Estrategia de pensamiento, ingeniería inversa, plan de contingencia y gestión de horarios | Presentación e informe integral de brechas y contingencia | `Auditoría Integral de Brechas • SENA (50 Slides).pdf`, `auditoria_mockup_horarios.md` | `03-execute/22-week/02-optional-activity/` | `03-execute/23-week/02-optional-activity/` | **COMPLETO** |
| **24** | 12/09/2026 | Gobernanza y proyecto Taller de Mecánica | Repositorios/documentación de gobernanza y taller | `repo.md` (enlaces a GitHub) | `03-execute/24-week/02-optional-activity/` | `03-execute/24-week/02-optional-activity/` | **PARCIAL** |
| **25** | 17/10/2026 | Documentación sobre trabajo del instructor (*Orderflow Engine*) | Preguntas de alcance e informe de auditoría | `5_PREGUNTAS_ORDERFLOW_ENGINE.pdf`, `INFORME_PRELIMINAR_AUDITORIA_ORDERFLOW.md` | `03-execute/25-week/02-optional-activity/` | `03-execute/25-week/02-optional-activity/` | **PARCIAL** |
| **26** | 07/11/2026 | Escaneo de apuntes de proyectos evaluados y clase | PDF con apuntes escaneados | `Evidencia de apuntes semana 26.pdf` | `03-execute/26-week/02-optional-activity/` | `03-execute/26-week/02-optional-activity/` | **COMPLETO** |
| **27** | 21/11/2026 | Archivos/diapositivas o trabajo E2E (*End-to-End*) | Entregable sobre pruebas E2E | Ninguno aún | `03-execute/27-week/02-optional-activity/` | `03-execute/27-week/02-optional-activity/` | **PENDIENTE** |
| **28–40** | Por programar | Semanas futuras | Por definir | Estructura preparada (`.gitkeep`) | `03-execute/28-week/` a `40-week/` | `03-execute/28-week/` a `40-week/` | **PENDIENTE** |

---

## J. Validación Final y Limitaciones

### 1. Verificaciones Ejecutadas
- **Verificación de Duplicados (SHA-256):** Se volvió a calcular el hash SHA-256 de todos los archivos del repositorio, comprobando que se eliminaron los 9 grupos de duplicados accidentales y solo permanece la copia intencional del informe `.md` de auditoría del mockup entre las semanas 21 y 23.
- **Verificación de Enlaces Relativos en `README.md` y `AUDITORIA_REORGANIZACION.md`:** Se ejecutó un script automatizado en Python que decodifica y comprueba en disco cada ruta relativa enlazada en la documentación (`100%` de enlaces válidos, `0` enlaces rotos).
- **Verificación de XML / SVG / BPMN / HTML:** Todos los 12 archivos `.bpmn`, 4 archivos `.drawio.svg` y 6 documentos `.html` fueron parseados y validados sin errores de sintaxis.
- **Verificación de Compilación y Pruebas del Proyecto Ejecutable (`design-software` en Semana 12):**
  - **Frontend React (`web/`):** Se validó la estructura de `package.json`, `src/App.jsx`, `src/main.jsx` y `Dockerfile`.
  - **Base de Datos (`db/`):** Se verificó la sintaxis DDL/DML de `001_schema.sql` y `002_seed_demo.sql`.
  - **API Go (`api/`):** Se revisó `cmd/server/main.go`, `go.mod` y `docker-compose.yml`.

### 2. Limitaciones del Entorno
- El contenedor de evaluación no cuenta con el demonio de Docker activo ni el compilador `go` preinstalado en `/usr/bin`, por lo que la validación del proyecto `03-execute/12-week/01-session/design-software` se realizó mediante inspección estática completa de código fuente, contratos SQL y manifiestos `Dockerfile`/`docker-compose.yml`.
- Los repositorios externos referenciados en [`03-execute/24-week/02-optional-activity/repo.md`](./03-execute/24-week/02-optional-activity/repo.md) (`Tomasberserk/sistema-taller-automotriz` y `Tomasberserk/ejemplo`) y los repositorios externos de *Orderflow Engine* (Semana 25) residen fuera de este repositorio.
