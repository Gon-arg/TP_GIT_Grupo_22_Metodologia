# git clone

```bash
git clone <url-del-repositorio>
```

El comando descarga una copia completa de un repositorio remoto en la carpeta local. No solo trae los archivos actuales, sino **todo el historial de commits**, las ramas y las etiquetas.

```bash
git clone <url> nombre-personalizado

git clone --branch nombre-rama <url>

git clone --depth 1 <url>
```
Estos son algunas variantes del comando, en el primer caso deja cambiarle el nombre a la carpeta que viene del remoto para tenerla con un nombre mas personalizado en el repositorio local. El segundo comando permite clonar solo una rama especifica del proyecto remoto. La tercer variante permite descargar el proyecto pero solo con el ultimo commit, si se quiere los ultimos dos se cambia el numero 1 a 2 y asi sucesivamente.


```bash
git init
git remote add origin <url>
git fetch origin
git checkout main
```

Estos cuatro comandos son el equivalente a ejecutar `git clone`. Por ultimo este comando se ejecuta sin inconvenientes cuando el repositorio es publico, y cuando es privado Git solicita alguna autenticacion o token.

  
 ### [volver al indice](../indice.md) 