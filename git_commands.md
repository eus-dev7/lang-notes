# Guia de comandos GIT
- Inicializa o reinicializa un repositorio
```
    git init
```
- Clonar un repositorio
```
    git clone https://github.com/....
```
- agregar un archivo al area de staging
```
    git add [filename]
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
- Mostrar cambios en file_name
```
    git diff [file_name]
```
- commit cambios
```
    git commit -m "mensaje de commit aqui"
```
- Preparar y hacer commit de cambios, pero ignora los archivos recién creados
```
    git add -a -m "mensage de commit aqui"
```


- descartar el último commit y hace checkout al anterior
```

```