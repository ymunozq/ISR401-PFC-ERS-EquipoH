# Anexo A — Lista de verificación de inspección (ISO/IEC/IEEE 29148:2018 §5.2.5–§5.2.8)

**Inspector:** Chavarria Cuenca Tahiny Mel — C.I. 0943050054 — tchavarriac@uteq.edu.ec
**Rol:** Inspector 1 (pase independiente I1)
**Documento revisado:** `ERS_SIGA_v1.0.pdf` — SIGA, Sistema Inteligente de Gestión de Aulas, Entrega 2A
**Fuente:** repositorio `gsanchezc6-beep/SIGA_FGMMN_ISR401_AVANCE_2A`, commit `bb04d43`, archivos `01_ERS/ERS_SRS_2A_v1.0.pdf` y `01_ERS/secciones_generadas.tex`
**Alcance asignado al pase I1:** Historial de versiones y Registro de correcciones; secciones I y II (1.1–2.7); sección 3.2 (RF-01 a RF-25); sección 3.4 (requisitos legales); sección 3.6 (historias de usuario); sección 5.3 (Kano); sección IX (referencias); Anexo A.4.
**Páginas efectivas revisadas:** 122 (121 numeradas + portada)
**Preparación individual:** 2026-08-08, 19:10–21:40 (2 h 30 min). Marca temporal verificable: commit `insp(anexo-a): pase I1 de Chavarria sobre el ERS v1.0` del repositorio del Equipo H, anterior a la reunión.

> Regla aplicada: la inspección **detecta**, no corrige. Ninguna observación de esta lista propone solución; las soluciones se acuerdan después de la reunión (véase `correcciones_aplicadas.csv`).

---

## P1 — Ambigüedad
*¿Cada requisito admite una sola interpretación razonable? ¿Se evitan términos de grado sin umbral?*

| # | Pregunta de verificación | Requisito revisado | Cumple (S/N) | Evidencia (línea / página) | Observación |
|---|---|---|---|---|---|
| 1.1 | ¿Los identificadores de requisito son únicos y estables a lo largo del documento? | NFR-01 a NFR-16 | **N** | L880 vs Tabla 41; 40 apariciones de `RNF-nn` y 31 de `NFR-nn` | El texto anuncia «RNF-01 a RNF-16» y la tabla los rotula «NFR-01 a NFR-16». El glosario (L80) registra ambos prefijos como sinónimos pero no fija uno. → **D-24** |
| 1.2 | ¿La organización cliente se denomina de una sola forma? | Alcance y stakeholders | **N** | L58 y L125 vs L163 y L187 | «Facultad de Ciencias de la Computación» frente a «Facultad de Ciencias de la Computación y Diseño Digital». → **D-27** |
| 1.3 | ¿Los criterios de verificación de los RF Must están cuantificados? | RF-01 a RF-23 | S | L511, L526, L541, L556… | Todos los RF Must fijan umbral numérico (≤10 s, ≤5 s, ≥95 %, ≤2 min). Punto fuerte del documento. |
| 1.4 | ¿Se evitan términos de grado sin umbral en las descripciones? | RF-01 a RF-25 | S | — | No se detectaron «adecuado», «suficiente» ni «significativo» en las fichas de RF. |
| 1.5 | ¿El glosario cubre los términos técnicos usados en los requisitos? | §1.3 | S | L76–L98 | 23 entradas; cubre IoT, MQTT, gateway, bitácora, explicabilidad. |

## P2 — Completitud
*¿Está todo lo necesario y nada queda como andamiaje sin llenar?*

