# git pull

## ¿Qué hace?

`git pull` trae los cambios que hay en el repositorio remoto y los mete en tu rama local.En realidad es un atajo para dos comandos que van siempre juntos:

```bash
git fetch   # Descarga los cambios sin tocar nada todavía
git merge   # Los une con lo que tenés en tu rama
```

Básicamente: va al servidor, agarra lo nuevo, y lo une con tu trabajo.

## Uso básico

```bash
# La forma mas comun, trae y mergea lo que haya en tu rama remota
git pull

# Si queres ser mas explicito con el remoto y la rama
git pull origin main
```

## Variantes

```bash
# En vez de hacer merge, reaplica tus commits encima de los remotos
git pull --rebase
```

>  `--dry-run` no existe en `git pull`. Si querés ver qué hay antes de integrar, usá `git fetch`.

### pull con rebase

```bash
git pull --rebase origin main
```

Esto sirve cuando simplemente queres ponerte al dia con el remoto sin generar un commit de merge extra.El historial queda mas prolijo  como si tus cambios siempre hubieran sido los últimos.

## ¿Cuándo puede fallar?

Si tenes cambios locales sin commitear que pisan los mismos archivos que los remotos, Git se va a frenar y te va a pedir que resuelvas el conflicto. La salida más limpia en ese caso:

```bash
git stash          # Guardás tus cambios temporalmente
git pull           # Traés lo del remoto sin drama
git stash pop      # Recuperás lo que habías guardado
```

## Ver qué hay en el remoto antes de integrar

Si no queres llevarte sorpresas, podés mirar primero:

```bash
git fetch origin
git log HEAD..origin/main --oneline  # Los commits que están allá y acá no tenés
```

## Configurar cómo se comporta por defecto

```bash
# Que siempre use rebase en vez de merge
git config --global pull.rebase true

# Que siempre use merge (el comportamiento por defecto de Git)
git config --global pull.rebase false
```

## fetch vs pull: ¿cuál usar?

| Comando      | ¿Descarga? | ¿Integra? |
|--------------|------------|-----------|
| `git fetch`  | ✅          | ❌         |
| `git pull`   | ✅          | ✅         |

`git fetch` te da mas control: descarga todo pero no toca tu rama hasta que vos decidas. Si trabajas con gente o en algo delicado, a veces vale la pena ese paso extra.

## Algunas buenas costumbres

- Antes de ponerte a codear, hace `git pull`. Antes de hacer `git push`, tambien.
- Si estas en una rama feature que lleva varios dias  de vez en cuando actualizá `main` con pull. Asi los conflictos al mergear son muchos menos.