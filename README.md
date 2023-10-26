# **Regresión Lineal Simple**

## 1.1. Modelo de Regresión Lineal Simple

El **modelo de regresión lineal simple**, un modelo con un solo regresor o variable $x$ que tiene una relación con una respuesta $y$, donde la relación es una línea recta.Este modelo de regresión lineal simple es 

$$y = \beta_0 + \beta_1x$$

donde la ordenada al origen $\beta_0$ y la pendiente $beta_1$ con constantes desconocidas, y $\epsilon$ es un componente aleatorio de error.Se supone que los errores tienen promedio cero y varianza $\sigma^2$ desconocida.Además, se suele suponer que los errores no estan correlacionados.

Conviene considerar que el regresor $x$ está controlado por el *analista de datos*, y se puede medir con error despreciable, mientras que la respuesta $y$ es una **variable aleatoria**. Con lo que hay una distribución de probabilidades de $y$ para cada valor posible de $x$. La media de esta distribución es 

$$E(y|x) = \beta_0 + beta_1x$$

