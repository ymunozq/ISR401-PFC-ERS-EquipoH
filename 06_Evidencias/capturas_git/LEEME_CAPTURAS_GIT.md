# Anexo E — Capturas del repositorio Git (pendientes de tomar por el equipo)

> Las capturas deben tomarse en la máquina de las integrantes **después de publicar el repositorio en GitHub**, y deben mostrar el terminal o la interfaz de GitHub con la cuenta visible. No se generan automáticamente: el criterio de admisión **A2** exige capturas propias.

## Capturas obligatorias

| Archivo esperado | Comando o vista | Qué debe verse |
|---|---|---|
| `01_git_log_graph.png` | `git log --oneline --graph --decorate` | El historial completo con los ≥8 commits semánticos, el grafo y la decoración del *tag* `baseline-v1.1` sobre el commit correspondiente. Debe verse la ruta del repositorio en el prompt. |
| `02_git_tag_n.png` | `git tag -n` | El *tag* anotado `baseline-v1.1` con su mensaje `Baseline aprobada por CCB`. |
| `03_git_shortlog.png` | `git shortlog -sne` | El reparto de autoría por integrante, que es lo que el criterio A3 y el FAI contrastan. |
| `04_github_releases.png` | Pestaña *Tags/Releases* del repositorio en GitHub | El *tag* `baseline-v1.1` publicado en el remoto, con la cuenta de la integrante visible en la barra superior. |

## Comandos para publicar y capturar

El repositorio local ya está inicializado, con el historial y el *tag* creados. Para publicarlo:

```bash
git remote add origin https://github.com/<usuario>/ISR401-PFC-ERS-EquipoH.git
```

```bash
git push -u origin main
```

```bash
git push origin baseline-v1.1
```

Y para generar las vistas que deben capturarse:

```bash
git log --oneline --graph --decorate
```

```bash
git tag -n
```

```bash
git shortlog -sne
```

## Verificación antes de entregar

- [ ] El repositorio remoto es **público** (criterio de piso G1: si la URL está rota o el repositorio no es accesible, la calificación es CERO).
- [ ] El *tag* `baseline-v1.1` aparece en la pestaña *Tags* de GitHub, no solo en local (error frecuente §13 de la guía).
- [ ] La versión `v1.1` se lee idéntica en la portada del informe, en el `CHANGELOG.md` y en el *tag*.
- [ ] `git shortlog -sne` muestra aportes de **ambas** integrantes.
- [ ] Cada integrante ha verificado y, si procede, rehecho desde su propia máquina los commits que le corresponden antes de publicar.
