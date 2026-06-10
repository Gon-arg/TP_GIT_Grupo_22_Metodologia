# git add

Git tiene tres zonas de trabajo:

1. **Working directory**: donde se editan los archivos
2. **Staging area**: donde se preparan los cambios que van al próximo commit
3. **Repositorio**: el historial permanente de commits

Este comando lo que hace es agregar cambios al **área de preparación** (también llamada *staging area* o *índice*).

## variantes

```bash
git add archivo.md
git add archivo1.md archivo2.md
git add .
git add -u
git add -A
git add -p archivo.md
```
El primer comando agrega un archivo especifico, el segundo agrega varios archivos, el tercero agrega todos los cambios, el cuarto agrega todos los archivos modificados o eliminados que hayan estado en el ultimo commit, y el quinto agrega todos los archivos nuevos, modificados o eliminados. El ultimo  te permite agregar una parte del archivo.
  
   
 ### [volver al indice](../indice.md) 