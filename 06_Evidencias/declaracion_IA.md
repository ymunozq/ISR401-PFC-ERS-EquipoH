# Anexo F — Declaración de uso de Inteligencia Artificial generativa

**Práctica:** PE4 — Práctica Experimental Unidad IV (ISR-401, 2026–2027 PPA)
**Equipo:** H — Muñoz Quiñonez Yeranick Esther y Chavarria Cuenca Tahiny Mel
**Fecha de la declaración:** 2026-08-09

---

## 1. Herramienta y versión

| Campo | Detalle |
|---|---|
| Herramienta | Claude Code (Anthropic), modelo Claude Opus 5 |
| Modalidad de uso | Asistente de análisis documental y de redacción, ejecutado localmente sobre los archivos del repositorio |
| Fechas de uso | 2026-08-08 y 2026-08-09 |
| Material puesto a disposición de la herramienta | Guía y rúbrica PE4 (PDF); repositorio público `gsanchezc6-beep/SIGA_FGMMN_ISR401_AVANCE_2A` en su commit `bb04d43`; carpeta de referencia del Equipo D como ejemplo de estructura |

## 2. Tareas asistidas, tarea por tarea

| # | Tarea | Grado de asistencia | Qué aportó el equipo |
|---|---|---|---|
| 1 | Lectura completa del ERS (2 256 líneas de fuente LaTeX, 122 páginas de PDF) y de los artefactos del repositorio | Alto — la herramienta recorrió el documento y devolvió citas literales con número de línea | El equipo definió el alcance de cada pase, las seis propiedades de verificación y los criterios de severidad |
| 2 | Localización de discrepancias verificables (numeración de tablas, conteos, identificadores cruzados, contradicciones entre secciones) | Alto | El equipo **verificó una a una** las 29 discrepancias contra el fuente y el PDF antes de admitirlas como defecto; véase §3 |
| 3 | Redacción de los Anexos A y B, del acta de inspección y de las métricas | Medio — redacción a partir de los hallazgos ya verificados | El equipo fijó la clasificación por tipo y severidad de cada defecto y la interpretación de cada métrica |
| 4 | Redacción de las tres RFC y del acta del CCB | Medio | El equipo decidió qué tres cambios elevar, las decisiones, las condiciones impuestas y los votos |
| 5 | Construcción de la matriz de trazabilidad corregida y del backlog | Medio | El equipo definió las épicas, los campos personalizados y qué requisitos son huérfanos |
| 6 | Redacción y maquetación del informe en LaTeX | Medio | El equipo aportó las cinco conclusiones críticas, los juicios de la comparativa CASE y la discusión IR tradicional / IR ágil |
| 7 | Comandos de Git, estructura de carpetas y compilación | Alto — ejecución mecánica | El equipo revisó los mensajes de *commit* y el contenido del *tag* |

**Tareas NO asistidas:** la ejecución de la reunión de inspección, la deliberación del CCB, la toma de las capturas del tablero y del historial de Git, y las fotografías de la sesión.

## 3. Verificación crítica realizada por el equipo

La regla que el equipo se impuso fue: **ningún hallazgo entra en el Anexo B si no se puede señalar con el dedo en el documento inspeccionado.** Las comprobaciones ejecutadas fueron:

| Verificación | Método | Resultado |
|---|---|---|
| Numeración real de las tablas 39, 41, 42 y 60 | Recuento programático de leyendas de `longtable` en el fuente | Confirmado: la tabla de RNF es la 41 y la de clasificación la 60 (defecto D-05) |
| Sección A.4 vacía | Lectura de la página 121 del PDF compilado | Confirmado visualmente: el título va seguido del Anexo C sin contenido (defecto D-01) |
| Ausencia de `\cite` y de `\ref` | Recuento de expresiones regulares sobre las 2 256 líneas | Confirmado: 0 `\cite`, 0 `\ref`, 51 `\label`, 1 `\nocite{*}` (defecto D-16) |
| Identificadores HU/CA de la matriz | Contraste del CSV contra las historias HU-01…HU-17 del ERS | Confirmado: 18 identificadores sin contrapartida (defecto D-02) |
| Directorio `02_Evidencias/Video/` | Listado recursivo del árbol del repositorio | Confirmado: 9 subcarpetas, 0 archivos (defecto D-17) |
| Aritmética de la tabla WSJF | Recálculo manual de los 17 cocientes | **Los 17 cocientes son correctos.** El defecto D-08 se reformuló: no es un error de cálculo sino la ausencia de fuente del dato de entrada |
| Repositorio y commit del MVP | `git ls-remote` sobre `SIGA_FGMMN_MVP` | **Verificado como correcto:** HEAD coincide con el commit `1ef2873` declarado. **No se registró como defecto** |
| Conteo de páginas del ERS | Descompresión de los flujos del PDF y verificación por lectura | 122 páginas físicas, 121 numeradas |
| Cobertura de CU en la matriz del ERS | Contraste CU-01…CU-16 contra las filas de la tabla | **Cobertura completa. No se registró como defecto** |

Se descartaron cuatro observaciones propuestas por la herramienta que no resistieron la verificación, entre ellas una supuesta discrepancia en el recuento de diagramas («41 diagramas» frente a 51 entornos de figura): al descontar los 4 *mockups*, la firma y las 5 imágenes duplicadas, el número declarado resultó correcto, por lo que **la observación se retiró** y el hallazgo se reformuló como el defecto menor D-29, limitado a la duplicación de figuras.

## 4. Fragmentos afectados del entregable

| Artefacto | Fragmentos con asistencia |
|---|---|
| `02_Inspeccion/` | Redacción de las tablas de los tres Anexos A, del acta y de las interpretaciones de las métricas |
| `03_CCB/` | Redacción de los formularios RFC y del acta; las decisiones, condiciones y votos son del equipo |
| `04_Trazabilidad/` | Generación de los CSV a partir de la estructura definida por el equipo |
| `05_Informe/` | Redacción y maquetación de las 14 secciones; §11 (conclusiones críticas), §9 y §10 responden a juicios del equipo |
| `README.md`, `CHANGELOG.md` | Redacción íntegra asistida |

**Sin asistencia:** las firmas, las capturas y las fotografías de sesión.

## 5. Declaración

Las integrantes del Equipo H declaran que:

1. El uso de IA generativa se limitó a las tareas descritas en §2 y no sustituyó la ejecución de la inspección ni la deliberación del CCB.
2. Los 29 defectos del Anexo B fueron verificados uno a uno contra el ERS inspeccionado, con cita de línea o de página, según consta en §3.
3. No se fabricó ninguna evidencia. Los elementos que exigen captura propia o fotografía (Anexos D parcial y E) están identificados como pendientes en `04_Trazabilidad/capturas/LEEME_CAPTURAS.md` y en `06_Evidencias/*/LEEME_*.md`, **sin sustitutos sintéticos**.
4. Las referencias del informe fueron comprobadas contra su fuente y todas están citadas en el texto.
5. Se conoce que declarar el uso de IA no exime de las penalizaciones de la sección 8.3 de la guía y que la omisión de esta declaración activa además el criterio de admisión A4.

---

**Firma:** _______________________
Muñoz Quiñonez Yeranick Esther — C.I. 1207929645 — ymunozq@uteq.edu.ec

**Firma:** _______________________
Chavarria Cuenca Tahiny Mel — C.I. 0943050054 — tchavarriac@uteq.edu.ec
