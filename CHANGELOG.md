# Registro de cambios — ERS SIGA (Equipo H, PE4)

Formato basado en [Keep a Changelog](https://keepachangelog.com/es-ES/1.1.0/).
Las versiones corresponden al ERS/SRS del sistema SIGA y a las líneas base establecidas en la Práctica Experimental PE4 de ISR-401, período 2026–2027 PPA.

---

## [v1.1] — 2026-08-09

Línea base aprobada por el Change Control Board del 2026-08-09 y publicada como *tag* anotado `baseline-v1.1`. Incorpora las 23 correcciones de los defectos críticos y mayores de la inspección Fagan del mismo día y los cambios aprobados en las tres RFC.

### Añadido

- **RF-26 — Escalado automático de alertas críticas no atendidas** y **NFR-17** (umbral de escalado de 30 min). Origen: defecto **D-11** — el diagrama de estados de la entidad *Alerta* definía la transición «Escalada» invocando un umbral inexistente en NFR-01, y ningún requisito especificaba el escalado.
- **RF-27 — Notificación de vulneraciones de seguridad** y **NFR-18** (plazos de 5 días a la Autoridad y 3 días al titular). Origen: **RFC-03**, derivada del defecto **D-13** — los Art. 43 y 46 de la LOPDP estaban mapeados a NFR-12, que solo emite una alerta interna al administrador.
- **RF-31 — Excepción autorizada de apagado automático** (máximo 4 h, motivo obligatorio, caducidad automática, registro en bitácora). Origen: **RFC-01**, derivada del defecto **D-23** — la estrategia de gestión del conflicto «Automatización de apagado frente a continuidad académica» comprometía excepciones autorizadas sin requisito destino.
- **RF-28, RF-29 y RF-30**, formalizados a partir de tres de las ocho necesidades marcadas como «candidato» en el catálogo de evidencias B.1. Origen: defecto **D-15**. Las cinco restantes se declaran expresamente diferidas a la Entrega 4 con motivo registrado.
- **Riesgo RG-01** (ausencia de conectividad en aulas no piloto), con NFR-16 como mitigación funcional obligatoria. Origen: **RFC-02**, derivada del defecto crítico **D-04**.
- **Clase de usuario «Titular de datos»** en la sección 2.3, con acceso restringido a su propio perfil, su bitácora y RF-24, RF-25 y RF-27. Origen: defecto **D-21**.
- **Contenido completo del Apéndice A.4 (declaración de uso de IA generativa)**, hasta ahora un título sin texto. Origen: defecto crítico **D-01**.
- **16 filas de RNF y 2 de RF-24/RF-25** en la matriz de trazabilidad impresa, que carecía de ellas; y las 18 restricciones de diseño y 12 RNF ausentes en la tabla de clasificación. Origen: defectos **D-15** y **D-09**.

### Cambiado

- **RF-24 y RF-25 pasan de *Should* a *Must*** por tratarse de derechos de ejercicio obligatorio del titular (LOPDP Art. 13 y 14), y su plazo se corrige de «15 días **hábiles**» a «15 días» naturales, alineándolo con el texto legal. Origen: **RFC-03**, defecto **D-14**. En consecuencia los RF *Must* pasan de 17 a 20 y la cobertura declarada del MVP se recalcula del 64,7 % al **55 %**.
- **NFR-16 se cuantifica en ≤30 s y se eleva a *Must***; **SUP-01 y DEP-01 se reformulan** para no asumir conectividad estable en las aulas, contradicha por la evidencia EV-15. Origen: **RFC-02**, defecto crítico **D-04**.
- **RF-13 y RF-16 delimitan sus disparadores** para eliminar el solapamiento: RF-13 opera sobre equipo individual con 15 min de desocupación *dentro* del horario; RF-16 sobre el apagado total al finalizar el horario. Origen: defecto **D-12**.
- **RF-06 incorpora dos postcondiciones verificables** —no persistir video ni fotogramas y no ejecutar reconocimiento facial— sobre las que pasa a sustentarse la clasificación en Categoría B de riesgo ético, antes apoyada en una afirmación sin requisito destino. Origen: defecto crítico **D-03**.
- **Las 17 historias de usuario y sus escenarios Gherkin se reescriben**: beneficio real en la cláusula «para», evento observable en «Cuando» y resultado verificable en «Entonces». Origen: defecto **D-10**.
- **La sección 6.1 declara un único alcance del MVP**, verificable contra el código del *commit* `1ef2873`, en lugar de dos listas incompatibles. Origen: defecto **D-06**.
- **El cronograma A.3 y las conclusiones se alinean con el estado real** de la entrega: OSF en revisión institucional sin DOI, modelado y priorización completados, análisis empírico parcial. Origen: defecto **D-07**.
- **El párrafo introductorio de la sección 3.2 declara el destino de RC-22 y RC-23**, requisitos crudos que no originaban ningún RF ni constaban como descartados. Origen: defecto **D-22**.
- **La sección 5.4 declara la fecha, los participantes y el stakeholder validador de la estimación WSJF**, cuya tabla estaba poblada bajo un texto que la declaraba pendiente. Origen: defecto **D-08**.
- **El protocolo experimental declara la regla de emparejamiento** (25 pares por objetivo funcional equivalente), sin la cual el diseño apareado no era ejecutable sobre 26 y 25 requisitos. Origen: defecto **D-18**.
- **EV-02 se identifica de forma única** como «Coordinación de la Carrera (COORD-01)» en las tres ubicaciones que antes daban tres denominaciones distintas. Origen: defecto **D-19**.
- **La tabla de resultados Kano se sustituye por la tabla de frecuencias completa** con n exacto por pregunta, y se retira la calificación de «categoría dominante clara» para un resultado del 37 %. Origen: defecto **D-20**.
- **La matriz de trazabilidad sustituye 18 identificadores HU/CA inexistentes** por las historias HU-01 a HU-17 que sí define el ERS, y completa la columna ID-HU de los 10 requisitos que la tenían vacía. Origen: defecto crítico **D-02**.
- **Las siete referencias cruzadas escritas a mano se sustituyen por referencias simbólicas** (`\ref`), tras etiquetar las 68 tablas y las 51 figuras. Origen: defecto **D-05**.
- **La fila del registro de correcciones sobre el video EV-02 se reescribe como declaración unívoca de estado pendiente**, en lugar de declarar la corrección hecha y pendiente en la misma celda. Origen: defecto **D-17**.

### Eliminado

- **`\nocite{*}` de la sección IX**, que imprimía las 37 entradas de la bibliografía sin que ninguna estuviera citada en el texto; se introducen citas explícitas en el punto de uso y se depuran las entradas que no sustentan ninguna afirmación. Origen: defecto **D-16**.
- **La afirmación de que SIGA procesa video para determinar ocupación agregada**, contradicha por RF-03 y por RF-06. Origen: defecto crítico **D-03**.
- **La frase «se deja la estructura lista para completar durante la semana 13»** de la sección 5.4, que contradecía una tabla ya poblada. Origen: defecto **D-08**.
- **La exclusión de los estudiantes como actores del sistema**, incompatible con su condición de titulares de datos para RF-24 y RF-25. Origen: defecto **D-21**.

### Pendiente

- Unificación de la nomenclatura RNF/NFR en las 71 apariciones del documento (defecto menor **D-24**, acción abierta A-05 del CCB).
- Definición de identificadores CA-nn para los criterios de aceptación, hoy inexistentes en el ERS pese a ser referenciados por la matriz (acción abierta A-02).
- Confirmación de la denominación institucional vigente de la Facultad (defecto menor **D-27**, acción abierta A-03).
- Regrabación de EV-02 en ≥720p o publicación del original desde la zona restringida (defecto **D-17**, acción abierta A-04).
- Consulta institucional sobre la designación de un responsable de protección de datos, condición de viabilidad de RF-27 (acción abierta A-01).

---

## [v1.0] — 2026-08-02 (Entrega 2A del PFC — versión inspeccionada)

Versión del ERS/SRS del sistema SIGA sometida a la inspección formal del Equipo H. Corresponde al *commit* `bb04d43` del repositorio `gsanchezc6-beep/SIGA_FGMMN_ISR401_AVANCE_2A`, archivo `01_ERS/ERS_SRS_2A_v1.0.pdf` (122 páginas). Se conserva íntegra en `01_ERS/` como artefacto de referencia de la inspección.

### Contenido

- 25 requisitos funcionales, 16 requisitos no funcionales sobre ISO/IEC 25010:2023, 18 restricciones de diseño y 16 casos de uso especificados textualmente.
- Sección de requisitos legales mapeados a la LOPDP y 17 historias de usuario en formato Connextra con criterios Gherkin.
- Modelado UML completo (41 diagramas) y modelado organizacional i*.
- Priorización combinada MoSCoW + Kano + WSJF y matriz de trazabilidad extendida.
- Producto Mínimo Viable en repositorio separado y protocolo del componente empírico.
