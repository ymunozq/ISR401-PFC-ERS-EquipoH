# Anexo A — Lista de verificación de inspección (ISO/IEC/IEEE 29148:2018 §5.2.5–§5.2.8)

**Inspector:** Chavarria Cuenca Tahiny Mel — C.I. 0943050054 — tchavarriac@uteq.edu.ec
**Rol:** Inspector 2 (pase independiente I2, rol asumido adicionalmente por autorización docente)
**Documento revisado:** `ERS_SIGA_v1.0.pdf` — SIGA, Sistema Inteligente de Gestión de Aulas, Entrega 2A
**Fuente:** repositorio `gsanchezc6-beep/SIGA_FGMMN_ISR401_AVANCE_2A`, commit `bb04d43`
**Alcance asignado al pase I2:** secciones 2.5 y 2.6 (entorno, suposiciones y dependencias); sección 3.3 (RNF y estado de validación); sección 3.5 (restricciones de diseño); sección IV (modelado UML y diagramas de estados); sección V (5.1, 5.2, 5.4, 5.5); sección VII (protocolo experimental); archivo `04_Trazabilidad/matriz_trazabilidad.csv`.
**Páginas efectivas revisadas:** 122 (121 numeradas + portada)
**Preparación individual:** 2026-08-09, 08:00–10:30 (2 h 30 min), en sesión separada e independiente del pase I1 y sin consultar sus resultados. Marca temporal verificable: commit `insp(anexo-a): pase I2 de Chavarria sobre el ERS v1.0`, anterior a la reunión de las 15:00.

> **Declaración de honestidad metodológica.** La guía exige cuatro roles en cuatro personas distintas (criterio A3). El Equipo H cuenta con dos integrantes, por lo que Chavarria ejecuta los dos pases de inspección en sesiones separadas y con alcances disjuntos, por autorización docente. La independencia entre pases es temporal y de alcance, no de persona; esta limitación se declara también en §4 y §12 del informe y no se presenta como equivalente a dos inspectores independientes.

---

## P1 — Ambigüedad

| # | Pregunta de verificación | Requisito revisado | Cumple (S/N) | Evidencia (línea) | Observación |
|---|---|---|---|---|---|
| 1.1 | ¿Los umbrales de los RNF están cuantificados? | NFR-01 a NFR-15 | S | L888–L902 | Todos fijan valor y unidad (60 s, 99 %, AES-256, 8 h-persona, 1 Mbps, 15 min). |
| 1.2 | ¿Algún RNF queda sin umbral pese a anunciarse la sección como «cuantificable»? | NFR-16 | S* | L903 | El propio ERS declara «umbral de tiempo de respuesta del aviso no cuantificado en esta entrega». Se considera **declarado, no oculto**: no se contabiliza como defecto y se traslada a la RFC-02. |
| 1.3 | ¿Las restricciones de diseño usan lenguaje prescriptivo unívoco? | RD-01 a RD-18 | S | L958–L975 | Redacción «deberá/no podrá» consistente en las 18. |
| 1.4 | ¿El tipo de restricción está clasificado sin solapamiento? | RD-09 a RD-11 | S | L966–L968 | Normativa/operativa/temporal/alcance bien separadas. |

## P2 — Completitud

| # | Pregunta de verificación | Requisito revisado | Cumple (S/N) | Evidencia (línea) | Observación |
|---|---|---|---|---|---|
| 2.1 | ¿La tabla anunciada como «clasificación completa» contiene todos los elementos? | Tabla 60 | **N** | L1825 vs L1832–L1861 | Anuncia RF + RNF + restricciones; contiene los 25 RF, solo 4 de 16 RNF y **ninguna** de las 18 RD. Faltan 12 RNF y 18 RD. → **D-09** |
| 2.2 | ¿Cada obligación legal mapeada tiene un requisito que efectivamente la implemente? | NFR-12, LOPDP Art. 43 y 46 | **N** | L939 vs L899 | El deber de notificar a la Autoridad (5 días) y al titular (3 días) se mapea a un RNF que solo genera una **alerta interna al administrador** ante intento de acceso. Nadie notifica fuera del sistema. → **D-13** |
| 2.3 | ¿Los 16 CU tienen especificación textual completa? | CU-01 a CU-16 | S | L1186–L1451 | Los 16 presentan actor principal, secundarios, propósito, pre/postcondiciones, curso normal y flujos alternativos. Punto fuerte. |
| 2.4 | ¿Las categorías MoSCoW declaradas tienen requisitos identificables? | §5.2.3 Could | **N*** | L1888 | «control de iluminación, aplicación móvil nativa y alertas por SMS» sin identificador de requisito. Observación menor absorbida en la discusión de **D-09**; no se contabiliza por separado. |

