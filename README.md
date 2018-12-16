# TESIS-UNSA-"Resumen automático de textos basado en un modelo unificado del resumen extractivo y abstractivo"
## Autor
* **Juan López Condori**
## Introducción
La generación automática de resumenes de texto suele formar parte de las aplicaciones
de minería de textos, la tarea es condensar automaticamente un trozo de texto
a una versión más corta manteniendo los puntos importantes. Hay principalmente dos
tipos de enfoques: extractivo y abstractivo.
La mayoría de estudios se enfocan en solo uno de ellos, en esta tesis se presenta un
modelo que combina ambos enfoques, los resultados obtenidos muestran que el método
propuesto es competitivo con los metodos de la literatura y, en varios casos, los superan.
## Organización
* En la carpeta evaluacion se encuentra los archivos java para realizar la evaluación
* En la carpeta papers colocamos los articulos relacionados mas importantes
* En la carpeta pointer-generator esta la RNN utilizada para el nivel extractivo
* En la carpeta textrank implementamos nuestro algoritmo textrank utilizado en nuestro modelo unificado
* En la carpeta unificado se presenta el modelo que se usa para unir el resumen extractivo con el abstractivo
* Añadimos nuestro plan, borrador de tesis y diapositivas
* El documento comandos.txt contienes los comandos necesarios para realizar los experimentos.
## Base de datos

Evaluamos nuestros modelos en el conjunto de datos de CNN / Daily Mail que contiene noticias en los sitios web de CNN y Daily Mail. Cada artículo en
este conjunto de datos está emparejado con un resumen de oraciones múltiples escrito
por el hombre.
Exactamente: 287; 113 pares de entrenamiento, 13; 368 pares de validación y 11;490
pares de prueba.
La base de datos esta habilitada en el siguiente link: [BaseDatos](http://cs.nyu.edu/~kcho/DMQA/)

## Entrenamiento
Luego de recibir el ranking de oraciones de nuestro extractor al aplicar TextRank,
entrenamos nuestro abstractor,configuramos el vocabulario con un tamaño a 50k para
el texto de origen y destino. La red con una dimensión oculta de 200. Se limita la
longitud del texto de origen a 450 y la longitud del resumen a 100.

Un modelo pre-entrenado para el Pointer-Generator: [Pre-entrenado](https://drive.google.com/file/d/0B7pQmm-OfDv7ZUhHZm9ZWEZidDg/view) 

## Pruebas 
  * Para las pruebas utilizamos las medidas ROUGE: [Rouge2](https://github.com/kavgan/ROUGE-2.0)
