# Aprendizaje no supervisado

El aprendizaje supervisado es una rama de la Inteligencia Artificial que se enfoca en aprender de datos no etiquetados.
En el mundo de la IA existen dos clases de datos, los etiquetados y los no etiquetados. En los etiquetados tenemos los datos y una columna extra que nos dice un valor que nos gustaría poder predecir mediante la computadora. Por ejemplo, los datos pueden ser información sobre casas,

|Metros cuadrados|Cuartos|Baños|
|---|---|---|
|120|2|2|
|110|3|2.5|

y las etiquetas serían los precios de venta. Dados los datos, queremos predecir de manera automática las etiquetas. Las etiquetas pueden ser valores contínuos como el precio, temperatura o velocidad; aunque lo más común es que sean tomadas de una lista, como `[positivo, negativo, neutro]`. Una de las cosas más complicadas de obtener al crear un nuevo conjunto de datos son las etiquetas ya que por lo general se necesita de un humano que las asigne de manera individual. Los conjuntos de datos suelen tener muchos ejemplos para que puedan ser usados por técnicas como el aprendizaje profundo. Los pequeños tienen miles de ejemplos y los grandes pueden llegar a los millones. Etiquetar un millón de ejemplos de manera manual es muy tardado y costoso, se necesita de un ejército de etiquetadores.

Los datos no etiquetados también pueden ser usados para extraer información. Las dos tareas principales son la reducción de dimensión y la organización en grupos. En el aprendizaje no supervisado se aprende de los datos tal como son, mientras que en el supervisado se aprende a predecir a los etiquetadores. En esta unidad, vamos a ver algoritmos de agrupamiento cuyo objetivo es organizar los datos en grupos con la propiedad de que elementos de un mismo grupo sean *parecidos* y al mismo tiempo sean *diferentes* de los otros grupos. De manera formal, no hay una definición para decidir si dos elementos son *parecidos* pues depende del problema. Esta ambiguedad hace que el problema sea complejo y que no exista una solución definitiva. Esta complicación se verá de manera especial durante la sección de evaluación.

## Algoritmos de centroides

Los algorimos de centroides son los más usados y buscan puntos especiales que se usan para separar al espacio de acuerdo a su distancia. La noción de similaridad será dada por una función distancia, la más usual es la distancia euclidiana. 

Dado un conjunto de datos ${x_1, \ldots, x_m}$, el objetivo es encontrar $k$ centroides ${c_1, \ldots, c_k}$ para minimizar

$$ O = \sum _{i=1} ^{m}\min_j(d(x_i, c_j))$$

donde $d$ es la función distancia.

Queremos minimizar la distancia de cada punto a su representante (centroide) más cercano. Para esto, se hace el siguiente proceso iterativo:
1. Se eligen $k$ centroides de alguna manera (generalmente al azar)
2. Se asignan los datos a su centroide más cercano y así se crean los clusters $c_1, \ldots, c_k$
3. De cada cluster $c_i$, se elige el representante óptimo que minimiza la función

$$ \sum_{x\in C_i}d(x, c_i)$$

que se puede hacer tomando el promedio de los puntos del cluster.

Esto se repite hasta que los centroides cambian menos que un umbral establecido.


## Algoritmos de densidad

## Evaluación del agrupamiento


