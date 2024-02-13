# Comandos GIT

## Configuración inicial

- Para inidicar localmente el nombre de usuario

  - `git config --global user.name "name"`
- Para indicar localmente el correo del usuario

  - `git config --global user.email "email"`
- Para indicar localmente el nombre de la rama principal de todos los repositorios futuros

  - `git config --global init.defaultBranch "branchName"`
- Para ver/editar la configuración global

  - `git config --global -e`
- Para corregir posible errores de CRLF (debo de estar ubicado en un repositorio git)

  - `git config core.autocrlf true`
- Para eliminar archivos o carpetas que ya estan siendo rastreadas en el repositorio

  - `git rm --cached "path or fileName"`
- Para ignorar la basura de MAC

  - `find . -name .DS_Store -print0 | xargs -0 git rm --ignore-unmatch`
- para creat un .gitignore global que ignore siempre los .DS_Store

  ```
  echo ".DS_Store" " ~/.gitignore_global
  echo "._.DS_Store" " ~/.gitignore_global
  echo "**/.DS_Store" " ~/.gitignore_global
  echo "**/._.DS_Store" " ~/.gitignore_global
  git config --global core.excludesfile ~/.gitignore_global
  ```

## ¿Cómo subir un proyecto local a un repositorio nuevo?

1. Primero, navega a la carpeta que deseas subir utilizando la línea de comandos. Puedes hacerlo con el comando cd, por ejemplo:
   `cd ruta/a/tu/carpeta`
2. Inicializa un nuevo repositorio de Git en esa carpeta con el comando git init:
   `git init`
3. Agrega todos los archivos en la carpeta al repositorio con el comando git add:
   `git add .`
4. Haz un commit de los archivos con el comando git commit. Asegúrate de agregar un mensaje de commit descriptivo:
   `git commit -m "Mi primer commit"`
5. Ve a GitHub y crea un nuevo repositorio. No inicialices el repositorio con un README, .gitignore o License. Solo dale un nombre y haz clic en “Create repository”.
6. En la página de tu nuevo repositorio, copia la URL del repositorio.
7. Vuelve a la línea de comandos y agrega la URL de tu repositorio como el “origin” remoto:
   `git remote add origin tu_url_del_repositorio`
8. Finalmente, sube tus archivos al repositorio con el comando git push:
   `git push -u origin main`

## Comandos básicos

### Status

- Para ver información sobre los "commits", sobre la rama en la que me encuentro actualmente, hace mención sobre los archivos a los que no se les esta haciendo seguimiento
  - `git status`

### Add

- Para añadir seguimiento a archivos en el repositorio
  - `git add "path or fileName"`

- Para añadir todos los cambios al "stage"
  - `git add .`

### Reset

- Para eliminar el seguimiento de un archivo o directorio
  - `git reset "path or fileName"`
  
- Para eliminar el ultimo commit
  - `git reset --soft HEAD^`
    - `--soft` con el SOFT no se eliminan los cambios
      `--mixed`
      `--hard` con el HARD se eliminaran los cambios
    - `HEAD^`: Apunta al hash del ultimo commit
    `HEAD^2`:Apunta al PENULTIMO commit,
    del mismo modo `HEAD^3` apuntara al commit anterior a este.

### Checkout

- Comando para reconstruir el proyecto a como estaba en el ultimo commit
  - `git checkout -- .`
  - TENER EN CUENTA QUE A LAS CARPETAS VACIAS NO SE LES HACE SEGUIMIENTO!

### Branch

- Para ver el nombre de la rama actual
  - `git branch`

- Para cambiar el nombre de la rama
  - `git branch -m "nombre actual" "nombre nuevo"` por ejemplo `git branch -m master main`

### Commit

- Para "tomar la fotografia" de el estado actual del repositorio
  - `git commit -m "mensaje descriptivo corto"`
  
- Para hacer un commit de archivos MODIFICADOS sin tener que escribir el "add" (no funciona con archivos UNTRACKED solo MODIFIED)
  - `git commit -am "el mensaje"`
  - NO FUNCIONA CON ARCHIVOS NUEVOS QUE AUN NO ESTAN SIENDO RASTREADOS

- Para modificar el mensaje del ultimo commit (--amend)
  - `git commit --amend -m "mensaje corregido"`

### Log

- Para mostrar el registro de todos los commits
  - `git log`


## Creando alias

### Status

* Para escribir mas rapido el `git status`
  * `git config --global alias.s "status --short"` o `git config --global alias.s "status -sb"`

### Log

* Para un `git log` mas visual
* `git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"`
*
