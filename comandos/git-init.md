# git init


```bash
git init
```
El comando convierte una carpeta común en un repositorio Git. Al ejecutarlo se crea una carpeta oculta llamada **.git** dentro del directorio actual, que es donde se guarda todo el historial.

## Ejemplo 

```bash
mkdir mi-proyecto
cd mi-proyecto
git init

```
En este ejemplo se crea primero una carpeta para el proyecto, luego se ingresa a esa carpeta y por ultimo se inicializa git (se crea el repositorio). A partir de ahí ya se puede empezar a agregar archivos y hacer commits.
Si ya existe un repositorio en la carpeta y se ejecuta el comando, **git init** no lo borra ni lo sobreescribe solo lo reinicializa.
Para empezar a trabajar con un repositorio **remoto existente**, conviene usar **git clone** en lugar de **git init**.
