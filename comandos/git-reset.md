# git reset

## ¿Qué hace?

`git reset` mueve HEAD hacia un commit anterior deshaciendo commits del historial. Según el modo que uses también puede afectar el staging area y los archivos en tu directorio de trabajo.

Es potente pero hay que usarlo bien porque modifica el historial.

## Los tres modos

### --soft

Solo mueve HEAD. Los cambios de los commits deshechos quedan en el staging area listos para volver a commitear.

```bash
git reset --soft HEAD~1
```

Sirve cuando queres deshacer el último commit pero no perder los cambios, por ejemplo para rehacerlo con un mensaje distinto.

### --mixed (el modo por defecto)

Mueve HEAD y vacía el staging area. Los cambios quedan en tu directorio de trabajo como archivos modificados pero sin preparar.

```bash
git reset HEAD~1
# es lo mismo que:
git reset --mixed HEAD~1
```

Sirve cuando queres deshacer un commit y reorganizar los cambios antes de volver a commitear.

### --hard

Mueve HEAD, vacia el staging area y descarta los cambios del directorio de trabajo. O sea los cambios desaparecen.

```bash
git reset --hard HEAD~1
```

Sirve cuando queres tirar todo a la basura y volver al estado de un commit anterior.

## Resumen visual

| Modo      | HEAD | Staging area | Working directory |
|-----------|------|--------------|-------------------|
| --soft  | mueve | no toca | no toca |
| --mixed | mueve | limpia | no toca |
| --hard  | mueve | limpia | limpia y borra |

## Ejemplos prácticos

```bash
# Deshacer el último commit pero conservar los cambios en staging
git reset --soft HEAD~1

# Sacar un archivo del staging sin perder los cambios
git reset HEAD archivo.md
# forma mas moderna:
git restore --staged archivo.md

# Volver al estado exacto del último commit
git reset --hard HEAD

# Ir a un commit específico por hash
git reset --hard abc1234
```

## Ver el hash de commits anteriores

```bash
git log --oneline
```

## Diferencia con git revert

| Comando       | Modifica historial | Crea nuevo commit | Seguro en ramas compartidas |
|---------------|--------------------|-------------------|-----------------------------|
| git reset   | si | no | no |
| git revert  | no | si | si |

Si ya hiciste push del commit que queres deshacer usa `git revert` en vez de reset para no reescribir el historial remoto y no romperle el trabajo a nadie.

## Notas

- `git reset --hard` es prácticamente irreversible si no tenes los cambios guardados en otro lado se van para siempre.
- Antes de usarlo fijate bien en qué commit estás con `git log --oneline` para no equivocarte de punto de destino.
  
### [volver al indice](../indice.md) 