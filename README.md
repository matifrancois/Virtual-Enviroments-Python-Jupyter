# Virtual-Enviroments-Python-Jupyter

Esta es una guía básica para el manejo de entornos virtuales:

## Entornos virtuales

- Creacion de entornos virtuales:

```console
python -m venv env
```


Con eso creaste un virtual enviroment que se llama env.

- Para activarlo hay que hacer:

```console
env\Scripts\activate.bat
```

Y listo, estás adentro.

- Para desactivar es:

```console
deactivate
```


## Entornos en Jupyter Lab:

- Para hacer correr el entorno virtual en jupyter lab:

Con el entorno virtual activado en la misma terminal ir hasta donde esté el ejecutable jupyter.exe
En mi caso esta en: 

"C:\Users\Usuario\Python\Lib\site-packages"

y ahí pones: 

```console
python -m ipykernel install --user --name=myenv
```

Eso va a linkear el entorno en el que estás con jupyter, esto lo hace con --name=myenv. Ese "myenv" es el nombre que va a tener en jupyter, así que hay que utilizar un nombre mas descriptivo quizás. Una vez hecho esto desde jupyter te va a dejar seleccionar el kernel que prefieras y myenv va a aparecer como una opción.

- Luego para "desinstalarlo de jupyter" tenes que:

Con el entorno virtual ya activado, desde ahi dentro en la consola te vas a donde tenes el jupyter.exe en mi caso es:

"C:\Users\Usuario\Python\Lib\site-packages"

y ahí pones: 

```console
jupyter kernelspec uninstall myenv
```

donde myenv es el nombre que le pusiste al entorno en jupyter.

- Despues para terminar de no dejar registro del entorno tenes que hacer:

```console
deactivate.
```

- Luego ir hasta la ubicación del entorno virtual y borrarlo.

## Dependencias del entorno virtual.

No te olvides de antes de eliminar el enornto crear un txt con todas las dependencias que tenías instaladas en el entorno virtual, para que otra persona pueda seguir tus pasos corriendo el código con las mismas versiones de las bibliotecas que utilizaste.

Para eso tenes:

```console
pip list
```

Ese comando te lista todas las dependencias que tenés.

Otro comando que lista las dependencias pero de manera más útil es: 

```console
pip freeze
```

Con ese comando se listan las dependencias igual que el anterior sólo que de una forma más cómoda para después instalar las dependencias. 

Y la forma más fácil y util de obtener todas las dependencias del entorno virtual finalmente es con el siguiente comando:

```console
pip freeze > requirements.txt
```

Con este comando generamos un txt que podemos despues utilizarlo para pasar las dependencias a otra persona para que las instale en su entorno virtual en un toque.

```
Ojo el unico tema de esa linea es que hay que correrla donde queramos que guarde el requierements.txt, sino lo termina creando a ese archivo en el lugar donde estés y eso puede que no sea lo que estas buscando, asi que asegurate de moverte en la consola hasta la carpeta de tu proyecto y ahí correr esa línea.
```