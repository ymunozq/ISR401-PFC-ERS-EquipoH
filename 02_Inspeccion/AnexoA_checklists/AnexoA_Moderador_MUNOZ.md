# Anexo A — Lista de verificación de inspección (ISO/IEC/IEEE 29148:2018 §5.2.5–§5.2.8)

**Revisora:** Muñoz Quiñonez Yeranick Esther — C.I. 1207929645 — ymunozq@uteq.edu.ec
**Rol:** Moderadora de la inspección (conduce la reunión y consolida el Anexo B). Ejecuta además un pase propio de revisión sobre el alcance no cubierto por los pases I1 e I2.
**Documento revisado:** `ERS_SIGA_v1.0.pdf` — SIGA, Sistema Inteligente de Gestión de Aulas, Entrega 2A
**Vínculo con el PFC:** la Moderadora es integrante del equipo FGMMN autor del ERS inspeccionado (portada del ERS, L59) y desempeña en él el rol de Documentadora (Anexo A.1 del ERS, L2127). Es, por tanto, la **integrante titular** que vincula esta práctica con el PFC (criterio A1).
**Alcance asignado a este pase:** Registro de correcciones 1B→2A; sección 2.4.2 (conflictos entre stakeholders); sección VI (MVP); sección VIII (conclusiones); Anexos A.1 a A.3 y B.1; coherencia entre el ERS y los artefactos del repositorio (`CHANGELOG.md`, `05_MVP/README.md`, `02_Evidencias/`).
**Preparación individual:** 2026-08-09, 10:45–12:45 (2 h 00 min). Marca temporal verificable: commit `insp(anexo-a): pase de revision de la Moderadora sobre el ERS v1.0`, anterior a la reunión de las 15:00.

> **Nota de conducción.** Por tratarse de un equipo de dos integrantes, la Moderadora aporta además un pase de revisión propio para alcanzar la cobertura del documento. Durante la reunión su función fue exclusivamente conducir, cronometrar, impedir la discusión de soluciones y consolidar el Anexo B; sus propios hallazgos se presentaron al inicio de la sesión y fueron contrastados por la inspectora antes de admitirse.

---

## P1 — Ambigüedad

| # | Pregunta de verificación | Elemento revisado | Cumple (S/N) | Evidencia | Observación |
|---|---|---|---|---|---|
| 1.1 | ¿El registro de correcciones describe cada corrección de forma unívoca? | Registro 1B→2A, fila 2 | **N** | L37 | Ver **D-17**: la misma celda declara la corrección hecha («subida de grabación en ≥720p») y pendiente («mientras se completa la nueva grabación»). |
| 1.2 | ¿Los roles del equipo se declaran con nombres formateados de manera uniforme? | Anexo A.1 | S* | L2125–L2128 | «SÁNCHEZ GARY», «MENDOZA ALLAN, WINSTON CEDEÑO», «MUÑOZ YERANICK»: mezcla de orden apellido-nombre y nombre-apellido. Erratas de forma; no se contabiliza como defecto de requisito. |
| 1.3 | ¿El alcance del MVP se enuncia con un solo porcentaje de cobertura? | §6.1, §6.4 | **N** | L2009, L2030 | Ver **D-06**. |

## P2 — Completitud

| # | Pregunta de verificación | Elemento revisado | Cumple (S/N) | Evidencia | Observación |
|---|---|---|---|---|---|
| 2.1 | ¿Cada estrategia de gestión de conflictos tiene un requisito destino? | §2.4.2, conflicto «Automatización de apagado frente a continuidad académica» | **N** | L242 | La estrategia compromete «permitir excepciones autorizadas y registrar actividades extraordinarias». RD-13 y RF-15 cubren la integración del horario, pero **ningún RF de RF-01 a RF-25** especifica un mecanismo de excepción u override sobre RF-13/RF-15/RF-16. Riesgo directo: apagar equipos durante una clase extendida. → **D-23** |
| 2.2 | ¿Los ocho conflictos restantes tienen estrategia con requisito destino? | §2.4.2 | S | L237–L244 | Los otros siete conflictos remiten a RF o RD existentes (RF-19, RF-23, RD-05, RD-10, RD-16). |
| 2.3 | ¿El catálogo de evidencias declara fecha verificable para cada EV? | EV-17, EV-18, EV-19 | S* | L2208–L2210 | La columna Fecha dice «2A» en lugar de una fecha; EV-18 se declara «8 de 15 mínimo, ampliación en curso». Observación de forma, admitida como declaración honesta y no contabilizada. |

## P3 — Consistencia

| # | Pregunta de verificación | Elemento revisado | Cumple (S/N) | Evidencia | Observación |
|---|---|---|---|---|---|
| 3.1 | ¿El alcance del MVP es el mismo en todas las subsecciones que lo declaran? | §6.1 vs §6.4 | **N** | L2009 vs L2030 | §6.1: 12 RF (RF-01, 02, 03, 04, 05, 07, 08, 10, 11, 12, 13, 15) = 71 %. §6.4: 11 RF (RF-01, 03, 07, 08, 10, 12, 13, 16, 19, 22, 23) = 64,7 %. Cinco RF de una lista no están en la otra y viceversa. Solo §6.4 coincide con `05_MVP/README.md`. → **D-06** |
| 3.2 | ¿El estado declarado en el cronograma coincide con el del cuerpo del documento? | Tabla 67 vs §IV, §5.3, §5.4, §VI, §VIII | **N** | L2169–L2173 | Cronograma: UML, Kano, WSJF y MVP «Pendiente» (sem. 14-15); análisis empírico y dataset Zenodo «Pendiente» (sem. 16); OSF «En proceso» (sem. 11). Cuerpo: todos presentados como ejecutados con datos reales. → **D-07** |
| 3.3 | ¿El ERS y el `CHANGELOG.md` del repositorio declaran el mismo estado de entrega? | Historial vs CHANGELOG | **N** | L12 vs `CHANGELOG.md` §Pendiente | El historial describe la v3.0 como «componente empírico registrado en OSF»; el CHANGELOG lista «Registro del protocolo experimental en el OSF» entre lo **pendiente**. Consolidado dentro de **D-07** por identidad de causa. |
| 3.4 | ¿Las figuras se insertan una sola vez? | §4.4, §4.5, §4.9 | **N** | L1489–L1527 vs L1580+ | Cinco imágenes duplicadas con etiquetas distintas; el Índice de figuras repite cinco leyendas y el conteo de 51 entornos `figure` no coincide con los «41 diagramas» de las conclusiones. → **D-29** |

