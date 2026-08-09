# Acta de la reunión de inspección formal (método Fagan)

**Proyecto inspeccionado:** SIGA — Sistema Inteligente de Gestión de Aulas (PFC, equipo FGMMN)
**Artefacto:** `ERS_SIGA_v1.0.pdf` (Entrega 2A), 122 páginas efectivas
**Origen:** `https://github.com/gsanchezc6-beep/SIGA_FGMMN_ISR401_AVANCE_2A`, commit `bb04d43`
**Equipo inspector:** Equipo H — ISR-401 Ingeniería de Requerimientos, 2026–2027 PPA
**Fecha:** 2026-08-09 · **Hora:** 15:00–16:25 · **Duración:** 85 min (máximo permitido: 90 min)
**Lugar:** FCCDD-LAB-TIC-201, Campus Central, UTEQ

---

## 1. Roles asignados (Fagan, 1976)

| Rol | Función | Integrante | C.I. | Correo institucional |
|---|---|---|---|---|
| Moderador | Conduce la reunión, cronometra, impide la discusión de soluciones y consolida el Anexo B | Muñoz Quiñonez Yeranick Esther | 1207929645 | ymunozq@uteq.edu.ec |
| Lector | Parafrasea el ERS sección por sección, sin lectura literal | Chavarria Cuenca Tahiny Mel | 0943050054 | tchavarriac@uteq.edu.ec |
| Inspector 1 | Revisa el ERS de forma independiente y completa su copia del Anexo A (pase I1) | Chavarria Cuenca Tahiny Mel | 0943050054 | tchavarriac@uteq.edu.ec |
| Inspector 2 | Revisa el ERS de forma independiente y completa su copia del Anexo A (pase I2, rol asumido adicionalmente por autorización docente) | Chavarria Cuenca Tahiny Mel | 0943050054 | tchavarriac@uteq.edu.ec |

**Declaración expresa sobre el criterio A3.** La guía exige los cuatro roles en cuatro personas distintas. El Equipo H tiene dos integrantes; los roles de Lector, Inspector 1 e Inspector 2 recaen en la misma persona por autorización docente. Para preservar en lo posible la independencia del método, los pases I1 e I2 se ejecutaron **en sesiones separadas, en fechas distintas y sobre alcances disjuntos del documento**, sin consultar el resultado del otro pase; la Moderadora aportó además un tercer pase de revisión sobre el alcance restante. Esta desviación se declara aquí, en los tres Anexos A, en §4 y en §12 del informe; **no se presenta como equivalente a una inspección de cuatro personas independientes** y se somete a la valoración del docente.

## 2. Alcance inspeccionado

| Pase | Responsable | Alcance | Páginas |
|---|---|---|---|
| I1 | Chavarria (Inspector 1) | Historial y registro de correcciones; §I y §II (1.1–2.4); §3.2 (RF-01 a RF-25); §3.4; §3.6; §5.3; §IX; Anexo A.4 | ≈ 58 |
| I2 | Chavarria (Inspector 2) | §2.5–§2.6; §3.3; §3.5; §IV; §V (5.1, 5.2, 5.4, 5.5); §VII; `matriz_trazabilidad.csv` | ≈ 45 |
| Mod | Muñoz (Moderadora) | Registro de correcciones; §2.4.2; §VI; §VIII; Anexos A.1–A.3 y B.1; coherencia con `CHANGELOG.md`, `05_MVP/`, `02_Evidencias/` | ≈ 19 |
| — | — | **Total documento** | **122** |

## 3. Preparación individual (previa y con marca temporal)

| Pase | Fecha y hora | Duración | Defectos registrados antes de la reunión |
|---|---|---|---|
| I1 | 2026-08-08, 19:10–21:40 | 2 h 30 min | 11 |
| I2 | 2026-08-09, 08:00–10:30 | 2 h 30 min | 12 |
| Mod | 2026-08-09, 10:45–12:45 | 2 h 00 min | 12 |
| **Total preparación** | | **7 h 00 min** | **35 observaciones brutas** |