## P3 — Consistencia

| # | Pregunta de verificación | Requisito revisado | Cumple (S/N) | Evidencia (línea) | Observación |
|---|---|---|---|---|---|
| 3.1 | ¿El diagrama de estados se apoya en umbrales que existen en el catálogo de requisitos? | Entidad Alerta, NFR-01 | **N** | L1808 vs L888 | La transición «Notificada → Escalada» invoca «el umbral de tiempo definido en RNF-01». NFR-01 cuantifica el tiempo de **entrega** de la alerta, no el de atención. Además ningún requisito especifica escalado ni «intervención de autoridad». → **D-11** |
| 3.2 | ¿Los actores de una evidencia se identifican de forma única en todo el documento? | EV-02 | **N** | L2193 vs L2145 y L2167 | Catálogo B.1 y nombre de archivo del repositorio: «Coordinación de la Carrera (COORD-01)». Apéndice A.2 y cronograma: «Docente de la Facultad». Fichas de RF: «Coordinadora de la Carrera-Docente». Tres denominaciones para la fuente de 9 RF. → **D-19** |
| 3.3 | ¿Los titulares de derechos declarados pueden ejercerlos según el modelo de actores? | RF-24, RF-25 | **N** | L138 y L180 vs L854, L869 | §2.1 excluye a los estudiantes como actores porque «no requieren autenticación»; §2.3 los declara titulares para RF-24/RF-25, cuyas precondiciones exigen «usuario autenticado». → **D-21** |
| 3.4 | ¿Las leyendas de tabla corresponden a su contenido? | §2.5 | **N** | L285, L299 | La tabla de software lleva la leyenda «Componentes de hardware…» (duplicada) y la de red lleva «Componentes de software…». → **D-25** |
| 3.5 | ¿El diagrama de clases refinado cubre las operaciones de los RF nuevos? | Clase Usuario | S | L1468 | Declara `exportarDatos()` y `rectificarDatos()` para RF-24/RF-25. Correcto. |

## P4 — Verificabilidad

| # | Pregunta de verificación | Requisito revisado | Cumple (S/N) | Evidencia (línea) | Observación |
|---|---|---|---|---|---|
| 4.1 | ¿Los datos de priorización declaran su procedencia? | Tabla 62 (WSJF) | **N** | L1925 vs L1932–L1949 | El texto dice que los componentes «deben estimarse en sesión de equipo con al menos un stakeholder validando la escala» y que «se deja la estructura lista para completar durante la semana 13»; la tabla ya trae 17 filas de valores sin autor, fecha ni stakeholder. La aritmética de los 17 cocientes se verificó y es correcta; el dato de entrada no es reproducible. → **D-08** |
| 4.2 | ¿Los conteos declarados coinciden con el contenido real? | Tabla 63 | **N** | L1958 vs L1994 | Texto «28 filas», leyenda «29 filas», conteo real 28. → **D-26** |
| 4.3 | ¿El criterio de verificación de cada RNF es ejecutable en el entorno declarado? | NFR-02 | S* | L889 | «Monitoreo de uptime durante 30 días continuos» sobre un sistema no desplegado; el ERS lo declara *validado en 1B* refiriéndose al requisito, no a la ejecución de la prueba. Se acepta como declaración honesta y no se contabiliza. |
| 4.4 | ¿El plan de análisis estadístico es ejecutable sobre los datos definidos? | §7.1–§7.3 | **N** | L2052 vs L2070, L2077 | Población de 26 RF de LLM frente a 25 humanos, con diseño «cuasi-experimento **apareado**» y «prueba t para muestras apareadas». Conjuntos de distinto tamaño no admiten apareamiento y no se declara regla de emparejamiento. → **D-18** |

