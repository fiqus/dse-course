# Clase 5 - Teorema de Bayes y Time Series

## Video
https://youtu.be/sHMeq-BVLUw

## Material
[Apuntes](https://github.com/lambdaclass/data_etudes/tree/master/clases/clase_5)

[Bayes theorem](https://www.youtube.com/watch?v=HZGCoVF3YvM)

[Intuición visual del teorema](https://www.skobelevs.ie/BayesTheorem/)

https://camdavidsonpilon.github.io/Probabilistic-Programming-and-Bayesian-Methods-for-Hackers/


## Extras
https://www.clarin.com/sociedad/coronavirus-argentina-formula-matematica-explica-mismo-test-positivo-infectado_0_jIwmKK7fW.html

https://www.countbayesie.com/blog/2015/2/18/bayes-theorem-with-lego

https://towardsdatascience.com/my-secret-sauce-to-be-in-top-2-of-a-kaggle-competition-57cff0677d3c


https://github.com/lambdaclass/finance_playground

https://github.com/lambdaclass/finance_playground/tree/master/notebooks/metadata-2020/rain-forecast

El ejemplo que estaba tratando de acordarme era: un análisis de los tweets de Donald Trump donde diferenciaban entre los que había escrito Trump realmente y los que estaban escritos por un community manager, no solo eran diferentes en tono sino también en el horario en que fueron escritos. No encontre el que yo lei, pero hay varios sobre el mismo tema, como este: https://www.wired.com/story/tell-when-someone-else-tweets-from-realdonaldtrump/

## Dudas
**¿Qué diferencia hay entre score de MultinomialNB y metrics.accuracy_score? dan igual resultado**
> la métrica que definis de accuracy es arbitraria, pero en general queres ver el ratio de aciertos sobre la totalidad de samples que tenes.
> metrics.accuracy_score define/usa esta métrica por defecto.
> multinomialNB es un clasificador bayesiano/la red bayesiana más sencilla de todas. seguramente el método metrics de multinomialNB sea actualmente solamente un proxy a accuracy.metrics. no lo chequee en profundidad. paso a explicar por qué.

> Sklearn fue uno de los primeros proyectos grandes en python de machine learning y tuvo muchos refactors. originalmente seguramente el clasificador (o en este caso el mixin/la clase) implementaba su propio método de score. Esto luego se refactorizó y correctamente se armó un módulo propiamente dicho de métricas que no esté atado a los métodos de clasificación y predicción. en este commit de hace 8 años podes ver parte de ese cambio. https://github.com/scikit-learn/scikit-learn/commit/8d901badc567bef9d6a57e44198d87f5b6c6cef2

> En resumen, no hay diferencia dado que una cosa es algoritmo que te permite armar un modelo que te vincula  los x con los y, otra cosa muy distinta y arbitraria es la métrica con la cual lo evalúas.

> El hecho de que tengas el método score en multinomialnb no es más que porque el software está vivo y fue mutando. no se debe a una cuestión teórica o de que la red bayesiana tenga una forma propia y particular de medir cuán buena es.

> Yo lo hubiese volado al método, pero si tenés usuarios finales que lo usan es difícil la migración.


**Qué diferencia hay entre:**

**- count_vectorizer = CountVectorizer(stop_words='english', min_df=0.05, max_df=0.9)**

**- count_vectorizer_2 = CountVectorizer(analyzer='word',  ngram_range=(2,2))**

- el countvectorizer2 hace un análisis de ngrama por palabra en vez de carácter. es el default y no hace falta especificar el argumento analyzer= word.

> El countvectorizer utiliza un diccionario inglés para remover las palabras que no suelen aportar mucha información  (y, el, ella). a su vez utiliza el analyzer de word porque es el defecto. en general son las que se repiten mucho/tienen poca entropía. utilizar un diccionario de stop words implica que estás haciendo un analice por palabras y no por letras. en general este use case es el más común: soles querer usar un diccionario para remover lo que no es importante y analizar por palabra.

