# Comandos Esenciales de GIT (2025) 🚀

![Texto alternativo](https://blog.knoldus.com/wp-content/uploads/2020/05/cover-first-steps-git.png)

<p>
Hola a todos, hoy les traigo una guía de comandos de GIT que les puede ser de mucha ayuda a la hora de organizar el código de trabajo, el historial y evolución del mismo.
</p>


#### Git: 
*Es un software de "Control de Versiones" que fue diseñada por Linus Torvalds, es Open Source y muy potente, permite registrar el historial de cambios de un proyecto y facilita a los usuarios a llevar el seguimiento de los cambios de un archivo.* 

--- 

## Establecemos los valores de configuración
Ahora debemos establecer las variables de configuración global, que son muy importantes, especialmente si estás trabajando con otros desarrolladores.
La principal ventaja de esto es que es más fácil averiguar quién ha hecho un commit de determinado bloque de código.

* git config puede ser usado para establecer una configuración específica de usuario, como el nombre de usuario ,y el email, etc. 

```cmd
$ git config --global user.name "nombre"
$ git config --global user.email "correo@correo.com"
```
* Habilitar la útil colorización del producto de la línea de comando.
```cmd
$ git config --global color.ui auto
```
* Ver la configuracion.
```cmd
$ git config --list
```
* Puedes establecer fácilmente un alias para cada comando mediante git config.
```cmd
$ git config --global alias.ci 'commit'
```
* Con este comando haremos que git detecte automaticamente lo que queremos escribir
```cmd
$ git config --global help.autocorrect 1
```


## CREAR REPOSITORIOS
* Iniciar un nuevo repositorio
```cmd
$ git init
```
* Clonar un repositorio existente, descarga un proyecto y toda su historia de versión
```cmd
$ git clone <https://link-con-nombre-del-repositorio>
```
* Agregar archivos a la área de preparación
```cmd
$ git add <nombre-del-archivo>   // Agregar un archivo especifico.
$ git add .                 // Agregar todos los archivos.
```
* Deshacer los git add
```cmd
$ git reset .
```
* Hacer commit de los cambios con un mensaje que explique los cambios
```cmd
$ git commit -m "mensaje de confirmación"
$ git commit -a -m "saltar el git add" // Con este comando nos saltamos de hacer el git add 

```
* Enumera todos los archivos nuevos o modificados que se deben confirmar
```cmd
$ git status -s
```
* Muestra las diferencias de archivos que no se han enviado aún al área de espera
```cmd
$ git diff
```
* Modificar los git commit
```cmd
$ git commit --amend
```
* Deshacer los commit
```cmd
$ git reset --soft HEAD~1   // Borra el ultimo commit y no borra los cambios
$ git reset --hard HEAD~1   // Borra el ultimo commit y si borra los cambios
```
* Subir los archivos a un repositorio remoto
```cmd
$ git push origin <nombre-de-la-rama>
```

## RAMAS 
* Crear una nueva rama
```cmd
$ git branch <nombre-de-la-rama>
```
* Crear una rama rama (Segunda opción)
```cmd
$ git checkout -b <nombre-de-la-rama> // Creará la nueva rama y cambiará a ella al instante
```
* Visualiza todas las ramas en el repositorio actual
```cmd
$ git branch
$ git branch --list
```
* Cambiar a la rama especificada y actualiza el directorio activo
```cmd
$ git checkout <nombre-de-la-rama>
```
* Volver a la rama anterior sin necesidad de escribir el nombre
```cmd
$ git switch -
```
* Borrar una Rama
```cmd
$ git branch -D <nombre-de-la-rama>
```
* Lista los branches con mas información
```cmd
$ git show-branch
```
* Combina el historial de la rama especificada con la rama actual
```cmd
$ git merge <nombre-de-la-rama>
```

## REBASE
* Se usa para aplicar ciertos cambios de una rama en otra, Une el branch actual con la main
```cmd
$ git rebase
```
* Cuando resolvemos los conflictos --continue continua la secuencia del rebase donde se pauso
```cmd
$ git rebase --continue
```
* Omite el conflicto y sigue su camino
```cmd
$ git rebase --skip
```
* Devuelve todo al principio del rebase
```cmd
$ git rebase --abort
```
* Se usa para aplicar ciertos cambios de una rama en otra 
```cmd
$ git rebase <nombre-de-la-rama>
```

## REMOTE
* Permite ver todos los repositorios remotos asigandos o a los que apunta tu repositorio local
```cmd
$ git remote -v
```
* Crear un repositorio remoto y lo enlaza con tu repositorio local
```cmd
$ git remote add <nombre/origin> <url>
```
* Remover el enlace al repositorio remoto
```cmd
$ git remote rm <nombre/origin>
```
* Permite cambiar la URL del repositorio remoto 
```cmd
$ git remote set-url origin <url>
```

## TAG
* Crea un nuevo tags
```cmd
$ git tag v0.0.1 -m "primera versión"
```
* Muestra una lista de todos los tags
```cmd
$ git tag
```
* Te permite ver cómo estaba el repositorio en cada estado
```cmd
$ git show v0.0.1
```
* Enviar al repositorio en GitHub
```cmd
$ git push --tags
```

## OTROS COMANDOS
* Busca los cambios nuevos y actualiza el repositorio
```cmd
$ git pull origin <nombre-de-la-rama>
```
* Verifica cambios en el repositorio online con el local
```cmd
$ git fetch
```
* Almacena temporalmente el trabajo sin comentar.
```cmd
$ git stash
```
* Para recuperar los últimos cambios desde el stash a tu staging.
```cmd
$ git stash pop
```
* Listar el historial de versiones de la rama actual.
```cmd
$ git log
$ git log --oneline --graph // Con este comando se lo puede ver mucho mejor 
$ git log --pretty=oneline --graph --decorate --all // Otra forma mas completa
```
* Deshacer el commit si ya se hizo push
```cmd
$ git revert 3a67899
```
* Para recuperar archivos que borre
```cmd
$ git checkout -- . 
```
* Borrar un archivo
```cmd
$ git rm <nombre-del-archivo> 
```
* Para recuperar archivos que borre después del git rm
```cmd
$ git checkout HEAD -- .
```
* Eliminar un repositorio de Git creado con ‘git init’ en un directorio
```cmd
cd carpeta/
$ rm -rf .git
```
* Cambia el nombre del archivo y lo prepara para commit
```cmd
$ git mv [archivo-original] [archivo-renombrado]
```

---

📌 Mis Redes: 🔵[Facebook](https://www.facebook.com/gdcode7) | 💼[LinkedIn](https://www.linkedin.com/in/gastondanielsen/) | 💻[Github](https://github.com/gdcodev)
