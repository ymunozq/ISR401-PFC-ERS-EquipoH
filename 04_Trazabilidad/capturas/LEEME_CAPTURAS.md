# Capturas del tablero CASE — pendientes de tomar por el equipo

> **Estas capturas NO pueden generarse automáticamente.** La guía exige en el criterio de admisión **A2 (Autenticidad de las evidencias)** que sean capturas propias del tablero del equipo, con las cuentas de las integrantes visibles. Una imagen sintética o de terceros activa el criterio A2 y, en el peor caso, el nivel S4 de la escala de uso indebido de IA.
>
> El contenido que deben mostrar ya está definido y es reproducible: cárguese `../backlog_export.csv` en Trello (Menú → Más → Importar) o créense las tarjetas manualmente según `../tablero_definicion.md`.

## Capturas obligatorias

| Archivo esperado | Contenido | Requisito de la guía |
|---|---|---|
| `01_tablero_completo.png` | Vista del tablero con las 5 listas (Backlog, Análisis, Aprobado, Desarrollo, Hecho) y las 24 tarjetas visibles. Deben verse el nombre del tablero y el avatar/cuenta de la integrante. | Paso 3.5 — «capturas del tablero completo» |
| `02_detalle_SIGA-5.png` | Tarjeta SIGA-5 abierta, mostrando: campos personalizados (Prioridad MoSCoW, Fuente del requisito, Estado de verificación), checklist de criterios de aceptación (SIGA-5.1 a 5.3) y los enlaces hacia atrás (EV-15, RFC-02) y hacia adelante (CU-01, CU-12, MU-01, PR-47). | Paso 3.5 — «detalle de al menos 3 issues con sus enlaces visibles» |
| `03_detalle_SIGA-9.png` | Tarjeta SIGA-9 abierta con sus 3 sub-tareas y los enlaces D-23 → RFC-01 → CU-13 → ExcepcionApagado → PR-31. Es la tarjeta que demuestra la trazabilidad desde el defecto detectado hasta el caso de prueba. | Paso 3.5 |
| `04_detalle_SIGA-24.png` | Tarjeta SIGA-24 abierta con los enlaces LOPDP Art. 43/46 → D-13 → RFC-03 → CU-17 → PR-27/PR-49. Es la tarjeta que demuestra la trazabilidad de una obligación legal. | Paso 3.5 |
| `05_panel_estadisticas.png` | Panel de estadísticas / vista de tablero por etiqueta o por campo personalizado, mostrando la distribución de tarjetas por épica y por prioridad MoSCoW. | Paso 3.5 — «panel de estadísticas» |
| `06_campos_personalizados.png` | Configuración de los tres campos personalizados (Power-Up Custom Fields), mostrando nombre, tipo y valores de cada uno. | Paso 3.3 — «dos campos personalizados configurados y usados» |

## Verificación antes de entregar

- [ ] En cada captura se lee el nombre del tablero `SIGA — Sistema Inteligente de Gestión de Aulas (ISR-401)`.
- [ ] En cada captura es visible la cuenta de la integrante que la tomó (avatar o correo institucional).
- [ ] La captura `01` muestra las cinco listas y no está recortada.
- [ ] Las capturas `02`, `03` y `04` muestran **los dos sentidos** de la trazabilidad, no solo uno.
- [ ] El CSV exportado desde Trello se guarda como `../backlog_export_trello.csv` junto al CSV de origen, para poder contrastarlos.
- [ ] Los archivos se nombran exactamente como indica la tabla y se versionan con un commit propio.
