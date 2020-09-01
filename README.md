# [Platzi Data Challenge](https://platzi.com/blog/data_challenge/?utm_source=twitter&utm_medium=organic&utm_campaign=agosto&utm_content=data-challenge)

Se dará como completado el reto cuando hayas **aprobado el curso de la semana** y 
**resuleto el reto**, Ayudarás mucho difundiendo que iniciaste este reto en tus redes con
**#PlatziDataChallenge**

## Clase 1
El primer paso es que crees un entorno virtual que estaremos usando a lo largo de estos retos.
Ejecuta en la línea de comandos:

````shell script
> mkdir PlatziDataChallenged
> cd PlatZiDataChallenged
> python -m venv .venv
> .venv\Scripts\activate.bat 
````

Con ello entrarás en un entorno virtual el cual podrás confirmar con el nombre de tu entorno
entre paréntesis al lado izquierdo del prompt de la terminal. para salir solo debes escribir 
en la línea de comandos **deactivate**

El siguiente paso es crear el archivo **requirements.txt** donde estaremos agregando las
librerías que vayamos usando. Para esta primera parte solo agrega:

```shell script
pandas
numpy
jupyter
```
Seguido instalamos las librerías dentro del entorno

```shell script
> pip install -r requirements.txt
```

Luego de haber instalado las librerias a usar, corremos jupyter notebook y te dirijes al puerto
donde estará corriendo el Jupyter para así crear tu primer notebook.

```python
import pandas as pd

# Para leer yn archivo csv
df = pd.read_csv("rutaarchivo.csv")

# Si tiene tiene un separador que no sea una com, en este ejemplo uso '#'
df = pd.read_csv("rutaarchivo.csv", sep="#")

# Si el archivo no tiene el nombre de las columnas (header)
list_columns = ["col1", "col2"] # Nombre de las columnas
df = pd.read_csv("rutaArchivo.csv", names=list_columns)

# Encontrar mas información al importar en CSV con Pandas en:
# https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_csv.html

# Ver los primeros y últimos 10 registros, dentrro del parentesis
# puedes agregar la cantidad de filas a mostrar
df.head()

# Ultimos 10
df.tail()

# Ver percentiles, valor maximo, valor minimo, desviacion estandar, etc
df.describe()

# Ver tipos de datos de cada columna como tambien los valores nulos
df.info()

# Agrupaciones, el .count() es que cuente cuente las filas,
# Tambien puede ser .sum(). mena(), etc.
df.groupby(by=["Col1", "Col2"]).count()

# Borrar dos columnas
df.drop(columns=["col1", "col2"])

# Ordenar
df.sort_values(by="Col1", ascending=False)

# Eliminar valores duplicados manteniendo el primero (ojo: revisar documentacion)
# df.drop_values(subset=["Col1", keep="first"])
df.drop_duplicates(subset=["Col1", keep="first"])

# Agregar columnas de un dataframe a otro con nombres de columnas keys distintas
df.merge(df2, left_on="colName_df", right_on="ColName_df2")

# Concatenar filas de dos DataFrames, ignorando los indices
pd.concat([df, df2], ignore_index=True)

# Lambdas, Muy util para hacer operaciones fila por fila de una o mas columnas
# en un DataFrame de forma muy eficiente.
df["col1"].apply(lambda x: x*8)

# Poder visualizar todas las columnas:
pd.set_option('display.max_columns', None)

```

Comenzar con el Primer reto [PlatziDataChallenge#1](https://platzi.com/comunidad/platzidatachallenge-1/)