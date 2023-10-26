# **Regresión Lineal Simple**

## **1.1. Modelo de Regresión Lineal Simple**

El **modelo de regresión lineal simple**, un modelo con un solo regresor o variable $x$ que tiene una relación con una respuesta $y$, donde la relación es una línea recta.Este modelo de regresión lineal simple es 

$$y = \beta_0 + \beta_1x \tag{1.1}$$                                        

donde la ordenada al origen $\beta_0$ y la pendiente $beta_1$ con constantes desconocidas, y $\epsilon$ es un componente aleatorio de error.Se supone que los errores tienen promedio cero y varianza $\sigma^2$ desconocida.Además, se suele suponer que los errores no estan correlacionados.

Conviene considerar que el regresor $x$ está controlado por el *analista de datos*, y se puede medir con error despreciable, mientras que la respuesta $y$ es una **variable aleatoria**. Con lo que hay una distribución de probabilidades de $y$ para cada valor posible de $x$. La media de esta distribución es 

$$E(y|x) = \beta_0 + \beta_1x \tag{1.2a}$$

y la varianza es

$$Var(y|x) = Var(\beta_0 + \beta_1x + \epsilon) = \sigma^2 \tag{1.2b}$$

A los parametros $\beta_0$ y $\beta_1$ se les suele llamar **coeficientes de regresión**.

## **1.2 Estimación de los parámetros por Mínimos Cuadrados**

Los parámetros $\beta_0$ y $\beta_1$ son desconocidos, y se deben estimar con los datos de la muestra. 
Supongamos que hay n pares de datos: $(x_1,y_1),(x_2,y_2),...,(x_n,y_n)$.

### **1.2.1 Estimación de Parametros**

Para estimar $\beta_0$ y $\beta_1$ se usa el **método de mínimos cuadrados**. Esto es, se estiman $\beta_0$ y $\beta_1$ tales que la suma de los cuadrados de las diferencias entre las observaciones $y_i$ y la linea recta sea mínima.Según la ecuación $(1.1)$, se puede escribir

$$y_i = \beta_0 + \beta_1x_i + \epsilon_i,    i= 1,2,..,n \tag{1.3}$$

Así, el criterio de mínimos cuadrados es

$$S(\beta_0, \beta_1) = \sum_{i=1}^{n}(y_i - \beta_0 - \beta_1x_i)^2 \tag{1.4}$$

Los estimadores, por mínimos cuadrados, de $\beta_0$ y $\beta_1$, que se designarán por $\hat{\beta}_0$ y $\hat{\beta}_1$, deben satisfacer


$${{\frac{\partial S}{\partial \beta_0}\Bigg|}_{\hat{\beta}_0 \hat{\beta}_1}} = 
-2\sum_{i=1}^{n} $$

y 

$${{\frac{\partial S}{\partial \beta_1}\Bigg|}_{\hat{\beta}_0 \hat{\beta}_1}} =-2\sum_{i=1}^{n}(y_i - \hat{\beta}_0 - \hat{\beta}_1x_i)x_i = 0$$

Se simplifican estas dos ecuaciones y se obtiene

$$n\hat{\beta}_0 +\hat{\beta}_1\sum_{i=1}^{n}x_i = \sum_{i=1}^{n}y_i$$

$$\hat{\beta}_0\sum_{i=1}^{n}x_i + \hat{\beta}_1\sum_{i=1}^{n}x_i^2 = \sum_{i=1}^{n}y_i x_i \tag{1.5}$$
