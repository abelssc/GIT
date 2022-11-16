# GIT
## CONOCIENDO EL FLUJO DE GIT

* EL PROYECTO INICIA CON EL WORKING DIRECTORY, QUE ES EL DIRECTORIO PRINCIPAL QUE RECIBIRA TODOS LOS CAMBIOS. EN ESTE MOMENTO ESTAMOS CON UN **GIT STATUS** ROJO
* PASAMOS AL STAGED AREA , AL USAR **GIT ADD** . , en este punto guardamos en memoria cambios que aun podemos revertir con **GIT RESTORE**
* PASAMOS AL AREA DE COMMITED AL USAR **GIT COMMIT -M " text"**
Y FINALMENTE PASAMOS TODOS NUESTROS ARCHIVOS AL REMOTO, "LA NUBE DE GITHUB" AL USAR **GIT PUSH**.

![](/img/git-flow.png)

## CONFIGURANDO GIT
```properties
#AL INICIAR GIT TENEMOS QUE CONFIGURAR ALGUNAS PROPIEDADES

#la clave --global hace referencia a que este cambio sera en abmito global para todo el S.O.
git config --global user.name "Abel Abed"
git config --global user.email abel_silva27@hotmail.com
git config --global user.ui true
#para ver la lista de configuraciones
git config --list
# ver todas las opciones de la configuración en la terminal
git config -h
# ver todas las opciones de la configuración en el navegador
git help config  

```

## FLUJO
```bash
#PARA INICIAR UN REPOSITORIO WORKING DIRECTORY
git init

#PARA AGREGAR LOS CAMBIOS AL STAGED
git add archivo/directorio
git add .

#CREAR UN ID/ TENER UN HISTORIAL DE LOS CAMBIOS
git commit 
git commit -m

#OPCIONALMENTE PODEMOS SELECCIONAR LA RAMA DONDE GUARDAR LOS CAMBIOS
git branch -M main

#PARA HACER REFERENCIA AL ORIGEN REMOTO
git remote add origin http://github.com/user/repositorio.git

#PARA SUBIR LOS CAMBIOS AL REPOSITORIO DE GITHUB X PRIMERA VEZ
#-u = --set-upstream que significa, crea la rama en el remoto....
git push -u origin master

#PARA NUEVAS ACTUALIZACIONES
git push


#PARA DESCARGAR CAMBIOS
git pull 
```

## GIT IGNORE
Es un archivo donde se le indica que carpetas o directorios no debe hacer seguimiento.
```properties
#Ignorar archivos,carpetas
archivo.etc
carpeta
/carpeta/archivo.etc
#ignorar en conjunto
*.etc
#ignorar excepto
!archivo.etc
#ingorar por carpeta
carpeta/*.txt
#ignorar por carpteas
carpeta/**/*.txt
```

## CLONAR REPOSITORIOS
Si queremos obtener un proyecto ya aloja en git podemos usar `git clone`.
```
git clone https://github.com/user/proyecto.git
```

## BRANCHES - NAVEGANDO POR RAMAS
```properties
#crear rama
git branch nombre_rama

#navegar por ramas
git checkout nombre_rama

#crear rama y navegar por ella
git -b checkout nombre_rama

#eliminar rama
git branch -d nombre_rama

#eliminar ramas remotas
git push origin --delete nombre_rama

#eliminar rama (forzado)
git branch -D nombre_rama

#listar las ramas del repositorio
git branch

# lista ramas no fusionadas a la rama actual
git branch --no-merged

# lista ramas fusionadas a la rama actual
git branch --merged

# rebasar ramas
git checkout rama-secundaria
git rebase rama-principal

```
## REGISTRO DE HISTORIAL
```properties
git log

# muestra en una sola línea por cambio
git log --oneline

# guarda el log en la ruta y archivo que especifiquemos
git log > commits.txt

# muestra el historial con el formato que indicamos
git log --pretty=format:"%h - %an, %ar : %s"

# cambiamos la n por cualquier número entero y mostrará los n cambios recientes
git log -n

# muestra los cambios realizados después de la fecha especificada
git log --after="2019-07-07 00:00:00"

# muestra los cambios realizados antes de la fecha especificada
git log --before="2019-07-08 00:00:00"

# muestra los cambios realizados en el rango de fecha especificado
git log --after="2019-07-07 00:00:00" --before="2019-07-08 00:00:00"

# muestra una gráfica del historial de cambios, rama y fusiones
git log --oneline --graph --all

# muestra todo el registro de acciones del log
# incluyendo inserciones, cambios, eliminaciones, fusiones, etc.
git reflog

# diferencias entre el Working Directory y el Staging Area
git diff
```

## RESETEO DE HISTORIAL
```properties
#nos muestra el listado de archivos nuevos (untracked), borrados o editados
git status

#borra cambios en el working
git restore .

#borra cambios en el stage (quita el add)
git restore --stage .

# borra HEAD
git reset --soft

# borra HEAD y Staging
git reset --mixed

# borra todo: HEAD, Staging y Working Directory
git reset --hard

# deshace todos los cambios después del commit indicado, preservando los cambios localmente
git reset id-commit

# desecha todo el historial y regresa al commit especificado
git reset --hard id-commit
```

## REMOTOS

```properties
#nos muestra el listado de archivos nuevos (untracked), borrados o editados
git status

# borra HEAD
git reset --soft

# borra HEAD y Staging
git reset --mixed

# borra todo: HEAD, Staging y Working Directory
git reset --hard

# deshace todos los cambios después del commit indicado, preservando los cambios localmente
git reset id-commit

# desecha todo el historial y regresa al commit especificado
git reset --hard id-commit

```