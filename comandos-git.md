# Comandos GIT

## Configuración inicial

- Para inidicar localmente el nombre de usuario
  - `git config --global user.name <name>`

- Para indicar localmente el correo del usuario
  - `git config --global user.email <email>`

- Para indicar localmente el nombre de la rama principal de todos los repositorios futuros
  - `git config --global init.defaultBranch <branchName>`

- Para ver/editar la configuración global
  - `git config --global -e`

- Para corregir posible errores de CRLF (debo de estar ubicado en un repositorio git)
  - `git config core.autocrlf true`

- Para eliminar archivos o carpetas que ya estan siendo rastreadas en el repositorio
  - `git rm --cached <path or fileName>`

- Para ignorar la basura de MAC
  - `find . -name .DS_Store -print0 | xargs -0 git rm --ignore-unmatch`

- para creat un .gitignore global que ignore siempre los .DS_Store
  ```
  echo ".DS_Store" >> ~/.gitignore_global
  echo "._.DS_Store" >> ~/.gitignore_global
  echo "**/.DS_Store" >> ~/.gitignore_global
  echo "**/._.DS_Store" >> ~/.gitignore_global
  git config --global core.excludesfile ~/.gitignore_global
  ```

## Comandos básicos

 - Para ver información sobre los "commits", sobre la rama en la que me encuentro actualmente, hace mención sobre los archivos a los que no se les esta haciendo seguimiento
   - `git status`
 
 - Para añadir seguimiento a archivos en el repositorio
   - `git add <path or fileName>`
   
 - Para añadir todos los cambios al "stage"
   - `git add .` 
 
 - Para eliminar el seguimiento dek un archivo o directorio
   - `git reset <path or fileName>`

 - Para "tomar la fotografia" de el estado actual del repositorio
   - `git commit -m <mensaje descriptivo corto>`
 
 - Comando para reconstruir el proyecto a como estaba en el ultimo commit
   - `git checkout -- .`
   - TENER EN CUENTA QUE A LAS CARPETAS VACIAS NO SE LES HACE SEGUIMIENTO!

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

  1. Finalmente, sube tus archivos al repositorio con el comando git push:
  `git push -u origin main`