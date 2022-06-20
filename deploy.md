Existen varias maneras de poner nuestros modelos en produccion, aca vamos a ver como hacerlo usando Streamlit y Heroku.
 

### Streamlit

Las apps de streamlit, son bastante sencillas, es un script de python normal y vamos insertando los widgets que necesitamos en el cuerpo del script. 

Un ejemplo básico, una pagina web que diga 'hola':

```python
import streamlit as st
st.write('hola!')
```
Lo guardamos en un archivo.py y para ejecutarlo:

```bash
streamlit run archivo.py
``` 
Luego desde nuestro navegador vemos nuestro mensaje.
Streamlit tiene una lista larga de widgets disponibles [aca](https://docs.streamlit.io/api.html). De manera de que podemos mostrar gráficos que interactuen con widgets como slides, inputs, etc. 

Con una sintasis muy sencilla podemos generar una interfaz web para que cualquier persona con un navegador pueda interactuar con nuestros complejos modelos de ML.

Hasta acá todo perfecto, pero... sigue funcionando de manera local; para poder tenerlo en funcionamiento online falta algo más:



### Heroku 


Heroku es una plataforma que da servicio de hosting de máquinas virtuales. 


1. Ir a [heroku.com](https://signup.heroku.com/) y registrarse.
2. Crear nueva app [aca](https://dashboard.heroku.com/new-app).
3. En el menu de la APP, ir a deploy method y seleccionar connect to Github.
4. Asociar heroku con su cuenta de github, buscar el repositorio donde tenemos nuestra app y conectar.
5. Seleccionaremos automatic deploys para que se actualicen automáticamente las versiones de nuestra app, y por último le damos a DEPLOY BRANCH.


Para crear la máquina virtual en Heroku, tenemos que especificar la versión de Python y de las librerias presentes en nuestra app; esto lo hacemos en los archivos Requirements y Runtime, que deben estar en el repositorio de github que asociamos a nuestra APP de heroku.

Ejemplo del contenido de estos archivos esta en:

https://github.com/danisa-loop/receta_ideal

```bash
Deploy.py
requirements.txt
runtime.txt
Procfile
create_config.sh
``` 


Esta app esta funcionando en:

[properatti.herokuapp.com](https://recetaideal.herokuapp.com/)


Basado en contenido creado por Fernando Carabedo.
