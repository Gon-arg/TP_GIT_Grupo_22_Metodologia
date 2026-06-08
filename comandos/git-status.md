```markdown
# git status

## ¿Que hace?

`git status` te muestra en que rama estas, que archivos cambiaron, cuales estan en el staging area listos para commitear y cuales son nuevos y Git todavia no los rastrea.

Es el comando que mas se usa en el dia a dia porque te da una foto rapida de que esta pasando antes de hacer `git add` o `git commit`.

## Uso basico

```bash
git status
```

## Ejemplo de salida

```
On branch feat/git-status
Your branch is up to date with 'origin/feat/git-status'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   comandos/git-init.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   comandos/git-clone.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        comandos/git-status.md
```

La salida se divide en tres zonas:

| Zona | Que significa |
|------|---------------|
| Changes to be committed | Archivos en staging listos para el proximo commit |
| Changes not staged | Archivos modificados a los que todavia no les hiciste git add |
| Untracked files | Archivos nuevos que Git aun no rastrea |

## Version corta

```bash
git status -s
```

Muestra lo mismo pero compacto. Dos columnas: la primera es el estado en staging, la segunda en el directorio de trabajo.

```
M  comandos/git-init.md    <- modificado y en staging
 M comandos/git-clone.md   <- modificado pero NO en staging
?? comandos/git-status.md  <- sin seguimiento
```

## Cuando usarlo

- Antes de `git add` para ver que cambio
- Antes de `git commit` para confirmar que va a entrar
- Despues de un `git merge` o `git rebase` para ver si quedo algun conflicto sin resolver
- Cada vez que no tengas claro en que estado esta el repo

## Notas

- `git status` nunca modifica nada, es solo lectura. Podes ejecutarlo las veces que quieras sin ningun riesgo.
- Si ves "nothing to commit, working tree clean" significa que no hay nada pendiente.
```