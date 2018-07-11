--- 
title: "Programación Científica en R"
subtitle: "Ciencia de los Datos Financieros"
author: "Synergy Vision"
date: "2018-07-11"
knit: "bookdown::render_book"
documentclass: krantz
bibliography: [book.bib, packages.bib]
biblio-style: apalike
link-citations: yes
colorlinks: yes
lot: yes
lof: yes
fontsize: 12pt
monofontoptions: "Scale=0.8"
keep_md: yes
site: bookdown::bookdown_site
description: ""
url: 'http\://synergy.vision/Programacion-Cientifica-en-R/'
github-repo: synergyvision/Programacion-Cientifica-en-R/
cover-image: images/cover.png
---

# Prefacio {-}

Placeholder


## ¿Por qué  leer este libro? {-}
## Estructura del libro {-}
## Información sobre los programas y convenciones {-}
## Prácticas interactivas con R {-}
## Agradecimientos {-}

<!--chapter:end:index.Rmd-->


# Acerca del Autor {-}

Este material es un esfuerzo de equipo en Synergy Vision, (<http://synergy.vision/nosotros/>).		 

El propósito de este material es ofrecer una experiencia de aprendizaje distinta y enfocada en el estudiante. El propósito es que realmente aprenda y practique con mucha intensidad. La idea es cambiar el modelo de clases magistrales y ofrecer una experiencia más centrada en el estudiante y menos centrado en el profesor. Para los temas más técnicos y avanzados es necesario trabajar de la mano con el estudiante y asistirlo en el proceso de aprendizaje con prácticas guiadas, material en línea e interactivo, videos, evaluación contínua de brechas y entendimiento, entre otros, para procurar el dominio de la materia.
  		  
Nuestro foco es la Ciencia de los Datos Financieros y para ello se desarrollará material sobre: **Probabilidad y Estadística Matemática en R**, **Programación Científica en R**, **Mercados**, **Inversiones y Trading**, **Datos y Modelos Financieros en R**, **Renta Fija**, **Inmunización de Carteras de Renta Fija**, **Teoría de Riesgo en R**, **Finanzas Cuantitativas**, **Ingeniería Financiera**, **Procesos Estocásticos en R**, **Series de Tiempo en R**, **Ciencia de los Datos**, **Ciencia de los Datos Financieros**, **Simulación en R**, **Desarrollo de Aplicaciones Interactivas en R**, **Minería de Datos**, **Aprendizaje Estadístico**, **Estadística Multivariante**, **Riesgo de Crédito**, **Riesgo de Liquidez**, **Riesgo de Mercado**, **Riesgo Operacional**, **Riesgo de Cambio**, **Análisis Técnico**, **Inversión Visual**, **Finanzas**, **Finanzas Corporativas**, **Valoración**, **Teoría de Portafolio**, entre otros.

Nuestra cuenta de Twitter es (https://twitter.com/bysynergyvision) y nuestros repositorios están en GitHub (https://github.com/synergyvision).
  		  
 **Somos Científicos de Datos Financieros**

<!--chapter:end:000-author.Rmd-->


# Introducción

Placeholder


## Características principales del lenguaje __R__
## Desventajas del lenguaje __R__
## El diseño del lenguaje __R__
## Instalación de __R__ y de paquetes de __R__
## Ayuda en __R__
## RStudio

<!--chapter:end:001-Introduccion.Rmd-->

# Objetos en __R__

Cuando nos referimos a objetos estamos hablando de entidades que combinan estado (atributo), comportamiento (método) e identidad; esto quiere decir, un objeto estará compuesto por datos también llamados atributos que tendrán valores concretos, con estos objetos se realizarán algunos procedimiento o método, esto corresponde al comportamiento que pueda tener dicho objeto, además todos los objetos se pueden identificar o diferenciar entre todos los demás a esto es lo que llamados identidad del mismo. Cuando los lenguajes de programación se basan en este paradigma es muy util a la hora de reutilizar códigos o métodos, logrando mejorar o simplemente flexibilizar, ajustar dicho código a situaciones particulares.

Los principales objetos con los que se trabajan con este lenguaje de programación son:

- Vector.

- Factor.

- Arreglo.

- Matriz.

- Data frame.

- Series de tiempo.

- Listas.

| **Objeto** |         **Tipos**         | **¿Varios tipos posibles?**|
|:----------:|:-------------------------:|:--------------------------:|
|   Vector   | N, C, Comp o Log          |            No              |
|   Factor   | N o C                     |            No              |
|   Arreglo  | N, C, Comp o Log          |            No              |
|   Matriz   | N, C, Comp o Log          |            No              |
| Data.frame | N, C, Comp o Log          |            Si              |
|   S.T      | N, C, Comp o Log          |            Si              |
|   Lista    | N, C, Comp,Log, Fun, Expr.|            Si              |

N = numérico  
C = caracter  
Comp = complejo  
Log = lógico  
Fun = función  
Expr = expresión 


## Tipos de objetos en __R__

Entre los principales objetos tenemos:

- __Datos Numéricos__: 

Dentro de los datos numéricos tenemos datos “numeric”, enteros “integer”,  complejo “complex”. La mayor parte del tiempo los números son “numeric”. 

Cualquier número real se puede expresar mediante notación científica, esto es diviendo o multiplicando por 10 tantas veces como sea necesario para que todos los dígitos aparezcan a la derecha del punto decimal y de modo que el primer dígito después del punto no sea cero, por ejemplo $7325.689=7.325689\times 10^4$. Con el lenguaje de programación __R__ la notación científica se imprime con una `e` para indicar el exponente, para continuar con el ejemplo anterior la notación en __R__ sería $7.325689e+4$. Esta notación se utiliza para almacenar los datos numéricos, lo que comumente se llama almacenamiento de punto flotante, el cual consta de tres partes: un signo (+1 ó -1), un exponente (un enteno $n$) y una precisión ($p$) $\pm 1\times p\times 10^n$.

Una de las maneras de trabajar con un dato entero es colocarle como sufijo la letra `L`, por ejemplo el entero uno se puede escribir como `1L`, también podemos tranformar valores numéricos a enteros con el comando `as.integer()`. 

Es importante acotar que la representación de punto flotante no puede almacenar todos los números con exactitud, por ejemplo, la raíz cuadrada de 2 es irracional y la representación en la computadora (de punto flotante) es una aproximación

- __Datos Categóricos__: 

__R__ tiene dos clases distintas para trabajar con datos categóricos: Factor y carácter.

Los datos de tipo **Factor** se utiliza cuando se tienen variables que se pueden registrar simplemente por medio de categorías, utilizadas para agrupar los datos, un ejemplo de este tipo de datos podría ser el historial de los distintos navegadores usados por los usuarios para acceder a un sitio web, así los datos se podrían agrupar dependendiendo del servidor que usaron los usuarios.

Los datos de tipo **carácter** son los que representan palabras o códigos únicos que identifican, como por ejemplo una dirección de un ordenador, también llamados _string_ por su traducción en ingles; este tipo de datos en __R__ se colocan utilizando comillas dobles `"` o simples `'` para delimitar un string.

- __Datos Lógico__: 

Estos datos también son llamados datos Booleanos, se caracterizan por tomar dos valores verdadero ó falso (TRUE o FALSE), generalmente se obtienen como el resultado de alguna función, por ejemplo podemos usar la función `is.numeric()` para saber si una variable o cualquier objeto que se introduzca cumple con las características de ser un valor numérico, en caso de ser cierto la función retornará `TRUE` y en caso contrario retornará `FALSE`.

- __Datos de Fecha y Hora__:

En la base del lenguaje de programación de __R__ se encuentran dos paquetes que trabajan los datos de tipo fecha y hora: `Date` (fechas) y `POSIXt` (fecha, hora y huso horario), las siglas POSIX se refieren a _Portable Operating System Interface_; esta última clase contiene dos subclases, `POSIXct` y `POSIXlt` que se diferencian simplemente en la forma en que almacenan internamente la fecha y la hora. Adicional a estos paquetes se encuentra el paquete `lubridate` el cual suele ser muy util para la extracción de componentes de un objeto fecha y hora de clase `POSIXct`.

- __Valores pérdidos, NA__:

Generalmente cuando se realizan encuestas o se toman datos se puede presentar la situación de que para ciertos individuos o categorias no se consigan datos, a este tipo de datos se les llama datos faltantes, o valores pérdidos; son valores que no están presentes. El lenguaje de programación __R__ los trata como `NA`, debido a las siglas en ingles de _not available_, cabe destacar que no es un string sino un tipo de objeto, estos valores pueden alterar los resultados que nos den algunas funciones.

- __Inf__:

Muchos cálculos nos pueden llevar a respuestas con valor infinito positivo o infinito negativo, en __R__ estos objetos se presentan por `Inf` y `-Inf`. Estos resultados se pueden tener cuando se realizan operaciones como 1/0

- __NaN__:

El nombre `NaN` se debe a su significado en ingles "not a number", es decir, no es un número. Este tipo de objeto se da cuando se realiza una operación que no da un valor numérico, por ejemplo una función indeterminada (como la división 0/0) o el resultado de una función evaluada en valores que no pertenecen a su dominio.

Un valor `NaN` es al mismo tiempo un valor `NA`, pero no al contrario. Tanto `NaN` como `NA` son ambos datos faltantes, la única diferencia es que `NaN` se produce de una operación matemática.

- __NULL__:

Generalmente indica que alguna acción no se puede ejecutar por no estar definida o disponible. Representa los objetos nulos.  Indica la ausencia del dato. Se utiliza para colocar una variable sin valor, como por ejemplo, para inicializar un vector que se va a utilizar como vector incremental.

Más adelante trabajaremos por separado otros objetos muy usados a la hora de programar en __R__.

## Manejo de Objetos

### Atributos de un Objeto

Los atributos de un objeto es la información específica sobre dicho objeto. Entre los principales encontramos:

- Nombres (`names`) : Este muestra las etiquetas de los elementos individuales de un vector o una lista.

- Dimensiones (`dimensions`): Dimensiones de los arrays (alguna puede ser cero).

- Dimnames (`dimnames`): Nombre correspondiente a las dimensiones de los arrays.

- Modo (`mode`): Tipo básico en un vector o array (lógico, entero, real, carácter, entre otros).

- Tipo (`typeof`): Tipo de los vectores o arrays (lógico, entero, double, complejo, carácter, entre otros).

- Clase (`class`): Vector alfanumérico con la lista de las clases del objeto.

- Otros: Otros atributos definidos por el usuario.

Todo objeto tiene dos atributos intrínsecos como tal; tipo y longitud.

- __Tipo__: Numérico, caracter, complejo y lógico (Verdadero o Falso).

- __Longitud__: Número de elementos en el objeto.
  
Para ver el tipo y la longitud de un objeto utilizamos las funciones `mode()` y `length()`.

Mediante la función `attributes()` podemos obtener una lista de los atributos no intrínsecos y con `attr()` podemos usar un atributo seleccionado.

### Nombres válidos para un objeto

Los nombres válidos para los objetos pueden ser el resultado de combinaciones entre letras números y el punto.

Estos son sensibles a las mayúsculas y minúsculas (`a` es diferente de `A`).  

Se recomienda usar nombres distintos a los usados ya en funciones creadas en los paquetes cargados, en especial a las de los paquetes base (por ejemplo `function`, `if`, `c`).

### Operador de asignación e igualdad

Las asignaciones de nombres a objetos se hace mediante el operador `<-` o equivalente `->`, hay que tomar en cuenta que estos símbolos no llevan espacio entre ellos. Por otra parte, se recomienda usar el símbolo `=` unicamente para los argumentos de las funciones.


```r
x <- 4
x
```

```
## [1] 4
```

```r
5 -> x
x
```

```
## [1] 5
```


```r
b <- 5
```


```r
# Crear un objeto a, igual a 5


# Imprimir el objeto a
```


```r
# Crear un objeto a, igual a 5
a <- 5

# Imprimir el objeto a
a
```

```
## [1] 5
```

## Principales funciones para trabajar en la consola

Entre las funciones más comunes y utilizadas tenemos:

- `ls()` -> Lista los elementos objetos creados en la consola. sólo muestra los nombres de los mismos.


```r
name <- "Carmen"; n1 <- 10; n2 <- 100; m <- 0.5
ls()
```

```
## [1] "a"    "b"    "m"    "n1"   "n2"   "name" "x"
```

- `ls.str()` -> Muestra algunos detalles de los objetos en memoria.


```r
ls.str()
```

```
## a :  num 5
## b :  num 5
## m :  num 0.5
## n1 :  num 10
## n2 :  num 100
## name :  chr "Carmen"
## x :  num 5
```

- `rm()` -> Para borrar objetos en memoria.


```r
rm(n1) #Eliminar el objeto n1
ls()
```

```
## [1] "a"    "b"    "m"    "n2"   "name" "x"
```

```r
rm(list=ls()) #Eliminar todos los objetos creados
ls()
```

```
## character(0)
```

- `paste()`  -> Esta función une todos los vectores de caracteres que se le suministran y construye una sola cadena de caracteres.


```r
paste("Aprendiendo", "a", "programar","con","R") 
```

```
## [1] "Aprendiendo a programar con R"
```

- `abs()` -> calcula el valor absoluto de un valor.


```r
y <- 5-8
abs(y)
```

```
## [1] 3
```

- `round()` -> redondea un número a los decimales que se le indiquen.


```r
round(0.1475945131, 3)
```

```
## [1] 0.148
```

- `sort()` -> ordena un vector que se le indique.


```r
sort(c(8,6,4,2,8,6,4,2))
```

```
## [1] 2 2 4 4 6 6 8 8
```

- `is.algo()` -> indica el tipo de estructura de datos y regresa un valor lógico.


```r
is.list(c(1,2,3))
```

```
## [1] FALSE
```

- `mean()` -> se utiliza para calcular el promedio aritmético de los elementos evaluados.


```r
mean(c(5,8,9,15,17,64,9,5,8,8,8,17,64,5))
```

```
## [1] 17.28571
```

La forma general de usar la función `mean` es `mean(x, ...)`, donde `(...)` es llamado elipsis, y es la manera en que __R__ pasa a través de los argumentos de una función sin tener que nombrarlos ni especificarlos.  

Sin embargo el método por default `S3` es `mean(x, trim = 0, na.rm = FALSE, ...)`, donde `trim` y `na.rm` tienen valores por defecto, lo cual los hace argumentos opcionales. Sin embargo cada uno tiene su función específica.

Por ejemplo:


```r
linkedin <- c(16, 9, 13, 5, 2, 17, 14)
facebook <- c(17, 7, 5, 16, 8, 13, 14)
# Promedio simple de la suma
avg_sum <- mean(linkedin + facebook)

# Promedio truncado de la suma 
avg_sum_trimmed <- mean((linkedin + facebook), trim = 0.2)

# Evaluando ambos promedios
print(avg_sum)
```

```
## [1] 22.28571
```

```r
print(avg_sum_trimmed)
```

```
## [1] 22.6
```


```r
linkedin <- c(16, 9, 13, 5, NA, 17, 14)
facebook <- c(17, NA, 5, 16, 8, 13, 14)

# Promedio simple de linkedin con argumentos por defecto
mean(linkedin)
```

```
## [1] NA
```

```r
# Promedio simple de linkedin con na.rm = TRUE
mean(linkedin, na.rm = TRUE)
```

```
## [1] 12.33333
```

- `median()` -> devuelve el valor de la mediana de los elementos evaluados.


```r
median(c(5,8,9,15,17,64,9,5,8,8,8,17,64,5))
```

```
## [1] 8.5
```

- `Moda` -> No hay una función que realice este cálculo directamento por lo tanto tenemos que recurrir a otras dos funciones. La moda nos representa el valor que tiene mayor frecuencia absoluta en una distribución de datos. Para realizar su cálculo utilizamos las funciones `sort()` para ordenar los datos y `table()` para ver el número de repeticiones de cada elemento.


```r
x <- c(5,8,9,15,17,64,9,5,8,8,8,17,64,5)
sort(x)
```

```
##  [1]  5  5  5  8  8  8  8  9  9 15 17 17 64 64
```

```r
table(x)
```

```
## x
##  5  8  9 15 17 64 
##  3  4  2  1  2  2
```

- `range()` -> es el intervalo entre el valor máximo y el valor mínimo. Permite obtener una idea de la dispersión de los datos, cuanto mayor es el rango, más dispersos están los datos de un conjunto. 


```r
x <- c(5,8,9,15,17,64,9,5,8,8,8,17,64,5)
range(x)
```

```
## [1]  5 64
```

- `quantile()` -> son los tres valores que dividen un conjunto de datos ordenados en cuatro partes porcentualmente iguales.


```r
quantile(x)
```

```
##   0%  25%  50%  75% 100% 
##  5.0  8.0  8.5 16.5 64.0
```

- `IQR()` -> la diferencia entre el tercer y el primer cuartil de una distribución. Es una medida de la dispersión estadística.


```r
IQR(x)
```

```
## [1] 8.5
```

- `boxplot()` -> proporcionan una visión general de la simetría de la distribución de los datos; si la mediana no está en el centro del rectángulo, la distribución no es simétrica. Permite ver como es la dispersión de los puntos con la mediana, los percentiles 25 y 75 y los valores máximos y mínimos. 

-- Son útiles para ver la presencia de valores atípicos también llamados outliers.

-- $Q_1 - 1.5 * IQR$

-- $Q_3 + 1.5 * IQR$


```r
boxplot(x, col = "orange", horizontal = TRUE)
```

![](Programacion-Cientifica-en-R_files/figure-html/unnamed-chunk-21-1.svg)<!-- -->

- `sd()` -> la desviación estandar es una medida del grado de dispersión de los datos con respecto al valor promedio. Se define como la raíz cuadrada de la varianza de la variable. 


```r
sd(x)
```

```
## [1] 20.20064
```

- `var()` -> es otra medida de dispersión y sirve para identificar a la media de las desviaciones cuadráticas de una variable de carácter aleatorio, considerando el valor medio de ésta.


```r
x <- c(5,8,9,15,17,64,9,5,8,8,8,17,64,5)
var(x)
```

```
## [1] 408.0659
```

- `summary()` -> permite calcular algunas medidas descriptivas elementales de todas las variables del fichero simultáneamente.


```r
summary(x)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##    5.00    8.00    8.50   17.29   16.50   64.00
```

```r
summary(cars)
```

```
##      speed           dist       
##  Min.   : 4.0   Min.   :  2.00  
##  1st Qu.:12.0   1st Qu.: 26.00  
##  Median :15.0   Median : 36.00  
##  Mean   :15.4   Mean   : 42.98  
##  3rd Qu.:19.0   3rd Qu.: 56.00  
##  Max.   :25.0   Max.   :120.00
```

- `apply()` -> permite realizar la misma operación en todas las filas y columnas de un arreglo simultáneamente. Sólo hay que indicarle la operación a realizar y el índice/índices sobre los cuales ha de realizarla.


```r
matriz <- matrix(1:4,nrow = 2,ncol = 2)
matriz
```

```
##      [,1] [,2]
## [1,]    1    3
## [2,]    2    4
```

```r
apply(matriz,1,sum)
```

```
## [1] 4 6
```

- `lapply()` -> funciona igual que la función `apply()`, con la diferencia de que puede ser utilizada en listas, dataframes o vectores y el retorna una lista.


```r
lapply(matriz,function (x) x^2)
```

```
## [[1]]
## [1] 1
## 
## [[2]]
## [1] 4
## 
## [[3]]
## [1] 9
## 
## [[4]]
## [1] 16
```

- `sapply()` -> funciona igual que la función `apply()`, con la diferencia de que puede ser utilizada en listas, dataframes o vectores y el retorna una vector.


```r
sapply(matriz,function(x) x^2)
```

```
## [1]  1  4  9 16
```

## __R__ como calculadora

### Operaciones Aritméticas

Estos pueden ser usado con variables de tipo numérico o complejo, pero también lógico; en el caso de lógicos son forzados a valores numéricos, como por ejemplo 0 y 1.

- Suma (`+`):


```r
3+4
```

```
## [1] 7
```

- Resta (`-`):


```r
1-6
```

```
## [1] -5
```

- Multiplicación (`*`):


```r
5*8
```

```
## [1] 40
```

- División (`/`):


```r
15/3
```

```
## [1] 5
```

- Raíz cuadrada:


```r
sqrt(25)
```

```
## [1] 5
```

- Potencia:


```r
5^2
```

```
## [1] 25
```

- División Entera:


```r
15%/%2
```

```
## [1] 7
```

- Módulo o resto de la división entera:


```r
15%%2
```

```
## [1] 1
```

- Logaritmos:

`log()` (Logaritmo nepereano), `logb()` (Logaritmo en base a b), `log10()` (Logaritmo en base a 10), `log2()` (Logaritmo en base a 2).


```r
log(0)
```

```
## [1] -Inf
```

```r
log(1)
```

```
## [1] 0
```

- Exponencial:

La función que trae __R__ para calcular la función exponencial es `exp()`


```r
exp(1)
```

```
## [1] 2.718282
```

- Funciones Trigonométricas

Seno `sin()`, coseno `cos()`, tangente `tan()`, arco-seno `asin()`, arco-coseno `acos()`, arcotangente `atan()` 


```r
sin(0)
```

```
## [1] 0
```

```r
cos(0)
```

```
## [1] 1
```

```r
tan(0)
```

```
## [1] 0
```

### Operadores Comparativos

Actuan sobre cualquier tipo de objeto, y retornan uno o varios valores lógicos, dependiendo del objeto. Estos usan todos los elementos de los dos objetos que se están comparando (reciclando los valores de los más pequeños si es necesario), devolviendo un objeto del mismo tamaño.
 
| Símbolo |      Operador     |
|:-------:|:-----------------:|
|    <    |     Menor que     |
|    >    |     Mayor que     |
|    <=   | Menor o igual que |
|    >=   | Mayor o igual que |
|    ==   |     Igual que     |
|    !=   |    Diferente de   |

### Operadores Lógicos
 
- __Y o en ingles AND__: `&`, `&&`.

Supongamos que tenemos dos operaciones lógicas a las que llamaremos `condición_1`,`condición_2` respectivamente, y queremos saber si estas se cumplen al mismo tiempo, en __R__ usamos `condición_1 & condición_2` o su equivalente `condición_1 && condición_2` y en este caso se estará evaluando si simultaneamente se cumplen las dos condiciones. En caso de que se cumplan la función retornará verdadero (`TRUE`).


```r
condicion_1 <- 20 > 10
condicion_2 <- 5/2 < 5
condicion_1 & condicion_2
```

```
## [1] TRUE
```

```r
condicion_1 && condicion_2 
```

```
## [1] TRUE
```

Es importante acotar que cuando se tengan vectores logical de más de un elemento se debe usar `&` para realizar la operación elemento a elemento. Si se estan comparando dos vectores, la comparación se hace elemento a elemento y si ambos no tienen el mismo tamaño se recurre al reciclaje de elemento para completar la comparación en el vector de menor tamaño, si en cambio colocamos `&&` simplemente realizará la comparación para los primeros elementos e ignorará el resto. 

Los símbolos `&&` generalmente debe usarse con el uso de condicionales como `if` o `while`.

- __O ó en ingles OR__: `|`, `||`

Al igual que el caso anterior supongamos que tenemos dos operaciones lógicas y queremos saber si se cumple una de las dos, entonces podemos plantearnos una expresión de este tipo, la manera de hacerlo en __R__ es la diguiente `condición_1 || condición_2`, si una de las dos se cumple ésta retornará verdadero (`TRUE`), también lo hará si ambas se cumple.


```r
condicion_1 <- 3 > 2 
condicion_2 <- 4/5 < 7/8

condicion_1 | condicion_2
```

```
## [1] TRUE
```

```r
condicion_1 || condicion_2
```

```
## [1] TRUE
```

Cuando usamos vectores para hacer este tipo de comparaciones se sigue con `|` y `||` el mismo criterio que con `&` y `&&`.



<!--chapter:end:002-Objetos-en-R.Rmd-->


# Vectores

Placeholder


## Definición
## Creación de Vectores
## Secuencias
## Selección de elementos de un vector
## Suma de Vectores

<!--chapter:end:003-Vectores.Rmd-->


# Matrices

Placeholder


## Definición
## Creación de Matrices
## Selección de los elementos de una matriz
## Operaciones con Matrices

<!--chapter:end:004-Matrices.Rmd-->


# Data.frame

Placeholder


## Generación de un Data.frame
## Acceder a Datos en un Data.frame

<!--chapter:end:005-Dataframe.Rmd-->


# Listas

Placeholder



<!--chapter:end:006-Listas-y-Factores.Rmd-->


# Fechas y Tiempo

Placeholder


## Fechas con formato `Date`
## Fechas con el formato `POSIXct` o `POSIXlt`

<!--chapter:end:007-Fechas-tiempo.Rmd-->

# Datos

## Importar Datos

## Datos de __R__

## Guardar Datos

## Exportar Datos




<!--chapter:end:008-Datos.Rmd-->


# Gráficos

Placeholder


## Gráfico de Puntos
## Gráfico de líneas
## Gráfico de Tortas
## Barplot
## Boxplot
## Histogramas
## Multiple gráficos por ventanas
## Guardar gráficos

<!--chapter:end:009-Graficos.Rmd-->


# Funciones

Placeholder


## Creación de Funciones
## Condicionales
## Loop o Bucles

<!--chapter:end:010-Funciones.Rmd-->


# (APPENDIX) Apéndice {-}

Placeholder

# Software Tools

Placeholder


## R and R packages
## Pandoc
## LaTeX

<!--chapter:end:400-apendice.Rmd-->

# Referencias {-}




<!--chapter:end:500-references.Rmd-->

