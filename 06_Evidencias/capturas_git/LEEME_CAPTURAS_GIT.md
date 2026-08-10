# Anexo E — Capturas del repositorio Git (pendientes de tomar por el equipo)

> Las capturas deben tomarse en la máquina de las integrantes **después de publicar el repositorio en GitHub**, y deben mostrar el terminal o la interfaz de GitHub con la cuenta visible.

## Capturas obligatorias

| Archivo esperado | Comando o vista | Qué debe verse |
|---|---|---|
| `01_git_log_graph.png` | `git log --oneline --graph --decorate` | El historial completo con los ≥8 commits semánticos, el grafo y la decoración del *tag* `baseline-v1.1` sobre el commit correspondiente. Debe verse la ruta del repositorio en el prompt. |
| `02_git_tag_n.png` | `git tag -n` | El *tag* anotado `baseline-v1.1` con su mensaje `Baseline aprobada por CCB`. |
| `03_git_shortlog.png` | `git shortlog -sne` | El reparto de autoría por integrante, que es lo que el criterio A3 y el FAI contrastan. |
| `04_github_releases.png` | Pestaña *Tags/Releases* del repositorio en GitHub | El *tag* `baseline-v1.1` publicado en el remoto, con la cuenta de la integrante visible en la barra superior. |