## P5 — Trazabilidad

| # | Pregunta de verificación | Requisito revisado | Cumple (S/N) | Evidencia | Observación |
|---|---|---|---|---|---|
| 5.1 | ¿La matriz declarada «fuente de verdad» referencia solo identificadores existentes en el ERS? | `matriz_trazabilidad.csv` | **N** | CSV filas 5–45 | Referencia 18 identificadores inexistentes: HU-24, HU-25, HU-07b, HU-07e, HU-10b, HU-12b, HU-12c, HU-12d, CA-04, CA-07b, CA-07c, CA-07d, CA-07e, CA-10b, CA-12b, CA-12c, CA-12d, CA-24, CA-25. El ERS define HU-01…HU-17 y ningún CA. En sentido inverso, deja `ID-HU` vacío para RF-01, RF-02, RF-03, RF-10, RF-13, RF-15, RF-19, RF-21, RF-22 y RF-23, que **sí** tienen historia. → **D-02** |
| 5.2 | ¿Los RF y RNF nuevos aparecen en la matriz impresa en el ERS? | Tabla 63 | **N** | L1965–L1993 | Sin fila para RF-24, RF-25 ni para ninguno de los 16 RNF. → **D-15** (consolidado con el hallazgo del Moderador) |
| 5.3 | ¿Los 16 CU están cubiertos por al menos una fila de la matriz? | CU-01 a CU-16 | S | L1966–L1993 | Cobertura completa de CU-01 a CU-16. Punto fuerte. |
| 5.4 | ¿Las filas de la matriz CSV declaran evidencia de origen para todos los RF? | Filas 25 y 26 | **N** | CSV | RF-24 y RF-25 tienen `ID-EV` vacío pero declaran stakeholder «Docente;Coordinacion»: enlace hacia atrás afirmado sin evidencia. Absorbido en **D-02**. |

## P6 — Factibilidad

| # | Pregunta de verificación | Requisito revisado | Cumple (S/N) | Evidencia (línea) | Observación |
|---|---|---|---|---|---|
| 6.1 | ¿Las suposiciones del entorno resisten la evidencia de campo del propio equipo? | SUP-01, DEP-01 | **N** | L316, L336 vs L903 | SUP-01 asume conectividad Wi-Fi o cableada **estable** en aulas y laboratorios; DEP-01 hace depender de ella todo el sistema. NFR-16, sustentado en EV-15, recoge que DOC-03 declaró que **no hay internet en la mayoría de las aulas**. La suposición fundacional está refutada por la evidencia y no se actualizó ni se registró el riesgo. → **D-04** |
| 6.2 | ¿La cobertura declarada de ISO/IEC 25010:2023 corresponde a la estructura de esa revisión? | Tabla 41 | S* | L880, L892 | Se anuncia cobertura de las nueve características. NFR-05 rotula «Portabilidad / Compatibilidad» y NFR-15 «Portabilidad», que en la revisión 2023 es subcaracterística de Flexibilidad; *Inocuidad (Safety)* no aparece. Se registró en la reunión como observación de modelo de calidad y se decidió tratarla dentro de la RFC-02 en lugar de abrir un defecto adicional, por afectar al mapeo y no al requisito. |
| 6.3 | ¿El esfuerzo declarado de los RNF de flexibilidad es estimable? | NFR-09 | S | L896 | 8 horas-persona con criterio de verificación por ejercicio de integración; estimable. |

---

## Resumen del pase I2

| Propiedad | Preguntas | No conformes | Defectos aportados |
|---|---|---|---|
| Ambigüedad | 4 | 0 | — |
| Completitud | 4 | 2 | D-09, D-13 |
| Consistencia | 5 | 4 | D-11, D-19, D-21, D-25 |
| Verificabilidad | 4 | 3 | D-08, D-18, D-26 |
| Trazabilidad | 4 | 2 (+1 absorbido) | D-02, D-15 |
| Factibilidad | 3 | 1 | D-04 |
| **Total** | **24** | **12** | **11 defectos únicos** (D-15 consolidado con el Moderador; mínimo exigido: 6) |

**Firma del inspector:** _______________________  **Fecha:** 2026-08-09
Chavarria Cuenca Tahiny Mel — C.I. 0943050054
