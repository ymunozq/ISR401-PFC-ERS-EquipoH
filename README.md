# ISR401-PFC-ERS-EquipoH

**Práctica Experimental PE4 — Unidad IV**
Validación, Gestión de Requisitos y Herramientas CASE
Ingeniería de Requerimientos (ISR-401) · UTEQ · 2026–2027 PPA

---

## Sistema del Proyecto Fin de Curso

**SIGA — Sistema Inteligente de Gestión de Aulas** (equipo FGMMN)
Plataforma de monitoreo, automatización y apoyo a la decisión operativa en las aulas de la Facultad de Ciencias de la Computación, basada en sensores IoT e inteligencia artificial.

**Artefacto inspeccionado:** ERS/SRS de la Entrega 2A, versión v1.0 (122 páginas)
**Origen:** https://github.com/gsanchezc6-beep/SIGA_FGMMN_ISR401_AVANCE_2A — commit `bb04d43`
**Versión resultante:** **v1.1**, línea base publicada como *tag* `baseline-v1.1`

## Equipo H

| Integrante | C.I. | Correo | Roles |
|---|---|---|---|
| Muñoz Quiñonez Yeranick Esther | 1207929645 | ymunozq@uteq.edu.ec | Moderadora de la inspección · Presidenta y Analista del CCB |
| Chavarria Cuenca Tahiny Mel | 0943050054 | tchavarriac@uteq.edu.ec | Lectora · Inspectora 1 · Inspectora 2 · Representante del cliente y Desarrolladora del CCB |

**Integrante titular del PFC:** Muñoz Quiñonez Yeranick Esther es integrante del equipo FGMMN, autor del ERS inspeccionado, en el que desempeña el rol de Documentadora (Anexo A.1 del ERS).

**Limitación declarada.** La guía exige los cuatro roles de la inspección en cuatro personas distintas (criterio A3). El Equipo H tiene dos integrantes; los roles de Lectora e Inspectoras recaen en la misma persona por autorización docente. Se mitigó ejecutando los pases I1 e I2 en fechas distintas, en sesiones separadas y sobre alcances disjuntos del documento. La desviación se declara en el acta de inspección, en los tres Anexos A, en el acta del CCB y en las secciones 4 y 12 del informe.

## Resultados

| Concepto | Valor |
|---|---|
| Defectos únicos consolidados | 29 (4 críticos, 19 mayores, 6 menores) |
| Densidad de defectos | 0,238 def./página sobre 122 páginas |
| Tipo dominante | Consistencia (34,5 %), seguido de Trazabilidad (24,1 %) |
| Esfuerzo de inspección | 10,0 horas-persona · eficiencia 2,9 def./h-persona |
| Correcciones aplicadas | 100 % de críticos y mayores (23 de 23) |
| RFC tramitadas | 3, todas derivadas de defectos reales de la inspección |
| Filas de la matriz de trazabilidad | 58 |

## Estructura del repositorio

```
ISR401-PFC-ERS-EquipoH/
├── README.md
├── CHANGELOG.md
├── 01_ERS/
│   ├── ERS_SIGA_v1.0.pdf              artefacto inspeccionado (122 pág.)
│   ├── ERS_SIGA_v1.0_main.tex         fuente principal de la v1.0
│   ├── ERS_SIGA_v1.0_secciones.tex    cuerpo de la v1.0 (2 256 líneas)
│   └── ERS_SIGA_v1.1_delta.tex        bloques corregidos, con la línea que reemplazan
├── 02_Inspeccion/
│   ├── AnexoA_checklists/             una lista de verificación por inspector
│   ├── AnexoB_registro_defectos.csv   registro consolidado de los 29 defectos
│   ├── Acta_Reunion_Inspeccion.md
│   ├── correcciones_aplicadas.csv     23 correcciones con texto antes/después
│   ├── metricas.csv                   M1–M5 con su interpretación
│   └── registro_horas_preparacion.csv
├── 03_CCB/
│   ├── RFC-01.md  RFC-02.md  RFC-03.md
│   └── Acta_CCB.md
├── 04_Trazabilidad/
│   ├── matriz_trazabilidad.csv        58 filas (Anexo D)
│   ├── matriz_trazabilidad_ERS_v1.0_original.csv   matriz original, para contraste
│   ├── backlog_export.csv             6 épicas, 24 historias, 14 sub-tareas
│   ├── tablero_definicion.md
│   └── capturas/                      capturas del tablero (Anexo E)
├── 05_Informe/
│   ├── PE4_U4_MUNOZ_CHAVARRIA.tex
│   ├── PE4_U4_MUNOZ_CHAVARRIA.pdf
│   ├── referencias.bib
│   └── figuras/
└── 06_Evidencias/
    ├── capturas_git/                  Anexo E — historial y tag
    ├── fotos_sesion/
    └── declaracion_IA.md              Anexo F
```

