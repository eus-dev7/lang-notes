# Guia de comandos GIT
- Inicializa o reinicializa un repositorio
```
    git init
```
- Clonar un repositorio
```
    git clone https://github.com/....
```
- agregar un [archivo] al area de staging
```
    git add [archivo]
```
- agregar nuevos archivos, actualizar archivos modificados y eliminar archivos eliminados del área de staging
```
    git add -A
```
- actualizar archivos modificados y eliminar archivos eliminados al area de staging
```
    git add -u
```
- estado actual del árbol de trabajo
```
    git status
```
- mostrar todos los archivos modificados
```
    git diff
```
- Mostrar cambios en [archivo]
```
    git diff [archivo]
```
- commit cambios
```
    git commit -m "mensaje de commit aqui"
```
- Preparar y hacer commit de cambios, pero ignora los archivos recién creados
```
    git add -a -m "mensage de commit aqui"
```
- quitar todos los archivos desde commit
```
    git reset
```
- quitar [archivo]
```
    git reset [archivo]
```
- Descartar ultimo commit y hacer checkout al commit anterior
```
    git reset --hard HEAD~1
```
- descartar ultimos 3 commits y revertir hasta el ultimo 4to commit
```
    git reset --hard HEAD~3
```
- Eliminar [archivo] desde area de staging y directorio de trabajo
```
    git rm [file_name]
```
- Renombrar [archivo] a [archivo_renombrado]
```
    git mv [file_name] [file_name_edited]
```
- Mover [archivo] a ./src/[file]
```
    git mv [file] ./src
```
- Crear una nueva rama con los contenidos del directorio de trabajo
```
    git branch [nombre-de-rama]
```
- Crear una nueva rama basado en un commit
```
    git branch [nombre-de-nueva-rama] [codigo-de-commit]
```
- Crear una nueva rama desde una etiqueta
```
    git branch [nombre-de-nueva-rama] [nombre-de-etiqueta]
```
- Crear una nueva rama desde una rama remota
```
    git branch --track [nombre-de-nueva-rama] origin/[rama-base]
```
- Eliminar una rama
```
    git branch -d [nombre-de-rama]
```
- Cambiar a una rama especifica
```
    git switch [nombre-de-rama]
```
- Actualiza el directorio de trabajo con los archivos el el indice
```
    git checkout
```
- Forma alternativa de cambiar entre ramas
```
    git checkout [nombre-de-rama]
```
- Muestra todas las commits que realizó junto con el nombre del autor y la hora del commit
```
    git log
```
- Agregar un origen con nombre remoto a un repositorio remoto
```
    git remote add origin [url-del-repositorio]
```
- Verificar remotos
```
    git remore -v
```
- Hacer un push a una rama
```
    git push origin [nombre-de-rama]
```
- Recuperar de un repositorio remoto
```
    git fetch origin master
```
- Fusionar una rama con el directorio actual
```
    git merge [nombre-de-rama]
```
- Buscar y fusionar desde un repositorio remoto 
```
    git pull origin [nombre-de-rama]
```
- Guardar todos los cambios locales
```
    git stash
```
- Eliminar todos los cambios guardados
```
    git stash pop
```
- Aplicar todos los cambios guardados previamente
```
    git stash apply
```
- Agregar una etiqueta a un commit
```
    git add [nombre-de-etiqueta] [codigo-de-commit]
```
- Desplegar todas las etiquetas
```
    git tag
```
- Hacer checkout a una etiqueta especifica
```
    git checkout [eqtiqueta]
```