# git diff

```bash
git diff
```

Este comando compara los cambios entre el directorio de trabajo y el staging area, mostrando exactamente qué líneas cambiaron en los archivos. Las líneas en rojo con `-` son las que se eliminaron, y las verdes con `+` son las que se agregaron. 



```bash
git diff --staged
git diff rama1 rama2
git diff hash1 hash2
git diff --name-only
git diff --stat
```
El primer comando compara el staging area (los archivos agregados con git add) contra el último commit. El segundo compara dos ramas completas y muestra las diferencias linea por linea. El tercero compara dos commits por sus respectivos hash esten en la misma rama o en distintas ramas. El cuarto muestra solo los nombres de los archivos que cambiaron en el working directory contrastado al staging area.El ultimo muestra un resumen estadístico de los cambios, no el detalle línea por línea.

## Ejemplo de salida de `git diff`

```diff
diff --git a/comandos/git-init.md b/comandos/git-init.md
index 3a1b2c4..8f2e1d3 100644
--- a/comandos/git-init.md
+++ b/comandos/git-init.md
@@ -10,7 +10,7 @@ git init convierte una carpeta en un repositorio Git.
 ## Uso básico
 
-git init nombre
+git init nombre-del-proyecto
 
```

## comandos de ayuda
```bash
git diff --help
man git-diff
```
El primer comando muestra la ayuda que trae git para "git diff". El segundo el manual completo delsistema mas detallado.