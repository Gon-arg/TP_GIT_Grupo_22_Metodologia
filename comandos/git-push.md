```markdown
# git push

## ¿Que hace?

`git push` sirve para subir tus commits al repositorio remoto. Basicamente es el paso que hace que tus cambios dejen de existir solo en tu maquina y pasen a ser visibles para el resto del equipo (o en GitHub).

La diferencia con `git commit` es que este ultimo solo guarda los cambios de forma local. El `push` es lo que los publica.

## Uso basico

```bash
# Subir la rama actual a su rama remota correspondiente
git push

# Especificar remoto y rama
git push origin nombre-de-la-rama
```

## Primera vez que subis una rama nueva

Si la rama aun no existe en el remoto Git no sabe a donde mandarla asi que hay que decirle que la cree y empiece a hacerle seguimiento:

```bash
git push -u origin nombre-de-la-rama
# o equivalente:
git push --set-upstream origin nombre-de-la-rama
```

Despues de ese primer push ya con escribir solo `git push` alcanza.

## Variantes utiles

```bash
# Subir todos los tags locales
git push --tags

# Eliminar una rama remota
git push origin --delete nombre-de-la-rama

# Forzar el push (sobreescribe el historial remoto)
git push --force

# Forzar pero solo si nadie mas subio nada desde tu ultimo fetch (mas seguro)
git push --force-with-lease
```

## ¿Cuando falla el push?

Si alguien del equipo subio cambios al remoto antes que vos Git te va a rechazar el push para no pisarlos:

```
! [rejected] main -> main (fetch first)
```

En ese caso lo que hay que hacer es un `git pull` primero (o `git pull --rebase`) resolver los conflictos si aparece alguno y recien ahi volver a intentar el push.

## Sobre el force push

`git push --force` reescribe el historial remoto lo que puede hacer que otros miembros del equipo pierdan commits. Usarlo solo en ramas personales que nadie mas este tocando.

Si necesitas forzar el push `--force-with-lease` es la opcion mas segura: falla automaticamente si alguien subio algo desde la ultima vez que hiciste fetch asi no pisas trabajo ajeno sin querer.

## Notas

- En este proyecto cada rama feature se sube con push para luego abrir un **Pull Request** en GitHub.
- Nunca hacer force push sobre `main`.

  
### [volver al indice](../indice.md) 