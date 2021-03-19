# Comandos de git y github
![Flujo de trabajo de git](https://i.imgur.com/HHZOixy.png "Flujo de trabajo de git")

- **Nota: 
algunos comandos que tengan estas lineas unidas: ![](https://i.imgur.com/kVFhm9H.png) deben escribirse asi: ![](https://i.imgur.com/EgWnqHg.png) ya que en el readme lo cambia y une las lineas**


- **Nota: Siempre que quiera probar algún comando podría crear una rama de prueba para probar cualquier comando y no afectar a la rama principal**

------------
## Iniciando con Git
- **git init** sirve para inicializar el proyecto que esté recién creado o que ya está creado con código, lo que indica es que vas a comenzar a usar git
- **git status** sirve para verificar si se añadió o editó algo en el proyecto
- **git add nombre_archivo** sirve para subir especificamente un archivo al staging area
- **git add .** sirve para subir todos los archivos al staging area
- **git commit -m "mensaje"** sirve para subir al repositorio local con un mensaje especifico de lo realizado, **nota:** tener en cuenta en dejar un mensaje claro de lo que se realizó
- **git config --global user.email "correo_electronico"** sirve para configurar, es decir hay que poner el correo de la persona que va a utilizar git, **Nota:** es preferible que ya este creada una cuenta en git y se ponga el correo vinculado con esa cuenta
- **git config --global user.name "nombre_usuario"** sirve para configurar, es decir hay que poner el nombre de usuario de la persona que va a utilizar git, **Nota:** es preferible que ya este creada una cuenta en git y se ponga el nombre de usuario vinculado con esa cuenta
- **git clone url_proyecto** sirve para clonar el proyecto que está en el repositorio remoto a mi pc, **Nota:** tener en cuenta que tengo que pegar solo la dirección url copiada del github después del git clone ya que la url varia por cada proyecto
- **git pull origin nombre_rama** sirve para traer los cambios que están en el repositorio remoto y que actualmente no los posees en tu repositorio local
- **git push origin nombre_rama** sirve para subir los cambios al repositorio remoto

## Github
- **git remote add origin url_git**  sirve para añadir mi proyecto a mi respositorio remoto, **Nota:** hay que tener en cuenta que ya se haya hecho con anterioridad los comandos: git init, git add ., git commit -m "", si no, hacerlo antes de ejecutar el comando git remote
- **git push -u origin main** sirve para subir mi proyecto al repositorio posteriormente de haberlo hecho con el comando anterior, **Nota:** tener en cuenta de que si es la primera vez que se instala o se ejecuta este comando en git hub saldrá una ventana emergente en el cual tendrás que poner tu nombre de usuario y contraseña de la cuenta de git, caso contrario si ya está vinculada no saldrá nada
### Consejo
- En la página de github también se puede añadir, editar o eliminar y hacer esos commit sin necesidad de hacerlo en algún editor de código si no directamente ahí solo al abrir, **Nota:** tener en cuenta que esto solo es en casos donde el cambio  sea poco o sencillo

## Git log
- **git log** sirve para mostrar la lista de todos los commit dando detalle de el sha-1 id largo del commit, nombre de usuario de quien hizo el commit, fecha y hora y el mensaje del commit, **Extra:** para cerrar solo presionar la tecla **q**
- **git log --oneline** sirve para mostrar la lista de todos los commit dando detalle de el sha-1 id **corto** y el mensaje del commit, **Extra:**para cerrar solo presionar la tecla **q**
- **git log -p** sirve para mostrar la lista de todos los commit realizados dando detalle de el sha-1 id largo del commit, nombre de usuario de quien hizo el commit, fecha y hora, mensaje de commit y muestra todo el código que se editó, eliminó o agregó, **Extra:**para cerrar solo presionar la tecla **q**
- **git log --stat** sirve para mostrar la lista de todos los commit realizados dando detalle de el sha-1 id largo del committ, nombre de usuario de quien hizo el commit, fecha y hora, mensaje de commit y  muestra el nombre de los archivos y la cantidad en números de las líneas de código insertadas o los archivos agregados

## Regresando a Commit
- **git restore nombre_archivo** sirve para descartar los cambios, es decir volveremos al inicio de todo y borraremos todo lo hecho, pero esto solo pasa si no se ha hecho un git add .
- **git restore --staged nombre_archivo** sirve para retroceder pero esto solo se puede hacer si ya se hizo un git add . ya que estaríamos en el staging area y queremos volver al working directory
- **git diff nombre_archivo** sirve para comparar los cambios que ya hiciste con lo que tenías antes al inicio, mostrando el codigo que editaste, eliminaste o añadiste.
- **git checkout sha1_id_corto** sirve para moverse a un commit, **Nota:** tener en cuenta que se usa en situaciones donde solo quiero revisar el código no se debe hacer ningún cambio, ya que correríamos riesgos de perder commit posteriores a este
- **git switch -** sirve para volver al commit principal de mi rama, **Nota:** este comando se usa después de haber usado el comando anterior, recuerde que para ejecutar este comando no se debió haber modificado nada, asi se podrá volver la normalidad
- **git switch -c nombre_rama** sirve para crear una rama del commit en el que me encuentro, **Nota:** tener en cuenta que para usar este comando se debe usar despues de ejecutar **git checkout sha1_id_corto** lo que se quiere lograr es crear una rama con este commit para realizar pruebas sin tener que dañar nada del commit en el que estoy
- **git revert id_commit** sirve para ir a algun commit en especifico sin borrar los commit posteriores al que regreso, lo que hace es crear un nuevo commit del que quiero regresar, no borraria nada, solo creo otro nuevo commit del que quiero regresar
- **git reset --hard sha1_id_corto** sirve para ir a algun commit en especifico, pero de una forma brusca ya que eliminaría los commit posteriores a ese y no quedaría ningún historial, **Nota:** cuidado al ejecutar este commit si no está seguro de lo hace
- **git reset --soft sha1_id_corto** sirve para ir a algun commit en especifico, pero a diferencia de --hard este comando volvería al commit que quiero, pero conservaría los cambios que hice posteriormente a este commit en el **staging area** y asi podríamos hacer otro commit y volveríamos al principio
- **git push -f origin nombre_rama** sirve para subir los cambios al repositorio remoto la opción **-f** es para forzar la sobreescritura del historial, **Nota:** este comando va de la mano con **git reset --hard sha1_id_corto** ya que al ir a un comando y borrar los commit posteriores a ese **git push -f origin nombre_rama** subira ese cambio forzadamente sin importar nada
### Consejo
- Tener en cuenta que al realizar push y después querer eliminar o editar algún commit puede traer problemas es recomendable trabajar en el repositorio local hasta que se esté listo en hacer push solo cuando se esté seguro de lo que se subirá al repositorio remoto

## Ramas
- **git branch** sirve para mostrar todas las ramas que tengo existentes en mi proyecto
- **git branch nombre_rama** sirve para crear una nueva rama a mi proyecto desde el commit en el que me encuentro
- **git checkout nombre_rama** sirve para cambiarse de rama, **Nota:** hay que tener en cuenta en la parte superior que está en paréntesis del nombre de la rama en la que me encuentro posicionado para verificar en que rama estoy
- **git push origin nombre_rama** sirve para subir la rama creada al repositorio remoto o tambien cambios realizados **Nota:** tener en cuenta que se debe estar ubicado en la rama para ejecutar este comando verificando su nombre en la parte de arriba en paréntesis
- **git branch -D nombre_rama** sirve para eliminar la rama en el repositorio local, **Nota:** tener en cuenta que al ejecutar este comando se debe cambiar a otra rama, ya que no dejará eliminar si se encuentra posicionado en la rama que quiere eliminar 
- **git push origin :nombre_rama** sirve para eliminar la rama del repositorio remoto, **Nota:** este comando va de la mano con el comando anterior 
- **git push origin --delete nombre_rama** sirve para eliminar directamente una rama en el repositorio remoto
- **git branch -m nuevo_nombre** sirve para renombrar tu rama local, **Nota:** no olvidar hacer push del nuevo nombre
- **git branch -m nombre_antiguo nombre_nuevo** sirve para renombrar tu rama local si estoy ubicado en otra rama **Nota:** no olvidar hacer push del nuevo nombre
- **git push origin :nombre_antiguo nombre_nuevo** sirve para borrar el nombre antiguo y hacer un push a la rama remota del nombre nuevo, **Nota:** este comando va de la mano con los anteriores de renombrar ramas, es decir que para hacer commit de las ramas renombradas se tiene que ejecutar este comando para subirlas al repositorio remoto
### Consejo
- Recordar que cuando se clona un proyecto que tiene ramas lo único que hay que hacer es poner **git branch –all** para ver todas las ramas existentes en el repositorio remoto o cambiar directamente a la rama obviamente ya tendriamos que saber el nombre al cual queremos cambiarnos directamente con **git checkout nombre_rama**

## Merge
- **git merge nombre_rama** sirve para unir ramas, lo que hace es (estoy en rama main) y quiero unir la rama desarollo a main **seria asi:** git merge desarollo
- **git merge --abort** sirve para abortar el merge en el caso de que haya un conflicto y lo quiero abortar
- **git rebase nombre_rama** sirve para unir ramas, lo que hace es (estoy en rama main) y quiero unir la rama desarollo a main **seria asi:** git merge desarollo  a diferencia de merge es que si este se tiene algún conflicto y se lo soluciona maneja el historial mucho mejor, ya que este si muestra el orden de las líneas que se quitaron o se agg al resolver el conflicto es más recomendable siempre hacer git rebase
### Consejo
- Siempre es mejor hacer git rebase a diferencia de merge porque si se tiene algún conflicto maneja el historial mucho mejor, ya que este si muestra el orden de las líneas que se quitaron o se agg en un orden cosa que merge no lo hace **es mas recomendable siempre usar git rebase**

## Reescribiendo el historial de git
- **git commit --amend** sirve para reescribir o reemplazar el ultimo commit que se subió, es decir que se subirá este commit pero eliminara el anterior reescribiéndolo o reemplanzandolo, **Extra:** se abrirá el editor vim para preguntar si se quiere dejar el mismo mensaje del commit anterior o se quiere modificar, para modificar presionar la tecla **i** luego a modificar el mensaje y para salir y guardar presionar las teclas **ESC** + **:wq**
- **git commit --amend -m "mensaje"** sirve para reescribir o reemplazar el ultimo commit que se subió , es decir que se subirá este commit pero eliminara el anterior reescribiéndolo o reemplanzandolo a diferencia del anterior comando este al Añadir la opción **-m** te permite escribir un nuevo mensaje desde la línea de comandos sin tener que abrir un editor.
- **git rebase -i HEAD~numero** sirve para reescribir el historial, es decir, se abrirá vim y se utilizaran la cantidad de commit que se ponga en **numero(1,2,3,etc)** se abrirá de esta manera:

![](https://i.imgur.com/SXcuw9d.png) 

se podra utilizar todos esos comandos para reescribir la cantidad de comando que se desee

**¿Para que sirve cada comando?**
- **p, pick sha1_id** = usar commit 
- **r, reword sha1_id** = sirve para editar el mensaje de commit 
- **e, edit sha1_id** = usar commit, pero deténgase para enmendar 
- **s, squash sha1_id** = sirve para fusionar commit **EJ:** tengo 3 commit y quiero fusionar los 3 en uno solo, tendría que cambiar 2 commit con **squash** y el restante dejarlo con **pick** así se fucionarian los 3 en uno solo, tener encuenta que el que se encuentra primero es el que se fusionara con el resto, también tener en cuenta que esto podría causar conflicto ya que los 3 commit posiblemente han hecho cambios en el mismo archivo
- **f, fixup sha1_id** = como "squash", pero descarta el mensaje de registro de esta confirmación 
- **x, exec comando** = ejecutar comando (el resto de la línea) usando shell 
- **b, break** = detener aquí (continuar rebase más tarde con 'git rebase --continue') 
- **d, drop sha1_id** = eliminar commit
- **l, label label** = etiquetar HEAD actual con un nombre 
- **t, reset etiqueta** = restablecer HEAD a una etiqueta 
- **m, merge [-C sha1_id | -c sha1_id] etiqueta [# oneline]** crear una confirmación de fusión utilizando la confirmación de fusión original. mensaje (o en línea, si no se realizó una confirmación de fusión original. especificado). Utilice -c **sha1_id** para reformular el mensaje de confirmación. 

## Git stash
![](https://i.imgur.com/mjTPhxa.png)

El comando git stash almacena temporalmente (o guarda en un stash) los cambios que hayas efectuado en el código en el que estás trabajando para que puedas trabajar en otra cosa y, más tarde, regresar y volver a aplicar los cambios más tarde.

- **git stash list** sirve para mostrar todos los stash que tengo
- **git stash save "mensaje"** sirve para guardar el stash, **¿cómo funciona?** primero se debio haber hecho commit y tener todo limpio, a partir de eso ya podría comenzar mi prueba con stash ya que lo que crearía desde ahí se guardaría en stash, una vez ejecutado el comando **Git stash save "mensaje"** se guardará y se volverá al principio donde todo estab limpio, **Nota:** es importante dejar claro el mensaje ya que con eso identificaremos cual stash aplicar despues al repositorio
- **git stash apply stash@{numero_posicion}** sirve para aplicar un stash al repositorio local, el **número de posición**, dependerá que cual sea la posición en la que se encuentra el stash que quiero aplicar, es decir que antes de usar este comando se debe usar **git stash list** para ver cual quiero usar
- **Git stash pop** sirve para aplicar el último stash creado
- **Git stash show -p** sirve para visualizar un resumen de lo que se agregó, modificó o eliminó en el stash, este haría lo mismo que **git log -p**
- **git stash drop stash@{numero_posicion}** sirve para eliminar un stash que no nesecite, indicándole su posición, **número de posición**, dependerá que cual sea la posición en la que se encuentra el stash que quiero aplicar, es decir que antes de usar este comando se debe usar **git stash list** para ver cual quiero eliminar
- **git stash clear** sirve para eliminar todos los stash creados

## Tags
- **git tag -a numero_version -m "mensaje" sha1_id_corto** sirve para versionalizar un proyecto poniendo el id del commit que ya está estable, en numero_version un ejemplo sería: **V0.1** 
- **git tag** sirve para mostrar todos los tags de mi proyecto
- **git show-ref --tags** sirve para mostrar todos los tags dando detalle del sha-1 id largo, nombre del tag
- **git show-ref nombre_tag** sirve para mostrar específicamente el tag que quiero dando detalle del sha-1 id largo y nombre
- **git push origin nombre_tag** sirve para subir específicamente el tag al repositorio remoto
- **git push origin --tags** sirve para subir al repositorio remoto todos los tags
- **git tag -d nombre_tag** sirve para eliminar el tag en el repositorio local
- **git push origin :refs/tags/nombre_tag** sirve para eliminar el tag del repositorio remoto, **Nota:** este comando va de la mano con el anterior
- **git checkout nombre_tag** sirve para cambiarme al tag, **Nota:** tener en cuenta que esto es lo mismo que realizar el cambio con checkout y poder crear una rama para pruebas apartir de ese tag con el comando **git switch -c Nombre_rama** o simplemente después de solo revisar el tag salir con **git switch -**

## Interfaz grafica de git
- **gitk** sirve para mostrar una interfaz grafica de git en vez de solo con la línea de comando, con esta interfaz se puede ver el historial a profundidad así como crear ramas, tags, busqueda de commit o autor , se puede visualizar de una mejor manera los cambios o lo agregado de cada commit
### Ayuda
- link de gitk que muestra todo lo que se puede hacer con la interfaz [click aquí](https://www.youtube.com/watch?v=aYM5v7KSYKc "click aquí")

## Github pages - pagina gratuita
- Es una herramienta que ofrece github para poder subir nuestros proyectos como paginas web, sitios, etc tener encuenta que esto solo permite ese tipo de cosas, no sirve para sistemas que usen base de datos

**¿Cómo crear mi hosting gratuito y configurarlo?**
- Primero crear una rama llamada **gh-pages**(es necesario colocar ese nombre de rama para que github pages funcione) esto creará un hosting a partir de esa rama, luego ir a ![](https://i.imgur.com/K6dHH5Q.png) y bajar hasta ![](https://i.imgur.com/7EA8yaj.png) y ahí encontraremos el link de nuestra página: ![](https://i.imgur.com/oNuou7f.png) podemos cambiar la dirección de la rama a donde queramos que se refleje el proyecto en el hosting dando click en ![](https://i.imgur.com/2VQHu6c.png) y nos aparecerá esto para poder cambiar la rama:
 
![](https://i.imgur.com/EUYaBuX.png)
### Ayuda
- Link de apoyo en youtube para crear este sitio comienza desde el minuto: **9:04** [click aquí](https://www.youtube.com/watch?v=QaxgF4v4hms&list=PLDbrnXa6SAzUyitkL4zcnWO07HxG0BvmS&index=18 "click aquí")


## .gitignore 
sirve para decirle a Git qué archivos o directorios completos debe ignorar y no subir al repositorio, archivo que se crea con ese nombre y luego se abre para escribir el nombre de las carpetas o archivos que desees que no se suban a tu repositorio 

**Ejemplo:**
- nombre_archivo.txt
- nombre_carpeta
- *.mp3 , esto es para ignorar todos los archivos con esa extensión

## Editor Vim
![](https://i.imgur.com/EdjU76E.png)

## Ayuda y consejos
- link de página para creación de readme: [click aquí](https://pandao.github.io/editor.md/en.html "Presione aquí")
- Para copiar repositorios de otros proyectos y tenerlos en mi perfil de github hacer click en ![](https://i.imgur.com/lmLEi9o.png) para clonar ese proyecto en tu perfil de github
- link de la documentación de git y github [click aquí](https://git-scm.com/book/es/v2 "click aquí")
- link de herramienta de notas donde podré guardar fotos y me daran un link para copiarlo y podre almacenar pedazos de codigo [click aquí](https://hackmd.io/EUFaQL5WTy2C9U3rDw0EUQ?both= "click aquí")
