EJERCICIO 1

Una vez creado el repositorio, debemos clonarlo: git clone https://github.com/rafaameedina/gitflow-php-rafamedina.git

Nos posicionamos en el nuestro repositorio y verificamos el historial de ramas: git branch -a

Inicializamos git flow: git init

Por último creamos la rama develop: git checkout -b "develop"


EJERCICIO 2

Creamos una nueva funcionalidad: git flow start crear-mi-archivo

Después creamos la carpeta alumnos y creamos dentro un nuevo archivo: echo '<?php echo "Hola, soy Rafa Medina y estoy aprendiendo Git Flow!"; ?>' > alumnos/rafamedina.php

Subimos los cambios a la rama develop: 
-git add .
-git commit -m "Subida mi archivo"
-git flow feature finish crear-mi-archivo (para finalizarlo)
-git push origin develop

Por último verificamos los commits: git log --oneline --graph


EJERCICIO 3

Creamos otra funcionalidad: git flow feature start modificar-index

Agregamos una línea para incluir nuestro archivo: echo '<?php include "alumnos/rafamedina.php"; ?>' >> index.php

El último paso es subir los cambios al igual que en el ejercicio anterior:
-git add .
-git commit -m "Modificación index.php"
-git flow feature finish modificar-index
-git push origin develop


EJERCICIO 4

Hacemos un git status para mostrar el conflicto

Después mergeamos ambas funcionalidades en develop: git merge develop

Luego añadimos el archivo, hacemos el commit y subimos los cambios:
-git add index.php
-git commit -m "Conflicto resuelto"
-git push origin develop


EJERCICIO 5

Creamos una nueva funcionalidad: git flow feature start borrar-mi-archivo

Eliminamos el archivo: rm alumnos/rafamedina.php

Hacemos el commit: git commit -m "Arvhivo borrado"

Subimos los cambios: git push origin develop

Y por último vemos la eliminación: git log --oneline


EJERCICIO 6

Creamos release: git flow release start v1.0

Después la eliminamos: git flow release finish v1.0

Creamos una rama tag y publicamos la versión:
-git tag -a v1.0 -m "Versión publicada"
-git push origin --tags