Cada pase superó el mínimo de 6 defectos por inspector exigido por la guía. Las marcas temporales son verificables en el historial de commits del repositorio del Equipo H (`git log --format='%h %ad %an %s'`), todos anteriores a las 15:00 del 2026-08-09.

## 4. Agenda ejecutada

| Hora | Bloque | Contenido |
|---|---|---|
| 15:00–15:05 | Apertura | La Moderadora recuerda la regla Fagan: **la inspección detecta, no corrige**. Se declara la desviación del criterio A3. |
| 15:05–15:20 | §I y §II | La Lectora parafrasea propósito, alcance, perspectiva, clases de usuario, stakeholders, conflictos, entorno, suposiciones y dependencias. Se reportan D-03, D-04, D-21, D-23, D-25, D-27. |
| 15:20–15:50 | §III | Paráfrasis de RF, RNF, requisitos legales, restricciones e historias de usuario. Se reportan D-01 (por reenvío al anexo), D-10, D-12, D-13, D-14, D-22, D-24, D-28. |
| 15:50–16:05 | §IV y §V | Paráfrasis del modelado y de la priorización y trazabilidad. Se reportan D-08, D-09, D-11, D-15, D-26, D-29. |
| 16:05–16:15 | §VI a §VIII | Paráfrasis del MVP, protocolo empírico y conclusiones. Se reportan D-06, D-07, D-18. |
| 16:15–16:22 | §IX y anexos | Paráfrasis de referencias y anexos. Se reportan D-01, D-05, D-16, D-17, D-19, D-20, D-02. |
| 16:22–16:25 | Cierre | Consolidación, deduplicación y conteo. Fijación de la fecha del CCB. |

## 5. Consolidación

| Concepto | Valor |
|---|---|
| Observaciones brutas presentadas | 35 |
| Duplicados fusionados | 6 (D-03/6.1 con 3.1; D-13 con 2.3 de I1; D-15 con 5.2 de I2 y 5.3 de Mod; D-07 con 3.3, 4.3 y 6.1 de Mod; D-14 con 3.3 y 3.4 de I1; D-02 con 5.4 de I2) |
| Observaciones desestimadas por ser de forma y no de requisito | 0 admitidas como defecto (registradas con asterisco en los Anexos A) |
| **Defectos únicos consolidados** | **29** |
| Críticos | 4 (D-01, D-02, D-03, D-04) |
| Mayores | 19 (D-05 a D-23) |
| Menores | 6 (D-24 a D-29) |
| Mínimo exigido por la guía | 15 únicos, ≥3 críticos o mayores — **cumplido con holgura** |

## 6. Incidencias de conducción

- En dos ocasiones (§3.2 RF-13/RF-16 y §5.5 matriz) la inspectora inició una propuesta de solución; la Moderadora la interrumpió y trasladó la discusión a la fase de corrección, conforme al método.
- El defecto D-02 requirió abrir el archivo `matriz_trazabilidad.csv` durante la sesión para contrastar identificadores; se registró como verificación en vivo, no como discusión de solución.
- No se discutió ninguna corrección durante los 85 minutos de sesión.

## 7. Acuerdos

1. Corregir el **100 % de los defectos críticos y mayores** (23 de 29) y documentar cada corrección con texto antes/después en `correcciones_aplicadas.csv`.
2. Dejar sin corregir los 6 defectos menores, con justificación registrada en el mismo archivo.
3. Elevar al CCB tres solicitudes de cambio: RFC-01 (alcance, derivada del defecto D-23 detectado en esta inspección), RFC-02 (calidad, modificación de RNF) y RFC-03 (normativa).
4. Convocar el CCB para el 2026-08-09 a las 17:00.
5. Publicar la línea base `baseline-v1.1` una vez implementados los cambios aprobados.

---

**Firma de la Moderadora:** _______________________
Muñoz Quiñonez Yeranick Esther — C.I. 1207929645

**Firma de la Lectora / Inspectora:** _______________________
Chavarria Cuenca Tahiny Mel — C.I. 0943050054
