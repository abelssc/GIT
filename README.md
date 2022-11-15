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
