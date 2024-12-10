Práctica 2. Inferencia Estadística.

Grado en Ciencia e Ingeniería de Datos. Universidad Rey Juan Carlos

Isaac Martín

2024-11-13

> **Introducción**

Existen varias formulas que describen cómo calcular el tamaño muestra
necesario para comparar una proporción con un valor de referencia. En
esta práctica vamos a seguir los argumentos usados por Whitehead (1983)
que permite derivar varias de estas fórmulas a partir de una teoría
unificada, que además puede ser usada en diseños de experimentos.

> Consideremos una secuencia *X*1*, . . . , Xn* de variables aleatorias
> bernoulli i.i.d. con probabilidad de éxito igual a *p*. Queremos
> testear la hipótesis:\
> *H*0 : *p* = *p*0
>
> Esto es equivalente a contrastar si un parámetro *θ* es igual a cero,
> siendo *θ* = *g*(*p, p*0), y *g* una función que parametriza la
> diferencia entre *p* y *p*0.
>
> Se pide
>
> 1\. Demostrar que la log-verosimilitud de *p* basada en *n*
> observaciones es:
>
> *p*\
> *ℓ*(*p*) = *r × log* 1 *−p* + *n × log*(1 *−p*)
>
> Donde *r* = *x*1 + *x*2 + *. . .* + *xn* es la suma de las respuestas
> en las *n* observaciones. ¿Qué distribución sigue la suma de *n*
> variables aleatorias Bernoulli i.i.d?
>
> El estadístico *Z* calculado como:

+-----------+-----------+-----------+-----------+-----------+-----------+
| *Z* =     | > *∂*\    | *θ*=0     | =         | *∂θp      | > *θ*=0   |
|           | > *       |           |           | ∂         |           |
|           | ∂θl*(*θ*) |           |           | ∂pl*(*p*) |           |
+===========+===========+===========+===========+===========+===========+
+-----------+-----------+-----------+-----------+-----------+-----------+

> es una medida de la diferencia entre *p* y *p*0.

+-----------------------+-----------------------+-----------------------+
| > Sea el estadístico  |                       |                       |
| > *V* = *∂θp* *∂* 2   |                       |                       |
| > *I*(*p*)*θ*=0la     |                       |                       |
| > información que *Z* |                       |                       |
| > posee sobre *θ*,    |                       |                       |
| > donde *I*(*p*) es   |                       |                       |
| > la información de   |                       |                       |
|                       |                       |                       |
| Fisher. En            |                       |                       |
| estadística, la       |                       |                       |
| cantidad de           |                       |                       |
| información de Fisher |                       |                       |
| se define para un     |                       |                       |
| parámetro *p* y       |                       |                       |
| proporciona una       |                       |                       |
|                       |                       |                       |
| > medida de precisión |                       |                       |
| > en la estimación de |                       |                       |
| > ese parámetro en    |                       |                       |
| > una muestra.        |                       |                       |
+=======================+=======================+=======================+
| Sabiendo que *I*(*p*) | *∂p*2 *l*(*p*)*∂*2    | > .                   |
| = *−E*                |                       |                       |
+-----------------------+-----------------------+-----------------------+
| > Se pide:            |                       |                       |
+-----------------------+-----------------------+-----------------------+

> 2\. Demuestra que en el caso de la variable Bernoulli de parámetro
> *p*, la información de Fisher sobre *p* en una muestra de tamaño *n*
> es igual a *p*(1*−p*).
>
> La fórmula para *Z* y *V* son diferentes dependiente de la forma en la
> que se parametriza la diferencia entre *p* y *p*0.
>
> Se pide:

1

> 3\. Calcular las expresiones de *Z* y *V* para las siguientes
> parametrizaciones de *θ*:• *θ* = *log*(*p*(1*~~−~~p*[0]{.underline})
> *p*0[(1]{.underline}*−p*[)]{.underline})\
> • *θ* = *p −p*0\
> • *θ* = *arcsin√p −arcsin√p*0
>
> **Constraste de hipótesis**
>
> Para valores de *n* suficientemente grandes y pequeños valores de *θ*,
> la distribución de *Z* es aproximadamente Normal con media *θ × V* y
> varianza *V* .
>
> Se pide:\
> 4. Presentar un código en R, comentado convenientemente para el
> cálculo de Z y V en cada una de las parametrizaciones propuestas.
>
> 5\. Simular para una muestra de tamaño 1000, el contraste de hipótesis
> siguiente:

*H*0 : *p* = 0*.*3

*H*1 : *p \>* 0*.*3

> **Cálculo del tamaño muestral**

valor de referencia *k*, entonce la hipótesis nula se rechaza con nivel
de significatividad *α*. En ese caso, puede *Z* se usa como estadístico
de contraste con nivel de significatividad *α* y potencia 1 *−β*. Si *Z*
es mayor que un concluirse que la proporción es superior a la
establecida en la hipótesis de partida. Los requerimientos para este
test (unilateral) son:\
*P*(*Z ≥k\|H*0 : *θ* = 0) = *α*\
*P*(*Z ≥k\|H*1 : *θ* = *θR*) = 1 *−β*\
donde *θR* es la diferencia que, si está presente, se desea detectar. Un
ensayo muestral fijo satisface estos requerimientos cuando la cantidad
de información *V* está dada por:

+-----------------------+-----------------------+-----------------------+
| *V* =                 | *zα/*2 + *zβ*         | > 2                   |
+=======================+=======================+=======================+
| *V*                   | *θR*                  |                       |
+-----------------------+-----------------------+-----------------------+

> donde *zτ* denota el percentil 100(1 *−τ*) de una distribución normal
> de media 0 y desviación típica 1.
>
> Se pide:\
> 6. Emplear la fórmula anterior para obtener una fórmula para el tamaño
> muestral necesario para realizar el contraste con la potencia deseada
> en cada una de las parametrizaciones de *θ* consideradas
> anteriormente.
>
> **Potencia y error de tipo I**
>
> En nuestro estudio, *p*0 es 0*.*003 y el valor de *p* que deseamos
> detectar es 0*.*006.
>
> Se pide:\
> 7. Emplear los resultados del último ejercicio con nivel *α* = 0*.*025
> y potencia 0*.*80 para estimar el tamaño de muestra necesario en este
> caso particular, para cada una de las parametrizaciones del
> estadístico. 8. Estimar los errores tipo I y la potencia del contraste
> basado en *Z* y *V* para cada una de los tamaños de muestra y
> parametrizaciones anteriores.
>
> 9\. Emplear además los contrastes siguientes:

2

> • Test de chi-cuadrado sin corrección de continuidad. 'chisq.test(x =
> c(r, n - r), p = c(p0, 1 - p0), correct = FALSE)'\
> • Prueba exacta. Función 'binom.test(r, n, p0, alternative =
> "greater")' .
>
> 10\. Como se ha explicado en clase, an algunas situaciones, las
> suposiciones necesarias para aplicar pruebas paramétricas no se
> cumplen, por lo que es necesario utilizar pruebas no paramétricas.
> Sugiere quéprueba no parámtrica podría emplearse para comparar una
> proporción con un valor de referencia. Escribe el código en R para
> realizar dicha prueba.

**Referencias**

> • Whitehead, J., & Stratton, I. (1983). Group sequential clinical
> trials with triangular continuation regions. Biometrics, 227-236.

3
