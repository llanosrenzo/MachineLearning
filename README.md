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

$$y_i = \beta_0 + \beta_1x_i + \epsilon_i,  \quad  i= 1,2,..,n \tag{1.3}$$

Así, el criterio de mínimos cuadrados es

$$S(\beta_0, \beta_1) = \sum_{i=1}^{n}(y_i - \beta_0 - \beta_1x_i)^2 \tag{1.4}$$

Los estimadores, por mínimos cuadrados, de $\beta_0$ y $\beta_1$, que se designarán por $\hat{\beta}_0$ y $\hat{\beta}_1$, deben satisfacer


$${{{\frac{\partial S}{\partial \beta_0}}\Bigg|}_{\hat{\beta}_0 , \hat{\beta}_1}} =  -2\sum_{i=1}^n (y_i - \hat{\beta}_0 - \hat{\beta}_1) = 0$$

y 

$${{\frac{\partial S}{\partial\beta_1}\Bigg|}_{\hat{\beta}_0 , \hat{\beta}_1}} =-2\sum {(y_i - \hat{\beta}_0 - \hat{\beta}_1x_i)} x_i = 0$$

Se simplifican estas dos ecuaciones y se obtiene

$$n\hat{\beta}_0 + \hat{\beta}_1\sum_{i=1}^n x_i = \sum_{i=1}^n y_i$$

$$\hat{\beta}_0 \sum x_i + \hat{\beta}_1\sum x_i^2 = \sum y_i x_i \tag{1.5}$$

Las ecuaciones $(1.5)$ son llamadas **ecuaciones normales de mínimos cuadrados**. Su solución es la siguiente:

$$\hat{\beta}_0 = \overline{y} - \hat{\beta}_1\overline{x} \tag{1.6}$$

$$\hat{\beta}_1 = \frac{\sum {y_i x_i} - \frac {(\sum y_i)(\sum x_i)}{n}}{\sum {x_i^2} - \frac{(\sum {x_i})^2}{n}} \tag{1.7}$$

en donde

$$\overline {y} = \frac{1}{n}{\sum_{i=1}^{n}} {y_i} \quad ,\quad  \overline {x} = \frac{1}{n}\sum_{i=1}^{n} {x_i}$$

son los promedios de $y_i$ y $x_i$, respectivamente. Por consiguiente,$\hat{\beta}_0$ y $\hat{\beta}_1$ en las ecuaciones $(1.6)$ y $(1.7)$ son los **estimadores por mínimos cuadrados** de la ordenada al origen y la pendiente, respectivamente. El modelo ajustado de regresion lineal simple es, entonces

$$\overline {y} = \hat{\beta}_0 + \hat{\beta}_1{x} \tag{1.8}$$

La ecuación $(2.8)$ produce un estimado puntual, de la media de $y$ para una determinada $x$.

Como el denominador de la ecuación $(2.7)$ es la suma corregida de cuadrados de las $x_i$ y el numerador es la suma corregida de los productos cruzados de $x_i$ y $y_i$, estas ecuaciones se pueden escribir en una forma más compacta como sigue:

$$S_{xx} = \sum x_i^2 - \frac{(\sum x_i)^2}{n} = \sum (x_i - \overline {x})^2 \tag {1.9}$$

y

$$S_{xy} = \sum {y_i x_i} - \frac{(\sum y_i)(\sum x_i)}{n} = \sum y_i(x_i - \overline {x}) \tag{1.10}$$

Entonces, una forma de expresarse la ecuación $(1.7)$ es

$$\hat{\beta}_{1} = \frac{S_xy}{S_xx} \tag{1.11}$$

La diferencia entre el valor observado  $y_i$ y el valor ajustado correspondiente $\hat{y}_i$ se llama **residual**. Matematicamente, el i_ésimo residual es

$$e_i = y_i - \hat{y}_i = y_i - (\hat{\beta}_0 + \hat{\beta}_1 x_i), \quad i=1,2,..,,n \tag{1.12}$$

Los residuales tienen un papel muy importante para investigar la **adecuación** del modelo de regresión ajustado.

### **1.2.2 Propiedades de los estimadores por mínimos cuadrados y el modelo ajustado de regresión**

Los estimadores por cuadrados mínimos $\hat{\beta}_0$ y $\hat{\beta}_1$ tienen algunas propiedades importantes. Primero, observese que, según las ecuaciones $(1.6)$ y $(1.7)$, $\hat{\beta}_0$ y $\hat{\beta}_1$ son **combinaciones lineales** de las observaciones $y_i$.

$$\hat{\beta}_1 = \frac{S_xy}{S_xx} = \sum_{i=1}^n c_i y_i$$

donde $c_i = (x_i - \overline{x})/S_{xx}$ , para $i=1,2,...,n$

