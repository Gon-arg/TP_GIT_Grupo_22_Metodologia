# git revert

## ¿Que hace?

`git revert` deshace los cambios de un commit anterior creando un commit nuevo que aplica el efecto inverso. A diferencia de `git reset` no reescribe el historial sino que agrega un commit que cancela al que queres deshacer.

Por eso es el comando mas seguro para usar en ramas compartidas o en commits que ya subiste con push.

## Uso basico

```bash
# Revertir el ultimo commit
git revert HEAD

# Revertir un commit especifico por su hash
git revert abc1234
```

Git abre el editor de texto para que confirmes o edites el mensaje del commit de revert. Si no queres que lo abra:

```bash
git revert abc1234 --no-edit
```

## Revertir multiples commits

```bash
# Revertir los ultimos 3 commits, crea un commit de revert por cada uno
git revert HEAD~3..HEAD

# Revertir un rango pero agrupar todo en un solo commit
git revert --no-commit HEAD~3..HEAD
git commit -m "revert: deshacer los ultimos 3 commits"
```

## ¿Que pasa si hay conflictos?

Si el commit que queres revertir toca las mismas lineas que commits posteriores puede haber conflictos. El proceso es igual que en un merge:

1. Resolver los conflictos a mano
2. `git add archivo-resuelto.md`
3. `git revert --continue`

Para cancelar todo:

```bash
git revert --abort
```

## Ejemplo completo

```bash
git log --oneline
# abc1234 feat: agregar seccion de ejemplos en git-reset
# def5678 docs: corregir encabezado
# ghi9012 feat: explicacion inicial de git-reset

# Me di cuenta de que abc1234 introdujo un error
git revert abc1234
# Se crea un nuevo commit: "Revert 'feat: agregar seccion de ejemplos en git-reset'"
```

## reset vs revert: ¿cuando usar cada uno?

| Situacion | Usar |
|-----------|------|
| Deshacer commits locales que nadie mas tiene | git reset |
| Deshacer commits ya pusheados o en ramas compartidas | git revert |
| Quiero mantener el historial intacto | git revert |

## Notas

- `git revert` es el comando de deshacer mas seguro porque nunca toca el historial existente.
- En este proyecto es uno de los tipos de commits requeridos asi que tiene que aparecer al menos una vez en el historial.
- El mensaje del commit de revert deberia seguir la convencion: `revert: descripcion de lo que se deshace`.