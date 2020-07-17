# Clase 8 - YOLO y Transferencia de aprendizaje

## Video
[Parte 1](https://www.youtube.com/watch?v=DmBrDEN5pGs&feature=youtu.be)

[Parte 2](https://www.youtube.com/watch?v=E2DTFz53QtU&feature=youtu.be)


## Material
[Apuntes](https://github.com/lambdaclass/data_etudes/tree/master/clases/clase_8)

[Transferencia de aprendizaje](https://github.com/lambdaclass/data_etudes/blob/master/clases/clase_8/slides_transferencia.ipynb)

## Extras
[Imagenet](http://www.image-net.org/) es una BD de imágenes

Para detección de imágenes se pueden usar NN entrenadas con imagenet y hacer transferencia de imágenes.

[Paper sobre similitud de NN](https://arxiv.org/pdf/1905.00414.pdf)

## Dudas
**¿Qué métodos de ML funcionan mejor si los atributos tienen una forma más normal (campana de Gauss)?**

> Casi todo lo de ML tienen assumptions de normalidad pero eso implica que no puedas trabajar con procesos generadores que no son normales es un tema para cortar mucha tela y tu pregunta es muy buena. mucha gente no le da bola y es algo clave.
> En general esto es asumido por métodos paramétricos: regresiones lineales, logísticas, perceptrones, NN simples. Los NO paramétricos no asumen mucho, entonces no overfiteas ruido.. por ej random forest, KNN.



**Hay manera de ver cómo podría salir el fit de una CNN sin correr el fit entero? más que nada por lo costoso que es.. y ahora al ppio puede que cometamos errores groseros al agregar capas a la red**

> No, no hay manera. Lo que se suele hacer es correr versiones sencillas de una CNN con parámetros muy laxos para que sea lo más rápido posible y dps vas fine tuning con GPU en general la mayoría de los problemas se resuelven muy rápido.
> Buscar la manera de simplificar la ejecución, por ej usando imágenes en baja resolución.
> Entrenar con menos épocas y ver la pendiente de aprendizaje.