## P4 — Verificabilidad

| # | Pregunta de verificación | Elemento revisado | Cumple (S/N) | Evidencia | Observación |
|---|---|---|---|---|---|
| 4.1 | ¿El commit del MVP declarado es verificable? | `05_MVP/README.md` | S | `git ls-remote` sobre `SIGA_FGMMN_MVP` | HEAD = `1ef2873d611aae8e…`, coincide con el commit declarado `1ef2873`. Repositorio público y accesible. **Punto fuerte verificado.** |
| 4.2 | ¿La matriz CSV alcanza el mínimo de filas declarado? | `matriz_trazabilidad.csv` | S | 44 filas de datos | Cumple el mínimo de 40 declarado en el Apéndice D. |
| 4.3 | ¿Las conclusiones reportan resultados que el cuerpo del documento sustente? | §VIII | **N** | L2097 | Se afirma que el componente empírico «ya cuenta con datos reales incorporados en esta versión (3 jueces ciegos, κ de Fleiss)»; el cuerpo (§VII) solo presenta el **plan** de análisis y no reporta un solo resultado. Consolidado dentro de **D-07**. |

## P5 — Trazabilidad

| # | Pregunta de verificación | Elemento revisado | Cumple (S/N) | Evidencia | Observación |
|---|---|---|---|---|---|
| 5.1 | ¿La evidencia citada por el registro de correcciones existe en el repositorio? | `02_Evidencias/Video/` | **N** | Inspección del árbol del repositorio | El directorio existe y contiene 9 subcarpetas (EV01–EV08, EV11) **sin un solo archivo**. Ni la grabación original ni la de ≥720p están disponibles. → **D-17** |
| 5.2 | ¿Todo requisito crudo elicitado tiene RF destino o declaración de descarte? | RC-01 a RC-25 | **N** | L498 vs L822, L837 | Se afirma correspondencia RC-01…RC-25 → 23 RF. La correspondencia es 1:1 hasta RF-21; RF-22 deriva de RC-24 y RF-23 de RC-25. **RC-22 y RC-23 no originan ningún RF** y no se declaran descartados, fusionados ni diferidos. → **D-22** |
| 5.3 | ¿Las necesidades marcadas como «candidato» en el catálogo se formalizaron? | EV-08, EV-10, EV-11, EV-13, EV-15 | **N** | L2199–L2206 | Ocho necesidades registradas como «candidato» (alerta ante manipulación de cámara, SLA por prioridad, vista individual de aula, historial de correcciones por equipo, control de acceso a puertas, SLA de 24 h, catálogo de incidencias ampliado, foto adjunta en reporte) no se formalizaron como requisito ni figuran en backlog alguno. → **D-15** (consolidado con el hallazgo 5.2 del pase I2) |
| 5.4 | ¿Los consentimientos de la segunda ronda están completos y declarados? | EV-15 / WT-03 | S | L2206, L2215 | El ERS declara explícitamente que el walkthrough WT-03 queda invalidado por falta de consentimiento y no se usa como evidencia. **Punto fuerte: gestión ética correctamente documentada.** |

## P6 — Factibilidad

| # | Pregunta de verificación | Elemento revisado | Cumple (S/N) | Evidencia | Observación |
|---|---|---|---|---|---|
| 6.1 | ¿El cronograma es compatible con el alcance comprometido? | Tabla 67 | **N** | L2169–L2174 | Las semanas 14-15 y 16 concentran modelado UML completo, Kano, WSJF, MVP, análisis empírico y dataset FAIR, mientras el documento ya los declara hechos en la semana 13. La planificación no sostiene el alcance declarado. Consolidado dentro de **D-07**. |
| 6.2 | ¿El MVP declarado es reproducible por un tercero? | `05_MVP/README.md` | S | Node ≥22.5, `npm start`, SQLite nativo | Instrucciones completas y stack sin dependencias de compilación. **Punto fuerte.** |

---

## Resumen del pase de la Moderadora

| Propiedad | Preguntas | No conformes | Defectos aportados |
|---|---|---|---|
| Ambigüedad | 3 | 2 (concurrentes) | — |
| Completitud | 3 | 1 | D-23 |
| Consistencia | 4 | 4 | D-06, D-07, D-29 |
| Verificabilidad | 3 | 1 (consolidado) | — |
| Trazabilidad | 4 | 3 | D-17, D-22, D-15 |
| Factibilidad | 2 | 1 (consolidado) | — |
| **Total** | **19** | **12** | **7 defectos únicos** |

**Firma de la Moderadora:** _______________________  **Fecha:** 2026-08-09
Muñoz Quiñonez Yeranick Esther — C.I. 1207929645
