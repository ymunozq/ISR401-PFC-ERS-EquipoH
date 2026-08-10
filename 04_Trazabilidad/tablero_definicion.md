# Definición del tablero CASE — SIGA (Trello)

**Herramienta:** Trello (plan gratuito)
**Nombre del tablero:** `SIGA — Sistema Inteligente de Gestión de Aulas (ISR-401)`
**Acceso otorgado a:** ymunozq@uteq.edu.ec, tchavarriac@uteq.edu.ec y el docente responsable (Ing. Gleiston Cicerón Guerrero Ulloa, PhD)
**Fuente de verdad del contenido:** `backlog_export.csv` de esta misma carpeta (Anexo D)

---

## 1. Estructura de listas

| Lista | Significado | Criterio de entrada |
|---|---|---|
| Backlog | Requisito identificado y priorizado, sin análisis de impacto | Tiene RF/RNF asignado y prioridad MoSCoW |
| Análisis | En especificación o pendiente de decisión | Tiene historia redactada y al menos un criterio de aceptación |
| Aprobado | Aprobado por el CCB o validado con stakeholder | Consta en `Acta_CCB.md` o tiene evidencia de validación |
| Desarrollo | En implementación | Asignado a un integrante con criterios de aceptación cerrados |
| Hecho | Implementado y verificado contra el código del MVP | Comprobado contra el commit `1ef2873` del repositorio del MVP |

## 2. Épicas (etiquetas de Trello) — 6, mínimo exigido 4

| Etiqueta | Épica | Historias |
|---|---|---|
| `E1` (verde) | Monitoreo y adquisición de datos IoT | SIGA-1, SIGA-2, SIGA-3, SIGA-4, SIGA-5 |
| `E2` (amarillo) | Control remoto y automatización energética | SIGA-6, SIGA-7, SIGA-8, SIGA-9, SIGA-10 |
| `E3` (naranja) | Alertas y gestión de mantenimiento | SIGA-11, SIGA-12, SIGA-13, SIGA-14, SIGA-15, SIGA-16 |
| `E4` (azul) | Reportes, analítica e IA | SIGA-17, SIGA-18, SIGA-19 |
| `E5` (morado) | Seguridad, acceso y auditoría | SIGA-20, SIGA-21 |
| `E6` (rojo) | Cumplimiento LOPDP | SIGA-22, SIGA-23, SIGA-24 |

## 3. Historias — 24, mínimo exigido 15

Una tarjeta por requisito funcional relevante. Cada tarjeta lleva en el título su clave (`SIGA-nn`) y en la descripción la historia en formato Connextra corregida (defecto D-10). Detalle completo en `backlog_export.csv`.

## 4. Sub-tareas por criterio de aceptación — 14 en 6 historias, mínimo exigido 2 en 5 historias

| Historia | Sub-tareas (checklist «Criterios de aceptación») |
|---|---|
| SIGA-1 | SIGA-1.1, SIGA-1.2 |
| SIGA-5 | SIGA-5.1, SIGA-5.2, SIGA-5.3 |
| SIGA-9 | SIGA-9.1, SIGA-9.2, SIGA-9.3 |
| SIGA-12 | SIGA-12.1, SIGA-12.2 |
| SIGA-22 | SIGA-22.1, SIGA-22.2 |
| SIGA-24 | SIGA-24.1, SIGA-24.2 |

## 5. Campos personalizados — 3 configurados, mínimo exigido 2

| Campo | Tipo en Trello | Valores | Uso |
|---|---|---|---|
| **Prioridad MoSCoW** | Lista desplegable | Must / Should / Could / Won't | Obligatorio por la guía. Refleja la sección 5.2 del ERS, ya con RF-24 y RF-25 elevados a Must por la RFC-03. |
| **Fuente del requisito** | Texto | `EV-nn`, `RC-nn`, `LOPDP Art. nn`, `RFC-nn`, `D-nn` | Obligatorio por la guía. Es el **enlace hacia atrás**: cada tarjeta declara el stakeholder o documento del que procede. |
| **Estado de verificación** | Lista desplegable | Verificado en MVP / Parcialmente sustentado / No verificado / Pendiente 2B / Nuevo por RFC | Campo valorado como tercero. Reproduce en el tablero la columna «Estado de validación» de la tabla de RNF del ERS, que es el punto más fuerte del documento inspeccionado. |

## 6. Trazabilidad bidireccional

Cada tarjeta lleva dos bloques de enlaces visibles en su descripción:

- **Hacia atrás (pre-traceability):** stakeholder, evidencia `EV-nn`, requisito crudo `RC-nn`, artículo de la LOPDP o defecto `D-nn` que la originó. Corresponde a la columna `Enlace-hacia-atras` del CSV.
- **Hacia adelante (post-traceability):** caso de uso `CU-nn`, clase o módulo del diagrama de clases refinado, mockup `MU-nn` y caso de prueba `PR-nn`. Corresponde a la columna `Enlace-hacia-adelante` del CSV.

**Requisitos huérfanos identificados y reportados explícitamente:**

| Requisito | Dirección faltante | Tratamiento |
|---|---|---|
| RF-06 | Sin mockup asociado | Se acepta: la vista de cámara se embebe en MU-01, no tiene pantalla propia. |
| RF-09, RF-14 | Sin historia de usuario | Coherente: son *Should*, y el ERS solo redacta historias para los *Must*. Se declara, no se oculta. |
| NFR-06, NFR-09 | Sin caso de uso | Coherente: son requisitos de mantenibilidad y flexibilidad del proceso de desarrollo, no de operación. |
| RF-24, RF-25 | Sin `ID-EV` (sin evidencia de campo) | **Huérfanos reales hacia atrás.** Se sustentan solo en análisis normativo; el ERS lo reconoce. Acción abierta A-01 del CCB. |
| RF-28, RF-29, RF-30 | Sin caso de prueba ejecutado | Recién formalizados desde los «candidatos» del catálogo B.1 (defecto D-15). Pendientes de 2B. |

## 7. Capturas requeridas (Anexo E)

Las capturas deben tomarse desde las cuentas de las integrantes, con el nombre del tablero y la cuenta visibles. Véase `capturas/LEEME_CAPTURAS.md`.
