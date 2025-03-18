## **Curso de Github**

[1. Configuración de GIT](#1-configuración-de-git)

[2. Crear repositorios](#2-crear-repositorios)

[3. Diferencia entre versiones](#3-diferencia-entre-versiones)

[4. Ramas (Branches)](#4-ramas-branches)

[5. Fusionar ramas (Merge)](#5-fusionar-ramas-merge)

[6. .gitignore](#6-gitignore)

[7. Github](#7-github)




### **_1. Configuración de GIT_**
1. Ir a la consola de git, luego de la instalación.
2. Comandos para configurar git

    > git config --global user.name "Xime"
    >
    > git config --global user.email "ximecamino@gmail.com"
    > 
    > git config --system
    > 
    > git config --local
    >
    > git config --list (todas las configuraciones posibles)
3. Configurar el editor de código VSC

    > git config --global core.editor "code --wait"
    >
    > git config --global color.ui true (configurar el color de nuestra interfaz)
    >
    > git config --global core.autocrlf true (salto de línea automático)

### **_2. Crear repositorios_**

1. Crear una carpeta y entrar.
2. Git init (lo inicializo).  Genera una carpeta .git de archivos ocultos de configuración.
3. Agregar archivos al área de preparación:
   1. Todos los de la carpeta _git add._
   2. Archivos específicos _git add archivo.txt_(para agregar más de 1 archivo, los separo por 1 espacio)
4. _git status_ dá información sobre el área de trabajo y de preparación.
5. Si queremos deshacer los archivos agregados, el status lo marca como "unstaged".  Comando remove: _git rm --cached archivo.txt_
6. Subir el archivo al repositorio: _git commit -m "mensaje corto para explicar lo que agrego"_
    
    _git commit -a_ directamente sube todo al repositorio sin pasar al área de preparación.
7. Eliminar un archivo y volverlo al área de trabajo.
   
    _git restore archivo.txt_

8. Retrocede a un estado anterior un archivo modificado.
   
   _git checkout archivo.txt_ (en el área de preparación)

   _git reset --hard_ (Borra los cambios en el área del repositorio y en el área de staging)

9. Renombrar un archivo.
    _git mv xime.txt ximecamino.txt_

### **_3. Diferencia entre versiones_**

_git show archivo.txt_ muestra el contenido del archivo.

_git diff --staged_ muestra las diferencias entre el archivo que está en preparación y en el repositorio.

_git log_ muestra información de todos los commits hechos con los mensajes.

_git rebase -i head-3_ lo que hace es modificar un commit anterior al último (en este caso 3 más atrás)

_git reset --soft 23a89_ vuelve para atrás a un commit determinado borrando todos los posteriores.

### **_4. Ramas (branches)_**

_git branch_ muestra todas las ramas.

_git branch nombre-rama_ crea la nueva rama.

_git switch nombre-rama_ para moverse a trabajar en esa rama.

_git switch -c nombre-rama_ crea una nueva rama y entra a trabajar en ella.

Para borrar las ramas creadas, tengo que salir de la rama que quiero borrar y escribir el comando _git branch -d nombre-rama_

Para modificar el nombre de una rama, entro en la rama que quiero cambiar el nombre y escribo el comando _git branch -m nuevo-nombre_

### **_5. Fusionar ramas (merge)_**

Es cuando trabajo en una rama creada y los archivos cambiados los quiero integrar a la rama principal.  Tengo que posicionarme en la rama destino (en este caso la principal), ahí escribo el comando: _git merge nombre-rama_

Deshacer la fusión y eliminar el commit: _git reset --hard 128s2b_

_git log --online --all_ muestra todos los commits de todas las ramas

#### Conflictos

Cuando hago un merge y aparecen conflictos.  En el VSC aparecen los fragmentos en conflicto, entonces ir a Resolve in Merge Editor.

### **_6. .gitignore_**

configurar un gitignore para todos los proyectos, global.

_git config --global core.excludesfile G:/.gitignore_global_

_git add ._

_git commit -m "Probando el nuevo .gitignore global"_

### **_7. Github_**

Crear repositorio siempre con camel case.

Clonar el repositorio creado para ligarlo a una carpeta de trabajo local:
- copiar la dirección del repositorio creado.
- _git clone https://github.com/bioxim/curso-git-github.git_
- Con git push, mando todos los cambios que hago a github _git push origin main_