Los estimadores $\hat{\beta}_0$ y $\hat{\beta}_1$ por mínimos cuadrados son **estimadores insesgados** de los parámetros $\beta_0$ y $\beta_1$ del modelo. Para demostrarlo con $\hat{\beta}_1$, considérese

$$E(\hat{\beta}_1) = E\Bigg(\sum{c_iy_i}\Bigg) = \sum {c_iE(y_i)}$$

$$= \sum c_i(\beta_0 + \beta_1 x_i) = \beta_0\sum c_i + \beta_1 \sum c_i x_i$$

ya que , se supuso que, $E(e_i) = 0$. Ahora se puede demostrar en forma directa que 

$$\sum c_i = \sum \Bigg( \frac{x_i - \overline x}{S_{xx}} \Bigg) = \frac{1}{S_{xx}}(\sum x_i -\sum \overline {x})$$

$$= \frac {1}{S_{xx}}(n\overline{x} - n\overline{x}) = 0$$

y

$$\sum {c_i x_i} = \frac{1}{S_{xx}} \sum (x_i - \overline{x})x_i = \frac{1}{S_{xx}} S_{xx} = 1$$

entonces 

$$E(\hat{\beta}_1) = \beta_1$$

Esto es, si se supones que el modelo es correcto [que $E(y_i) = \beta_0 + \beta_1 x_i$], entonces $\hat{\beta}_1$ es un estimador insesgado de $\beta_1$. De igual manera se puede demostrar que $\hat{\beta}_0$ es un estimador insesgado de $\beta_0$, es decir,

$$E(\hat{\beta}_0) = \beta_0$$

Tenemos la siguiente demostracion:

$$y_i = \beta_0 + \beta_1x_i +e_i$$

$$\sum y_i = \sum(\beta_0 + \beta_1x_i +e_i)$$

$$\sum y_i = n \beta_0 + \beta_1 \sum x_i + \sum e_i$$

$$\frac{\sum y_i}{n} = \beta_0 +\beta_1 \frac{\sum x_i}{n}$$

$$\overline {y} = \beta_0 + \beta_1 \overline{x}$$

Luego,

$$E(\hat{\beta}_0) = E[\overline{y} - \hat{\beta}_1\overline{x}]=E[\overline {y}] - \overline{x} E[\hat{\beta}_1]$$

$$= \overline{y} - \overline {x}\beta_1 = \beta_0$$

La varianza de $\hat{\beta}_1$ se calcula como sigue:

$$Var(\hat{\beta}_1) = Var\Bigg( \sum{c_i y_i}\Bigg)$$

$$= \sum {c_i^2} Var(y_i) \tag{1.13}$$

ya que las observaciones $y_i$ son no correlacionadas, por lo que la varianza de la suma es igual a la suma de las varianzas. La varianza de cada término en la suma es $c_i^{2} Var(y_i)$ y hemos supuesto que $Var(y_i)= \sigma^2$; en consecuencia,

$$Var(\hat{\beta}_1) = \sigma^2 \sum {c_i^2} = \frac{\sigma^2 \sum(x_i - \overline{x})^2}{S_x^2}$$


$$= \frac{\sigma^2}{S_{xx}} \tag{1.14}$$

La varianza de $\hat{\beta}_0$ es 

$$Var(\hat{\beta}_0) = Var(\overline{y} - \hat{\beta}_1 \overline{x})$$

$$= Var(\overline{y}) + \overline{x}^2 Var(\hat{\beta}_1) - 2\overline{x} Cov(\overline{y}\hat{\beta}_1)$$

Ahora bien, la varianza de $\overline{y}$ no es más que $Var(\overline{y}) = \sigma^2/n$, y se puede demostrar que la co-varianza entre $\overline{y}$ y $\hat{\beta}_1$ es cero. Así,

$$Var(\hat{\beta}_0) = Var(\overline {y}) + \overline{x}^2Var(\hat{\beta}_1)$$

$$= \sigma^2 \Bigg( \frac{1}{n} + \frac{\overline{x}^2}{S_{xx}} \Bigg) \tag{1.15}$$

Otro resultado importante acerca de la calidad de los estimadores por mínimos cuadrados $\hat{\beta}_0$ y $\hat{\beta}_1$ es el **teorema de Gauss-Markov**, que establece que para el modelo de regresión (1.1) con las hipótesis $E(e)=0$, $Var(e) = \sigma^2$ y con errores no correlacionados, los estimadores por mínimos cuadrados son insesgados y tienen varianza mìnima en comparación con todos los demás estimadores insesgados que sean combinaciones lineales de las $y_i$. Con frecuencia se dice que los estimadores por mínimos cuadrados son los **estimadores lineales insesgados óptimos**, donde "óptimos" implica que son de varianza mínima.

Hay varias otras propiedades útiles por mínimos cuadrados:

