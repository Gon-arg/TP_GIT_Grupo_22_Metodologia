# git log

```bash
git log
```
Este comando muestra el historial de commits de la rama actual, del más reciente al más antiguo, mostrando el hash completo, el autor, la fecha y el mensaje.

## Variantes 

```bash
git log --oneline
git log --oneline --graph
git log --oneline --graph --all
git log -5
git log --oneline -- comandos/git-init.md
git log --author="Nombre"
git log --after="2024-01-01" --before="2024-12-31"
git log --stat
git log -p
```
El primer comando lista el historial de la rama actual con un hash corto y el mensaje por commit. EL segundo muestra el historial de la rama actual con un gráfico ASCII que representa bifurcaciones y merges. El tercero lista el historial de todas las ramas del repositorio, incluyendo el gráfico de cómo se relacionan entre sí. EL cuarto muestra únicamente los últimos 5 commits de la rama actual. EL quinto muestra solo los commits que modificaron ese archivo específico. EL sexto lista los commits realizados por un autor determinado. EL septimo filtra los commits hechos dentro de un rango de fechas. El octavo muestra un resumen estadístico de los archivos modificados en cada commit (cantidad de líneas agregadas/eliminadas). El ultimo muestra el detalle completo línea por línea de los cambios introducidos en cada commit.

## comandos de ayuda

```bash
git log --help
man git-log
```
EL primero da una ayuda resumida. EL segundo da el manual completo del sistema respecto de git log.

## Ejemplo de salida de `git log --oneline --graph --all`

```bash
* 3a1b2c4 (HEAD -> main) feat: agregar explicación de git push
* 8f2e1d3 feat: agregar explicación de git pull
| * 1c3d5e7 (feat/git-rebase) feat: agregar explicación de git rebase
|/
* 9a7b6c5 feat: agregar explicación de git merge
```

Cada `*` es un commit. Las líneas y ramas muestran cómo se bifurca y une el historial.