## Instrucciones de compilación del informe

**Compilador:** pdfLaTeX (probado con MiKTeX 24.x en Windows 11).
**Archivo principal:** `05_Informe/PE4_U4_MUNOZ_CHAVARRIA.tex`
**Dependencias:** paquetes de una distribución LaTeX estándar — `inputenc`, `fontenc`, `babel` (spanish), `geometry`, `graphicx`, `float`, `longtable`, `array`, `booktabs`, `amssymb`, `xcolor` (opción `table`), `enumitem`, `fancyhdr`, `titlesec`, `lastpage`, `tikz`, `hyperref`. El estilo bibliográfico es `ieeetr`, incluido en toda distribución LaTeX.
**Archivo de bibliografía:** `05_Informe/referencias.bib` (15 entradas, todas citadas en el texto).

Orden de comandos, desde la carpeta `05_Informe/`:

```bash
pdflatex PE4_U4_MUNOZ_CHAVARRIA.tex
```

```bash
bibtex PE4_U4_MUNOZ_CHAVARRIA
```

```bash
pdflatex PE4_U4_MUNOZ_CHAVARRIA.tex
```

```bash
pdflatex PE4_U4_MUNOZ_CHAVARRIA.tex
```

Las tres pasadas de `pdflatex` son necesarias: la primera genera los auxiliares, `bibtex` resuelve las citas y las dos siguientes fijan la bibliografía, el índice y las referencias de página (`lastpage`). Alternativamente, `latexmk -pdf PE4_U4_MUNOZ_CHAVARRIA.tex` ejecuta la secuencia completa.

**Nota sobre las figuras.** Los gráficos de las métricas M2 y M3 se dibujan con TikZ dentro del propio `.tex`; no dependen de archivos de imagen externos, de modo que el PDF se reproduce por clonación del repositorio sin ningún recurso adicional.

## Pendientes antes de la entrega al SGA

- [x] Crear el repositorio remoto público y publicarlo: https://github.com/ymunozq/ISR401-PFC-ERS-EquipoH — `main` y el *tag* `baseline-v1.1` ya están en GitHub.
- [ ] **Recompilar `PE4_U4_MUNOZ_CHAVARRIA.pdf`** — el `.tex` se corrigió después de generar el PDF actual (conteo de *commits* en la sección de línea base); el PDF del repositorio está desactualizado en ese detalle hasta la próxima compilación.
- [ ] Construir el tablero en Trello a partir de `04_Trazabilidad/backlog_export.csv` y tomar las capturas listadas en `04_Trazabilidad/capturas/LEEME_CAPTURAS.md`.
- [ ] Tomar las capturas de Git listadas en `06_Evidencias/capturas_git/LEEME_CAPTURAS_GIT.md` (ahora con el historial ya publicado).
- [ ] Tomar las fotografías de sesión listadas en `06_Evidencias/fotos_sesion/LEEME_FOTOS.md`.
- [ ] Firmar los tres Anexos A, el acta de inspección, el acta del CCB y la declaración de IA.
- [ ] Subir `PE4_U4_MUNOZ_CHAVARRIA.pdf` (recompilado) al SGA en la Semana 14.

## Referentes

ISO/IEC/IEEE 29148:2018 §6.4 · ISO/IEC/IEEE 15288:2023 · ISO/IEC/IEEE 12207:2017 · ISO/IEC 25010:2023 · Pohl (2025), Parte V · SWEBOK v4.0 §1.6–1.8 · PMBOK 7.ª ed. · IREB CPRE FL v3.1 · Fagan (1976) · Cohn (2004) · Smart (2014) · Gotel y Finkelstein (1994) · Cleland-Huang et al. (2012) · Wiegers y Beatty (2013).