**1.** La suma de los residuales en cualquier modelño de regresión que contenga una ordenada al origen $\beta_0$ siempre es igual a cero, esto es,

$$\sum_{i=1}^{n} {(y_i - \hat{y}_i)} = \sum {e_i} = 0$$


**2.** La suma de los valores observados $y_i$ es igual a la suma de los valores ajustados $\hat{y}_i$

$$\sum_{i=1}^{n} y_i = \sum_{i=1}^{n} \hat{y}_i$$

**3.** La línea de regresión de mínimos cuadrados siempre pasa por el **centroide** de los datos, que es el punto $(\overline{x}, \overline{y})$.

**4.** La suma de los residuales, ponderados por el valor correspondiente de la variable regresora, siempre es igual a cero:

$$\sum_{i=1}^{n} {x_i e_i} = 0$$

**5.** La suma de los residuales,ponderados por el valor ajustado correspondiente, siempre es igual a cero:

$$\sum_{i=1}^{n} {\hat{y}_i e_i} = 0$$

### **1.2.3 Estimacion de**\n
$\sigma^2$

Además de estimar $\beta_0$ y $\beta_1$, se requiere un estimado de $\sigma^2$ para probar hipótesis y formar estimados de intervalo pertinentes al modelo de regresión. El estimado de $\sigma^2$ se obtiene de la suma de cuadrados de residuales, o la suma de cuadrados de error:

$$SS_{res} = \sum {e_i^2} = \sum {(y_i - \hat{y}_i)^2} \tag{1.16}$$

Se puede deducir una formula cómoda para calcular $SS_{Res}$ sustituyendo $\hat{y}_i = \hat{\beta}_0 + \hat{\beta}_{1} x_i$ en la ecuación $(1.16)$, y simplificando

Así se llega a

$$SS_{res} = \sum{y_i^2} = n{\overline{y}^2} - \hat{\beta}_1 S_{xy} \tag{1.17}$$

Pero

$$\sum{y_i^2} - n{\overline{y}^2} = \sum(y_i - \overline{y})^2 = SS_{T}$$

es justo la suma de cuadrados corregida, de las observaciones de la respuesta, por lo que

$${SS_{res}} = SS_{T} - \hat{\beta}_1 {S_{xy}} \tag{1.18}$$

La suma de cuadrados de residuales tiene $n-2$ grados de libertad, porque dos grados de libertad se asocian con los estimados $\beta_0$ y $\beta_1$ que se usan para obtener $\hat{y}_i$. Tenemos el valor esperadode ${SS_{Res}}$ es $E(SS_{Res}) = (n-2)\sigma^2$, por lo que un **estimador insesgados de** $\sigma^2$ es 

$$\hat{\sigma}^2 = \frac{SS_{Res}}{n-2} = MS_{Res} \tag{1.19}$$

La expresion $MS_{Res}$ se llama **cuadrado medio residual**. La raiz cuadrada de $\hat{\sigma}^2$ se llama, el **error estándar de la regresión**.



## **1.3 Prueba de Hipotesis**

**1.3.1 Uso de las pruebas** *t*
Supongamos que se desea probar la hipótesis que la pendiente es igual a una constante, por ejemplo, a $\beta_{10}$

$$H_0 : \beta_1 = \beta_{10}$$

$$H_1 : \beta_1 \neq \beta_{10}$$

Comúnmente se desconoce $\sigma^2$. Se sabe que $MS_{res}$ es un estimador insesgado de $\sigma^2$. Tenemos que $(n-2)MS_{res}/\sigma^2$ tiene una distribución $\chi_{n-2}^2$ y que $MS_{res}$ Y $\hat{\beta}_1$ son independientes.

Estadístico de Prueba *t*

$$t_0 = \frac{\hat{\beta}_1 - \beta_k}{\sqrt{MS_{res}/S_{xx}}}$$

sigue una distribucion $t_{n-2}$ si es cierta la hipotesis nula $H_0 : \beta_1 = \beta_k$

Se rechaza la hipótesis nula si

$$|t_0| > t_{\alpha /2 , n-2}$$

También se podría usar el método del valor *P* para tomar la decisión.

El denominador del estadistico $t_0$ en la ecuación se llama con frecuencia el **error estándar estimado**, o más sencillamente el **error estándar** de la pendiente.

$$se(\hat{\beta}_1) = \sqrt{\frac{MS_{res}}{S_{xx}}}$$
## **Coeficiente de Determinación**

Tenemos lo siguiente 

$$R^2 = \frac{SS_R}{SS_T} = 1 - \frac{SS_Res}{SS_T} 	\tag{1.47}$$

se llama **coeficiente de determinación**. 

$R^2$ se interpreta, con frecuencia, la proporción de la variación explicada por el regresor $x$. Ya que $0 \leq SS_{Res} \leq SS_T$, entonces $0 \leq R^2 \leq 1$