| # | Pregunta de verificación | Requisito revisado | Cumple (S/N) | Evidencia (línea / página) | Observación |
|---|---|---|---|---|---|
| 2.1 | ¿Toda sección anunciada en el índice tiene contenido? | Anexo A.4 | **N** | L2225–L2228; PDF p. 121 | «A.4 Declaración de uso de Inteligencia Artificial Generativa» aparece como título sin una sola línea de texto, seguida inmediatamente del Anexo C. El Registro de correcciones (L38) la cita como evidencia de una corrección exigida por el docente. → **D-01** |
| 2.2 | ¿Las declaraciones sobre el estado de un requisito se materializan en su ficha? | RF-24, RF-25 | **N** | L498 vs L846–L873 | Se afirma que ambos «se marcan explícitamente como pendientes de validación»; ninguna de las dos fichas contiene esa marca. La referencia «(Sección 3, RNF)» no resuelve a ninguna sección. → **D-28** |
| 2.3 | ¿Cada obligación legal identificada tiene un requisito que la implemente? | LOPDP Art. 43 y 46 | **N** (revisado también por I2) | L939 vs L899 | Concurrente con **D-13**; se registra en el pase I2. |
| 2.4 | ¿La plantilla de atributos está completa en las 25 fichas de RF? | RF-01 a RF-25 | S | L505–L873 | Las 25 fichas presentan los mismos 6 campos + ID y nombre. Uniformidad correcta. |
| 2.5 | ¿El catálogo de RF cubre las funciones anunciadas en §2.2? | §2.2 vs §3.2 | S | L145–L157 vs L505–L873 | Las 7 funciones del producto tienen al menos un RF destino. |

## P3 — Consistencia
*¿El documento se contradice consigo mismo o con sus artefactos anexos?*

| # | Pregunta de verificación | Requisito revisado | Cumple (S/N) | Evidencia (línea / página) | Observación |
|---|---|---|---|---|---|
| 3.1 | ¿La justificación legal del tratamiento de imagen se corresponde con lo que especifican los RF? | RF-03, RF-06, RD-05 | **N** | L941 vs L536 y L581 | La fila Art. 4 / Art. 26 afirma que SIGA procesa el video para determinar ocupación agregada, sin almacenar fotogramas ni identificar personas. RF-03 detecta ocupación **con sensores de presencia, sin depender de cámaras**; RF-06 solo embebe el flujo en el panel. Sobre esa afirmación descansa la clasificación Categoría B. → **D-03** |
| 3.2 | ¿Existen requisitos Must que especifiquen el mismo comportamiento? | RF-13, RF-16 | **N** | L686 vs L731 | Mismo comportamiento (apagado por aula vacía fuera de horario), misma prioridad, mismo umbral de 2 min, sin delimitación entre ambos. → **D-12** |
| 3.3 | ¿La prioridad MoSCoW asignada es compatible con la naturaleza del requisito? | RF-24, RF-25 | **N** | L855, L870 vs L1881 | Derechos de ejercicio obligatorio (LOPDP Art. 13 y 14) priorizados **Should**, categoría definida como «el sistema opera sin ellos». Además el plazo pasa de «15 días» (L936–937) a «15 días **hábiles**» en las fichas. → **D-14** |
| 3.4 | ¿Los plazos normativos se transcriben sin alteración? | RF-24, RF-25, NFR-11 | **N** | L854, L869, L898 | Incluido en **D-14**. |
| 3.5 | ¿Las leyendas de tabla corresponden al contenido de su tabla? | §2.5 | **N** (revisado por I2) | L285, L299 | Concurrente con **D-25**. |
| 3.6 | ¿La versión declarada en portada, historial y CHANGELOG coincide? | Historial de versiones | S* | L10–L12 vs `CHANGELOG.md` | El historial usa «3.0», el CHANGELOG «2A-1.0.0» y el archivo «v1.0». Se registra como observación de fondo del baseline, tratada en la RFC-03 y en §8 del informe; no se contabiliza como defecto independiente por corresponder al repositorio, no al ERS. |

## P4 — Verificabilidad
*¿Puede un tercero comprobar objetivamente el cumplimiento?*

