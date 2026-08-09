# Acta del Change Control Board (CCB) simulado

**Proyecto:** SIGA — Sistema Inteligente de Gestión de Aulas (PFC, equipo FGMMN)
**Documento base:** `ERS_SIGA_v1.0` → resultante `ERS_SIGA_v1.1`
**Fecha:** 2026-08-09 · **Hora:** 17:00–18:30 · **Duración:** 90 min
**Lugar:** FCCDD-LAB-TIC-201, Campus Central, UTEQ
**Marco de referencia:** PMBOK 7.ª ed. (control integrado de cambios) e ISO/IEC/IEEE 15288:2023 §6.4.6

---

## 1. Asistentes y roles del CCB

| Rol en el CCB | Integrante | C.I. | Voto |
|---|---|---|---|
| Presidente del CCB | Muñoz Quiñonez Yeranick Esther | 1207929645 | Sí |
| Representante del cliente (Infraestructura y Mantenimiento / Coordinación) | Chavarria Cuenca Tahiny Mel | 0943050054 | Sí |
| Analista de requisitos | Muñoz Quiñonez Yeranick Esther | 1207929645 | Sí |
| Desarrollador | Chavarria Cuenca Tahiny Mel | 0943050054 | Sí |

**Declaración expresa.** El Equipo H tiene dos integrantes y el CCB requiere cuatro perspectivas diferenciadas. Cada integrante asumió dos roles y **argumentó separadamente desde cada uno**, dejando constancia en la deliberación de qué perspectiva sostiene cada argumento. El cómputo de votos es de cuatro votos, uno por rol. Esta desviación se declara igualmente en §6 y §12 del informe.

## 2. Agenda

1. Apertura y recordatorio de la regla de decisión: toda RFC cierra con decisión motivada, responsable y plazo (17:00–17:05).
2. Deliberación de RFC-02 — Cuantificación de NFR-16 y modo degradado (17:05–17:35).
3. Deliberación de RFC-01 — Excepción autorizada de apagado automático (17:35–18:00).
4. Deliberación de RFC-03 — Deberes de notificación LOPDP y plazo legal (18:00–18:25).
5. Cierre, nueva versión resultante y acciones (18:25–18:30).

El orden de deliberación se alteró respecto del numérico a propuesta del analista: RFC-02 se trató primero por introducir la guarda de datos obsoletos que protege los mismos requisitos que RFC-01 modifica.

---

## 3. Deliberación por RFC

### 3.1 RFC-02 — Cuantificación de NFR-16 y elevación a Must (calidad)

**Resumen de la deliberación.**
El *analista* abrió señalando que este no es un cambio de mejora sino una corrección de validez: el ERS mantiene en SUP-01 la suposición de conectividad estable mientras su propia evidencia EV-15 documenta lo contrario, de modo que la especificación se apoya sobre una premisa que el equipo ya sabe falsa. El *representante del cliente* apoyó el cambio con un argumento operativo distinto y más fuerte que el documental: para el Personal de Infraestructura, un dato antiguo presentado como actual es peor que la ausencia de dato, porque induce a **no** acudir a un aula que sí tiene un problema; pidió expresamente que el aviso sea visible en la tarjeta del aula y no solo en un registro. El *desarrollador* aceptó el umbral de 30 s como técnicamente alcanzable, pero advirtió que el cambio obliga a introducir una guarda en el motor de reglas de apagado —hoy implementado en el MVP— y pidió que la prueba de regresión sobre RF-13 y RF-16 fuera condición de cierre. El *presidente* consultó el efecto sobre el alcance comprometido del MVP: elevar NFR-16 a Must obliga a cubrirlo, lo que el desarrollador estimó en 21 h dentro de la ventana de la Entrega 4.

**Alternativas consideradas y descartadas.**
(a) *Mantener NFR-16 sin cuantificar y limitarse a corregir SUP-01*: descartada porque deja el requisito inverificable, que es exactamente lo que el defecto D-04 señala. (b) *Cuantificar en 60 s por alinearlo con NFR-01*: descartada porque NFR-01 mide entrega de alerta y no obsolescencia de dato; reutilizar el umbral por comodidad reproduciría el error del defecto D-11.

**Decisión: APROBADO** (4 votos a favor, 0 en contra).
**Justificación:** corrige un defecto crítico de factibilidad, convierte la evidencia de campo de mayor valor de la segunda ronda en un requisito verificable y cierra de paso un riesgo funcional no formulado (apagado con datos de ocupación obsoletos).
**Acciones:** (1) Reformular SUP-01 y DEP-01 y registrar el riesgo RG-01. (2) Cuantificar NFR-16 en ≤30 s y elevarlo a Must. (3) Añadir la guarda de datos obsoletos a RF-13 y RF-16. (4) Prueba de regresión sobre RF-13 y RF-16 como condición de cierre.
**Responsables:** Cedeño Ávila Winston Damián (implementación); Muñoz Quiñonez Yeranick Esther (ERS y matriz).
**Plazo:** ERS v1.1 el 2026-08-09; implementación en la semana 16 de la Entrega 4 (2B).
**Prioridad de implementación:** 1 de 3.

