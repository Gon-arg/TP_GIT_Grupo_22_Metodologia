```markdown
# Herramientas de terminal

Aca se agrupan algunos comandos de terminal que se usan bastante junto con Git en el dia a dia.

---

## ls

`ls` lista los archivos y carpetas del directorio donde estas parado.

```bash
# Listar archivos del directorio actual
ls

# Listar con detalles como permisos, tamaño y fecha
ls -l

# Incluir archivos ocultos como .git
ls -a

# Los dos combinados
ls -la
```

Ejemplo de salida:
```
total 24
drwxr-xr-x  4 usuario  staff  128 Jan  1 12:00 .
drwxr-xr-x  8 usuario  staff  256 Jan  1 11:00 ..
drwxr-xr-x  9 usuario  staff  288 Jan  1 12:00 .git
drwxr-xr-x  3 usuario  staff   96 Jan  1 12:00 comandos
-rw-r--r--  1 usuario  staff  420 Jan  1 12:00 indice.md
```

---

## nano

`nano` es un editor de texto que corre dentro de la terminal. Es el mas facil de usar si no queres salir de la linea de comandos para editar algo.

```bash
# Abrir o crear un archivo
nano nombre-archivo.md
```

Los controles basicos se muestran en la parte de abajo de la pantalla:

| Atajo | Accion |
|-------|--------|
| Ctrl + O | Guardar el archivo |
| Enter | Confirmar el nombre al guardar |
| Ctrl + X | Salir |
| Ctrl + K | Cortar linea |
| Ctrl + U | Pegar linea |
| Ctrl + W | Buscar texto |

---

## vim

`vim` es otro editor de texto en terminal, mucho mas potente que nano pero mas dificil de arrancar a usar. Tiene dos modos principales:

- Modo normal (el que abre por defecto): para navegar y ejecutar comandos
- Modo insercion: para escribir texto

```bash
# Abrir un archivo
vim nombre-archivo.md
```

Comandos basicos:

| Comando | Accion |
|---------|--------|
| i | Entrar al modo insercion para empezar a escribir |
| Esc | Volver al modo normal |
| :w | Guardar |
| :q | Salir |
| :wq | Guardar y salir |
| :q! | Salir sin guardar |
| dd | Borrar la linea actual |
| u | Deshacer |

Git usa vim como editor por defecto para los mensajes de commit cuando no se pasa `-m`. Si te aparece vim sin quererlo lo mas rapido es escribir `:q!` para salir sin guardar.

Para cambiar el editor por defecto de Git a nano:
```bash
git config --global core.editor nano
```

---

## alias

Un alias es un atajo que le asignas a un comando largo.

```bash
# Crear un alias temporal, dura hasta que cierres la terminal
alias gl='git log --oneline --graph --all'

# Usarlo
gl
```

Para que quede guardado hay que agregarlo al archivo de configuracion del shell:

```bash
# En bash
echo "alias gl='git log --oneline --graph --all'" >> ~/.bashrc
source ~/.bashrc

# En zsh que es el que usa macOS por defecto
echo "alias gl='git log --oneline --graph --all'" >> ~/.zshrc
source ~/.zshrc
```

Tambien se pueden crear alias directamente en Git:

```bash
git config --global alias.lg "log --oneline --graph --all"
# Uso:
git lg
```

---

## Notas

- `nano` es la opcion mas amigable si no tenes experiencia editando en la terminal.
- `vim` aparece mucho en tutoriales y servidores remotos asi que conviene saber al menos como salir con `:q!`.
- Los alias ahorran bastante tiempo en comandos que usas todo el tiempo como `git log --oneline --graph --all`.
  
### [volver al indice](../indice.md) 
  
