# Entrega_modulo_01_Git

Entrega de la práctica del módulo 01 Git, GitHub y Gitlab

## Preguntas entrega

**¿Qué comando utilizaste en el paso 11? ¿Por qué?**
Uso el comando ***git reset hard*** para eliminar los cambios producidos en el fichero git-nuestro.md que al bajar un nodo con HEAD~1 se encuentra modificado en el working copy, con *reset --hard* cargamos la última versión almacenada en git eliminando los posibles cambios.
```
$ git reset --hard HEAD~1
```  

 **¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?**
En este caso primero se hace un ***git reflog*** para visualizar el historial de movimientos del **HEAD** y poder ir al código de identificación hash del commit que necesitamos recuperar. 

Después con el comando ***git reset*** y ***git restore*** o directamente con el comando ***git reset --hard***  recuperamos el commit en su versión original almacenada, descartando cualquier cambio adicional que pudiera tener.
```
# Para visualizar el historial
$ git reflog

# Para recuperar el commit(nodo) que necesitamos
$ git reset --hard <código id commit>
```
 
 **El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?**
No se produce ningún tipo de conflicto porque el fichero git-nuestro.md en la rama styled esta modificado con respecto a la versión del fichero almacenada en master. Por tanto son completamente diferentes, por lo que no coincide ninguna de las líneas de contenido. 

 **El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?**
Si, en este caso los ficheros tenían contenido diferente en las mismas líneas en cada una de las ramas, por tanto al querer fusionar las ramas tenemos que especificar cual de las dos versiones existentes es la que tiene que permanecer (el contenido válido final). 

 **El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?**
En este caso no se produce ningún conflicto porque el contenido es completamente diferente, en la rama master está el contenido inicial y en la rama styled la versión modificada para esta rama. Por tanto, en este caso se mantiene le contenido proveniente de la mara styled dado que es la que master está absorbiendo.

 **¿Qué comando o comandos utilizaste en el paso 25?**
Para mostrar el diagrama del árbol de nodos de git el comando empleado ha sido <mark>***git log --graph***</mark>
```
# Para visualizar el diagrama
$ git log --graph

# Otra posible alternativa más comprimida es:
git log--graph --pretty=oneline
```

 **El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?**
Si porque pertenece a una lista enlazada, no existe ningún commit inaccesible por tanto también se podría hacer con un merge por defecto (fast forward).

 **¿Qué comando o comandos utilizaste en el paso 27?**
Debemos usar un reset simple para no deshacer las modificaciones del working copy.
```
# En este caso no se deshacen los cambios del working copy
$ git reset HEAD~1
```

 **¿Qué comando o comandos utilizaste en el paso 28?**
Para descartar los cambios del working copy en el fichero git-nuestro.md recuperado al deshacer el merge de title con la rama master.
```
# Para descartar los cambios
$ git restore git-nuestro.md
```

 **¿Qué comando o comandos utilizaste en el paso 29?**
El comando para eliminar la rama title ha sido:
```
# Para eliminar la rama title
$ git branch -D title
```

 **¿Qué comando o comandos utilizaste en el paso 30?**
Primero es necesario un reflog para encontrar el identificador de la operación o último commit antes de deshacer el merge y resetear ese momento eliminando cualquier posible cambio con reset hard. De esta forma tendremos la versión con el titulo mergeado desde la rama title.
```
# Para visualizar el historial
$ git reflog

# Para recuperar el commit(nodo) que necesitamos
$ git reset --hard <código id commit>
```

 **¿Qué comando o comandos usaste en el paso 32?**
Primero es necesario un reflog para encontrar el identificador del momento que queremos rescuperar y hacer un reset --hard a ese momento a través del identificador.
```
# Para visualizar el historial
$ git reflog

# Para recuperar el commit(nodo) que necesitamos
$ git reset --hard <código id commit>
```

 **¿Qué comando o comandos usaste en el punto 33?**
 En este caso aplicamos los mismos pasos que en el punto 32, primero un reflog para localizar el commit y posteriormente un reset --hard.
```
# Para visualizar el historial
$ git reflog

# Para recuperar el commit(nodo) que necesitamos
$ git reset --hard <código id commit>
```
