las configuraciones se guardan en la raiz .gitconfig
C:\Users\Sugo\.gitconfig
git config --global --list

<!--~ --------------------------------------------------------------------------------- -->

# Comandos Git

touch <nombre.ext> <!-- Crea archivo -->
git checkout <file> <!-- Regresa el archivo al ultimo Commit -->
git checkout <id_commit> <!--! Regresa el proyecto al Commit mencionado - OJO: Si te queda algun archivo en "staged", puede que pierdas datos, debes hacer un commit antes de continuar -->
git reset <!-- Muestra los ficheros que se han modificado, pero que pueden volver al ultimo commit -->
git log --graph <!-- Te muestra el log de commit con un graph -->
git log --graph --pretty=oneline <!-- Te muestra el log del commit mas resumnido -->
git log --decorate --all --oneline <!-- Decora todo en una linea -->
git config --global alias.<nombre> "log --graph --decorate --all --oneline" <!-- Agrega un alias al comando, se puede cambiar en la configuracion en .gitconfig, en este caso si el alias es tree, se debe invocar con "git tree" -->
git config --global --unset alias.<nombre> <!--  -->
git config --global --unset-all 
git reset --hard <id_commit> <!--! Te situa en el Commit mencionado - OJO: Borra todas las instancias de Commit futuras al ID Commit mencionado -->
git reflog <!--! Es el log de todo los cambios que se han realizado, incluso estan las commit que se borraron con "git reset --hard <id_commit>" --> 
<!--^ Supongamos que tengo el Commit 1, 2, 3, 4 y 5. Donde el Commit 5 es el mas actualizado. Si hiciera un "git reset --hard <id_commit_2>", perderia los Commit del 3 al 5. Al ejecutar el commando "git reflog" puedo ver todos los cambios e incluso obtener el id del commit 5, obteniendo el id, se puede recuperar todo con nuevamente el comando "git reset --hard <id_commit_5>"-->
git tag <!-- Muestra los tags creados -->
git tag <nombre_tag> <!-- Le pone un tag a todo lo que hagamos hasta el commit -->
git checkout tags <nombre_tag> <!--! Regresa el proyecto al Commit del "tag" mencionado - OJO: Si te queda algun archivo en "staged", puede que pierdas datos, debes hacer un commit antes de continuar -->

<!--~ --------------------------------------------------------------------------------- -->

# Comandos Git para Branch/Rama

git branch <!-- Indica en la rama que estas posicionado -->
git branch <nombre> <!-- Crea una Ramas -->
git branch -m <nombre> <!-- Cambia el nombre de la Ramas -->
git switch <nombre> <!-- Cambia de Ramas y no hay problema si las Ramas estan en tu local -->
git checkout <nombre> <!--! Cambia de Ramas pero te descarga el contenido si la Ramas no esta en tu local -->
git merge <nombre_rama> <!--! Junta las ramas  -->
<!--^ Debes estar situado en la rama donde quieras que se traiga la informacion, si tiene 2 ramas, y trabajas en la rama 2, y quieres traerte los cambios actualizados de la rama 1, entonces debes estar en la rama 2 "git branch" y ejecutar el comando "" -->
git stash <!-- Guarda el archivo que se esta trabajando sin realizar un commit -->
git stash list <!-- Muestra los diferentes Stash -->
git stash pop <!-- Obtienes el archivo con el error para seguir trabajando en el -->
git stash drop <!-- Elimina lo que tienes guardado en el git stash -->
git branch -d <nombre> <!-- Elimina la rama seleccionada  -->

<!--~ --------------------------------------------------------------------------------- -->

# Primeros Comandos Git Hub (Debes tener usuario en Git Hub)
ls -al ~/.ssh <!-- Listar claves SSH -->
cat <nombre> <!-- Leer archivo -->
ssh -T git@github.com <!-- Verificar la conexion a github -->
<!--^ Despues de crear un nuevo repositorio -->
git remote add origin git@github.com:sugofc/curso-git2.git <!-- Comando que te da Git Hub para conectar tu proyecto al repositorio creado -->
git push -u origin main <!-- Crea el primer push para subir tu proyecto al repositorio -->

<!--~ --------------------------------------------------------------------------------- -->

# Comandos GitHub
git push <!-- Sube tu proyecto al repositorio -->
git fetch <!-- Descarga en local el historial de cambios, pero sin descargarse los cambios -->
git pull <!-- Descarga en local el historial de cambios y tambien se descarga los cambios -->