# git commit

```bash
git commit -m "tipo: descripción breve del cambio"
```

Este comando guarda de forma permanente los cambios que están en el *staging area* dentro del historial del repositorio con un identificador unico (hash).

Ademas es la forma convencional (Conventional Commits) con la cual se escribe este comando.

Los tipos más comunes son:

| Tipo       | Cuándo usarlo                                      |
|------------|----------------------------------------------------|
| `feat`     | Se agrega una nueva funcionalidad                  |
| `fix`      | Se corrige un error                                |
| `docs`     | Cambios en documentación                           |
| `style`    | Formateo, espacios, punto y coma (sin lógica)      |
| `refactor` | Reestructuración sin cambiar comportamiento        |
| `revert`   | Se deshace un commit anterior                      |
| `chore`    | Tareas de mantenimiento, configuración             |


## Variantes útiles

```bash
git commit
git commit -a -m "fix: corregir typos generales"
git commit --amend -m "mensaje corregido"
git commit --no-verify -m "chore: commit de emergencia"
```
El primer comando abre el editor de texto(nano,vim) para escribir el mensaje y guardar los cambios en el repositorio, el segundo permite guardar todos los archivos modificados , eliminados y ademas escribir el mensaje en consola entre comillas. El tercero  permite modificar el ultimo commit y tanto en los archivos como en el mensaje, el ultimo permite guardar sin verificaciones (hooks) de Git.

  
### [volver al indice](../indice.md) 