### 3.2 RFC-01 — Excepción autorizada de apagado automático (alcance)

**Resumen de la deliberación.**
El *analista* presentó la RFC como cierre del hueco de trazabilidad D-23: la sección 2.4.2 compromete «permitir excepciones autorizadas» como estrategia de gestión de un conflicto real entre stakeholders, y ningún RF la implementa. El *representante del cliente* fue el defensor más firme, con el argumento de adopción: una sola clase interrumpida por un apagado automático destruye la confianza del claustro en el sistema, y EV-12 (DOC-01) ya sitúa la fiabilidad percibida como el factor decisivo. El *desarrollador* no se opuso al requisito pero abrió la objeción de fondo de la sesión: una excepción sin límite temporal se convierte en la práctica en una desactivación permanente del ahorro energético, que es el beneficio con el que el proyecto se justifica ante las Autoridades; propuso limitar la duración. El *presidente* recogió la objeción y la convirtió en condición formal, y consultó si procedía implementarlo ya en el MVP; el desarrollador respondió que no, porque el MVP no implementa RF-15 y la inhibición quedaría parcialmente ciega.

**Alternativas consideradas y descartadas.**
(a) *Resolver el conflicto solo ampliando la integración del horario académico (RD-13)*: descartada porque el horario oficial no contempla defensas de tesis, tutorías ni clases extendidas, que son precisamente los casos del conflicto. (b) *Permitir la anulación manual del apagado sin registro*: descartada por incompatibilidad con RF-23 y con RD-11, que exigen bitácora de toda acción.

**Decisión: APROBADO CON CONDICIONES** (4 votos a favor, 0 en contra).
**Condiciones:** duración máxima de la excepción **4 horas**; motivo obligatorio; caducidad automática; registro en bitácora (RF-23); notificación al responsable del aula.
**Justificación:** cierra un compromiso que el propio ERS adquirió sin requisito destino, con coste bajo (34 h-persona) frente al riesgo de apagar equipos durante una clase en curso.
**Acciones:** (1) Crear RF-31 con las condiciones impuestas. (2) Añadir el permiso «registrar excepción» a RF-19. (3) Inhibir la notificación de RF-21 durante una excepción vigente. (4) Actualizar CU-13, el diagrama de clases y MU-01. (5) Añadir la fila correspondiente a la matriz de trazabilidad.
**Responsables:** Sánchez Cornejo Gary Alberto (especificación); Mendoza Palma Allan Jeremy (modelado).
**Plazo:** ERS v1.1 el 2026-08-09; implementación en la semana 17 de la Entrega 4 (2B).
**Prioridad de implementación:** 3 de 3.

### 3.3 RFC-03 — Deberes de notificación LOPDP y corrección del plazo legal (normativa)

**Resumen de la deliberación.**
El *analista* expuso que la tabla 3.4 del ERS identifica los Art. 43 y 46 y los mapea a NFR-12, que solo emite una alerta interna: la obligación está reconocida por escrito y no está implementada, lo que agrava la exposición en lugar de reducirla. Añadió los dos defectos concurrentes: RF-24 y RF-25 priorizados Should pese a ser derechos de ejercicio obligatorio, y el plazo convertido de «15 días» a «15 días hábiles». El *representante del cliente* apoyó sin reservas los cambios documentales y preguntó quién notificaría materialmente a la Autoridad; el analista reconoció que el ERS no designa responsable de protección de datos y que esa designación es una decisión organizacional ajena al equipo. El *desarrollador* planteó la objeción de coste y de dependencia: RF-27 son 25 horas y depende de una figura organizacional inexistente, por lo que se opuso a comprometerlo en el MVP. El *presidente* señaló el efecto colateral que nadie había calculado: elevar RF-24 y RF-25 a Must lleva los RF Must de 17 a 20 y baja la cobertura declarada del MVP del 64,7 % al 55 %.

**Punto de discrepancia registrado.** El desarrollador se abstuvo en la votación de RF-27 por considerar que el CCB no puede comprometer un requisito cuya viabilidad depende de una designación institucional que el equipo no controla. La abstención se registra como tal y no se computa como voto favorable.

**Alternativas consideradas y descartadas.**
(a) *Mantener el mapeo actual y anotar «cumplimiento organizacional, fuera del sistema»*: descartada porque los Art. 43 y 46 exigen trazabilidad de la notificación, que sin registro en el sistema no puede demostrarse. (b) *Elevar solo RF-24 y dejar RF-25 en Should*: descartada por arbitraria; ambos artículos tienen la misma naturaleza obligatoria.