| # | Pregunta de verificación | Requisito revisado | Cumple (S/N) | Evidencia (línea / página) | Observación |
|---|---|---|---|---|---|
| 4.1 | ¿Los criterios de aceptación en Gherkin son ejecutables? | HU-01 a HU-17 | **N** | L991–L1154 | Las 17 historias repiten la descripción del RF en la cláusula «para ⟨beneficio⟩»; los 17 escenarios usan el comodín «cuando se cumple la condición operativa de RF-nn» y colocan un procedimiento de prueba en «Entonces». Ninguno es decidible. → **D-10** |
| 4.2 | ¿Los resultados cuantitativos reportados permiten reconstruir el cálculo? | Kano RF-05, RF-07, RF-08 | **N** | L1902–L1912 | RF-05 «Indiferente (37 %, categoría dominante clara)» sin declarar la distribución del 63 % restante; RF-08 reporta 24 respuestas y RF-07 18, frente a n=27–30. → **D-20** |
| 4.3 | ¿El estado de validación de cada RNF está declarado sin ambigüedad? | NFR-01 a NFR-16 | S | L888–L903 | Punto fuerte real: la columna «Estado de validación» declara *validado*, *parcialmente sustentado* o *no verificado* para los 16, sin casillas en blanco. |
| 4.4 | ¿Las afirmaciones no triviales se anclan a una fuente citada? | §IX y todo el cuerpo | **N** | L2104; 0 comandos `\cite` en 2 256 líneas | La bibliografía se emite con `\nocite{*}`: las 37 entradas se imprimen aunque ninguna esté citada. Las atribuciones («Chazette y Schneider, 2020») son texto plano sin vínculo. → **D-16** |

## P5 — Trazabilidad
*¿Cada requisito enlaza hacia atrás con su fuente y hacia adelante con sus artefactos?*

| # | Pregunta de verificación | Requisito revisado | Cumple (S/N) | Evidencia (línea / página) | Observación |
|---|---|---|---|---|---|
| 5.1 | ¿Las referencias cruzadas internas resuelven a la tabla correcta? | Tablas 41 y 60 | **N** | L880, L912, L919, L1825, L1874, L2097 | «Tabla 39» (×5) apunta en realidad a la ficha de RF-24; la tabla de RNF es la 41. «Tabla 42» (×2) apunta a *Trazabilidad Ley→Artículo→RF/RNF*; la de clasificación es la 60. Siete números escritos a mano; el fuente define 51 `\label` y no usa un solo `\ref`. → **D-05** |
| 5.2 | ¿Cada RF declara su evidencia de origen? | RF-01 a RF-23 | S | L507, L522, L537… | Los 23 RF heredados citan EV-01 y/o EV-02 y su RC de origen. |
| 5.3 | ¿La bibliografía listada está efectivamente citada en el texto? | §IX | **N** | — | Incluido en **D-16**. |
| 5.4 | ¿Cada correción declarada tiene evidencia localizable? | Registro 1B→2A | **N** (revisado por Moderador) | L37 | Concurrente con **D-17**. |

## P6 — Factibilidad
*¿Es realizable con los recursos, el entorno y las restricciones declaradas?*

| # | Pregunta de verificación | Requisito revisado | Cumple (S/N) | Evidencia (línea / página) | Observación |
|---|---|---|---|---|---|
| 6.1 | ¿Las suposiciones del entorno resisten la evidencia de campo recogida? | SUP-01, DEP-01, NFR-16 | **N** (revisado por I2) | L316, L336 vs L903 | Concurrente con **D-04**. |
| 6.2 | ¿Los umbrales de los RF Must son alcanzables con la arquitectura propuesta? | RF-01, RF-02, RF-04 | S | L509–L556 vs §4.8 | Latencias de 5–15 s son alcanzables sobre MQTT + API REST según el diagrama de despliegue. |
| 6.3 | ¿Las restricciones económicas acotan el alcance de forma coherente? | RD-07, RD-08 | S | L964–L965 | Aulas piloto antes de cobertura total; coherente con el MVP. |

---

## Resumen del pase I1

| Propiedad | Preguntas | No conformes | Defectos aportados |
|---|---|---|---|
| Ambigüedad | 5 | 2 | D-24, D-27 |
| Completitud | 5 | 2 (+1 concurrente) | D-01, D-28 |
| Consistencia | 6 | 3 (+1 concurrente) | D-03, D-12, D-14 |
| Verificabilidad | 4 | 3 | D-10, D-16, D-20 |
| Trazabilidad | 4 | 1 (+2 concurrentes) | D-05 |
| Factibilidad | 3 | 0 (+1 concurrente) | — |
| **Total** | **27** | **11 propios** | **11 defectos** (mínimo exigido: 6) |

**Firma del inspector:** _______________________  **Fecha:** 2026-08-08
Chavarria Cuenca Tahiny Mel — C.I. 0943050054
