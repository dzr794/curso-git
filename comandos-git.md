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