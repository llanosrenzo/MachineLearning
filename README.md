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

### **1.2.1 Estimación de $\beta_0$ y $\beta_1$ **

Para estimar $\beta_0$ y $\beta_1$ se usa el **método de mínimos cuadrados**. Esto es, se estiman $\beta_0$ y $\beta_1$ tales que la suma de los cuadrados de las diferencias entre las observaciones $y_i$ y la linea recta sea mínima.Según la ecuación