**Decisión: APROBADO CON CONDICIONES** (3 votos a favor, 1 abstención).
**Condiciones:** RF-27 y NFR-18 se **especifican** en el ERS v1.1 pero se **implementan** en la Entrega 4; su viabilidad queda supeditada a que la Facultad designe un responsable de protección de datos, lo que se eleva como consulta institucional. La cobertura del MVP se recalcula y se declara en 55 % sobre 20 RF Must, en lugar de mantener el 64,7 % sobre un denominador desactualizado.
**Acciones:** (1) Crear RF-27 y NFR-18. (2) Acotar el alcance declarado de NFR-12 en la tabla 3.4. (3) Elevar RF-24 y RF-25 a Must y corregir «15 días hábiles» → «15 días» en RF-24, RF-25 y NFR-11. (4) Ampliar RD-09. (5) Recalcular y declarar la cobertura del MVP. (6) Elevar la consulta sobre el responsable de protección de datos.
**Responsables:** Gilces Carranza José Ignacio (RF-27 y NFR-18); Muñoz Quiñonez Yeranick Esther (prioridad, plazo, matriz y recálculo).
**Plazo:** cambios documentales en el ERS v1.1 el 2026-08-09; RF-27 implementado en la semana 17 de la Entrega 4 (2B).
**Prioridad de implementación:** 2 de 3.

---

## 4. Resumen de decisiones

| RFC | Naturaleza | Origen | Decisión | Votos | Prioridad | Plazo |
|---|---|---|---|---|---|---|
| RFC-01 | Alcance (RF nuevo) | Defecto D-23 de la inspección | Aprobado con condiciones | 4–0 | 3 | Sem. 17 (2B) |
| RFC-02 | Calidad (modificación de RNF) | Defecto D-04 de la inspección (crítico) | Aprobado | 4–0 | 1 | Sem. 16 (2B) |
| RFC-03 | Normativa | Defectos D-13 y D-14 de la inspección | Aprobado con condiciones | 3–0–1 | 2 | Sem. 17 (2B) |

Las tres RFC provienen de conflictos o defectos reales detectados en la inspección del Paso 1; ninguna procede de un escenario hipotético.

## 5. Versión resultante del ERS

| Concepto | Valor |
|---|---|
| Versión anterior | ERS_SIGA **v1.0** (Entrega 2A, commit `bb04d43` del repositorio del PFC) |
| **Versión resultante** | **ERS_SIGA v1.1** |
| Contenido de la v1.1 | 23 correcciones de defectos críticos y mayores (`02_Inspeccion/correcciones_aplicadas.csv`) + los cambios aprobados en las tres RFC |
| Requisitos nuevos | RF-26 (escalado de alertas), RF-27 (notificación de vulneraciones), RF-28 a RF-30 (candidatos formalizados), RF-31 (excepción de apagado), NFR-17, NFR-18 |
| Requisitos repriorizados | RF-24 y RF-25 (Should → Must); NFR-16 (→ Must) |
| Requisitos modificados | RF-06, RF-13, RF-16, RF-19, RF-21, NFR-11, NFR-12, SUP-01, DEP-01, RD-09, RD-13 |
| RF Must resultantes | 20 (antes 17) |
| Cobertura recalculada del MVP | 55 % (11 de 20 RF Must), antes declarada 64,7 % sobre 17 |
| Línea base | `baseline-v1.1`, *tag* anotado y publicado |
| Coherencia de versión | «v1.1» declarada de forma idéntica en la portada del informe, en el historial de revisiones, en `CHANGELOG.md` y en el *tag* de Git |

## 6. Acciones abiertas

| # | Acción | Responsable | Plazo |
|---|---|---|---|
| A-01 | Elevar a la Coordinación de Carrera la consulta sobre la designación de un responsable de protección de datos (condición de viabilidad de RF-27) | Muñoz Yeranick | 2026-08-16 |
| A-02 | Definir identificadores CA-nn para los criterios de aceptación, hoy inexistentes en el ERS pese a ser referenciados por la matriz (raíz del defecto D-02) | Gilces José | Entrega 4 (2B) |
| A-03 | Resolver la denominación institucional vigente de la Facultad (defecto D-27, no corregido a la espera de respuesta oficial) | Muñoz Yeranick | Entrega 4 (2B) |
| A-04 | Regrabar EV-02 en ≥720p o publicar el original desde la zona restringida (defecto D-17) | Sánchez Gary | Entrega 4 (2B) |
| A-05 | Unificar la nomenclatura RNF/NFR en las 71 apariciones del documento (defecto D-24) | Muñoz Yeranick | Entrega 4 (2B) |

---

**Firma del Presidente del CCB:** _______________________
Muñoz Quiñonez Yeranick Esther — C.I. 1207929645

**Firma del Representante del cliente / Desarrollador:** _______________________
Chavarria Cuenca Tahiny Mel — C.I. 0943050054

**Fecha de firma:** 2026-08-09
