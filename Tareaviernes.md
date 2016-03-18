# Actividad tarea.
Eduardo Castro T.  
March 18, 2016  

##Introducción##

Hoy en día por medio de algunos dispositivos es posible monitorear la actividad diaria de una persona. En esta actividad se presentan los datos generados por uno de estos dispositivos, el cual recabó información durante los meses de Octubre y Noviembre del año 2012. El dispositivo capturó información diaria sobre el número de pasos que una persona camina por día.

##Análisis de datos##

Como primer paso es necesario descargar el archivo que contiene los datos desde el siguiente [Enlace](https://d396qusza40orc.cloudfront.net/repdata%2Fdata%2Factivity.zip).  

Posteriormente debemos cargar los datos en el ambiente de RStudio.


```r
pasos=read.csv("activity.csv")
```

Obtenemos las medias por día en un vector denominado como "medias".


```r
medias = c(apply(pasos[0:288,1,drop=F],2,mean),apply(pasos[289:576,1,drop=F],2,mean),apply(pasos[577:864,1,drop=F],2,mean),apply(pasos[865:1152,1,drop=F],2,mean),apply(pasos[1153:1440,1,drop=F],2,mean),apply(pasos[1441:1728,1,drop=F],2,mean),apply(pasos[1729:2016,1,drop=F],2,mean),apply(pasos[2017:2304,1,drop=F],2,mean),apply(pasos[2305:2592,1,drop=F],2,mean),apply(pasos[2593:2880,1,drop=F],2,mean),apply(pasos[2881:3168,1,drop=F],2,mean),apply(pasos[3169:3456,1,drop=F],2,mean),apply(pasos[3457:3744,1,drop=F],2,mean),apply(pasos[3745:4032,1,drop=F],2,mean),apply(pasos[4033:4320,1,drop=F],2,mean),apply(pasos[4321:4608,1,drop=F],2,mean),apply(pasos[4609:4896,1,drop=F],2,mean),apply(pasos[4897:5184,1,drop=F],2,mean),apply(pasos[5185:5472,1,drop=F],2,mean),apply(pasos[5473:5760,1,drop=F],2,mean),apply(pasos[5761:6048,1,drop=F],2,mean),apply(pasos[6049:6336,1,drop=F],2,mean),apply(pasos[6337:6624,1,drop=F],2,mean),apply(pasos[6625:6912,1,drop=F],2,mean),apply(pasos[6913:7200,1,drop=F],2,mean),apply(pasos[7201:7488,1,drop=F],2,mean),apply(pasos[7489:7776,1,drop=F],2,mean),apply(pasos[7777:8064,1,drop=F],2,mean),apply(pasos[8065:8352,1,drop=F],2,mean),apply(pasos[8353:8640,1,drop=F],2,mean),apply(pasos[8641:8928,1,drop=F],2,mean),apply(pasos[8929:9216,1,drop=F],2,mean),apply(pasos[9217:9504,1,drop=F],2,mean),apply(pasos[9505:9792,1,drop=F],2,mean),apply(pasos[9793:10080,1,drop=F],2,mean),apply(pasos[10081:10368,1,drop=F],2,mean),apply(pasos[10369:10656,1,drop=F],2,mean),apply(pasos[10657:10944,1,drop=F],2,mean),apply(pasos[10945:11232,1,drop=F],2,mean),apply(pasos[11233:11520,1,drop=F],2,mean),apply(pasos[11521:11808,1,drop=F],2,mean),apply(pasos[11809:12096,1,drop=F],2,mean),apply(pasos[12097:12384,1,drop=F],2,mean),apply(pasos[12385:12672,1,drop=F],2,mean),apply(pasos[12673:12960,1,drop=F],2,mean),apply(pasos[12961:13248,1,drop=F],2,mean),apply(pasos[13249:13536,1,drop=F],2,mean),apply(pasos[13537:13824,1,drop=F],2,mean),apply(pasos[13825:14112,1,drop=F],2,mean),apply(pasos[14113:14400,1,drop=F],2,mean),apply(pasos[14401:14688,1,drop=F],2,mean),apply(pasos[14689:14976,1,drop=F],2,mean),apply(pasos[14977:15264,1,drop=F],2,mean),apply(pasos[15265:15552,1,drop=F],2,mean),apply(pasos[15553:15840,1,drop=F],2,mean),apply(pasos[15841:16128,1,drop=F],2,mean),apply(pasos[16129:16416,1,drop=F],2,mean),apply(pasos[16417:16704,1,drop=F],2,mean),apply(pasos[16705:16992,1,drop=F],2,mean),apply(pasos[16993:17280,1,drop=F],2,mean),apply(pasos[17281:17568,1,drop=F],2,mean))

number=c(1:61)
names(medias)=number
medias
```

```
##          1          2          3          4          5          6 
##         NA  0.4375000 39.4166667 42.0694444 46.1597222 53.5416667 
##          7          8          9         10         11         12 
## 38.2465278         NA 44.4826389 34.3750000 35.7777778 60.3541667 
##         13         14         15         16         17         18 
## 43.1458333 52.4236111 35.2048611 52.3750000 46.7083333 34.9166667 
##         19         20         21         22         23         24 
## 41.0729167 36.0937500 30.6284722 46.7361111 30.9652778 29.0104167 
##         25         26         27         28         29         30 
##  8.6527778 23.5347222 35.1354167 39.7847222 17.4236111 34.0937500 
##         31         32         33         34         35         36 
## 53.5208333         NA 36.8055556 36.7048611         NA 36.2465278 
##         37         38         39         40         41         42 
## 28.9375000 44.7326389 11.1770833         NA         NA 43.7777778 
##         43         44         45         46         47         48 
## 37.3784722 25.4722222         NA  0.1423611 18.8923611 49.7881944 
##         49         50         51         52         53         54 
## 52.4652778 30.6979167 15.5277778 44.3993056 70.9270833 73.5902778 
##         55         56         57         58         59         60 
## 50.2708333 41.0902778 38.7569444 47.3819444 35.3576389 24.4687500 
##         61 
##         NA
```

Y hacemos lo mismo para el caso de las medianas.


```r
medianas = c(apply(pasos[0:288,1,drop=F],2,median),apply(pasos[289:576,1,drop=F],2,median),apply(pasos[577:864,1,drop=F],2,median),apply(pasos[865:1152,1,drop=F],2,median),apply(pasos[1153:1440,1,drop=F],2,median),apply(pasos[1441:1728,1,drop=F],2,median),apply(pasos[1729:2016,1,drop=F],2,median),apply(pasos[2017:2304,1,drop=F],2,median),apply(pasos[2305:2592,1,drop=F],2,median),apply(pasos[2593:2880,1,drop=F],2,median),apply(pasos[2881:3168,1,drop=F],2,median),apply(pasos[3169:3456,1,drop=F],2,median),apply(pasos[3457:3744,1,drop=F],2,median),apply(pasos[3745:4032,1,drop=F],2,median),apply(pasos[4033:4320,1,drop=F],2,median),apply(pasos[4321:4608,1,drop=F],2,median),apply(pasos[4609:4896,1,drop=F],2,median),apply(pasos[4897:5184,1,drop=F],2,median),apply(pasos[5185:5472,1,drop=F],2,median),apply(pasos[5473:5760,1,drop=F],2,median),apply(pasos[5761:6048,1,drop=F],2,median),apply(pasos[6049:6336,1,drop=F],2,median),apply(pasos[6337:6624,1,drop=F],2,median),apply(pasos[6625:6912,1,drop=F],2,median),apply(pasos[6913:7200,1,drop=F],2,median),apply(pasos[7201:7488,1,drop=F],2,median),apply(pasos[7489:7776,1,drop=F],2,median),apply(pasos[7777:8064,1,drop=F],2,median),apply(pasos[8065:8352,1,drop=F],2,median),apply(pasos[8353:8640,1,drop=F],2,median),apply(pasos[8641:8928,1,drop=F],2,median),apply(pasos[8929:9216,1,drop=F],2,median),apply(pasos[9217:9504,1,drop=F],2,median),apply(pasos[9505:9792,1,drop=F],2,median),apply(pasos[9793:10080,1,drop=F],2,median),apply(pasos[10081:10368,1,drop=F],2,median),apply(pasos[10369:10656,1,drop=F],2,median),apply(pasos[10657:10944,1,drop=F],2,median),apply(pasos[10945:11232,1,drop=F],2,median),apply(pasos[11233:11520,1,drop=F],2,median),apply(pasos[11521:11808,1,drop=F],2,median),apply(pasos[11809:12096,1,drop=F],2,median),apply(pasos[12097:12384,1,drop=F],2,median),apply(pasos[12385:12672,1,drop=F],2,median),apply(pasos[12673:12960,1,drop=F],2,median),apply(pasos[12961:13248,1,drop=F],2,median),apply(pasos[13249:13536,1,drop=F],2,median),apply(pasos[13537:13824,1,drop=F],2,median),apply(pasos[13825:14112,1,drop=F],2,median),apply(pasos[14113:14400,1,drop=F],2,median),apply(pasos[14401:14688,1,drop=F],2,median),apply(pasos[14689:14976,1,drop=F],2,median),apply(pasos[14977:15264,1,drop=F],2,median),apply(pasos[15265:15552,1,drop=F],2,median),apply(pasos[15553:15840,1,drop=F],2,median),apply(pasos[15841:16128,1,drop=F],2,median),apply(pasos[16129:16416,1,drop=F],2,median),apply(pasos[16417:16704,1,drop=F],2,median),apply(pasos[16705:16992,1,drop=F],2,median),apply(pasos[16993:17280,1,drop=F],2,median),apply(pasos[17281:17568,1,drop=F],2,median))

number=c(1:61)
names(medianas)=number
medianas
```

```
##  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 
## NA  0  0  0  0  0  0 NA  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0 
## 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 46 47 48 49 50 
##  0  0  0  0  0  0 NA  0  0 NA  0  0  0  0 NA NA  0  0  0 NA  0  0  0  0  0 
## 51 52 53 54 55 56 57 58 59 60 61 
##  0  0  0  0  0  0  0  0  0  0 NA
```


Para analizar los patrones de actividad por día podemos insertar una grafica que nos muestre la media de pasos de cada uno de los días.


```r
number=c(1:61)
names(medias)=number
barplot(medias, xlab="día", ylab="pasos", main="comparación de pasos promedio por día")
```

![](Tareaviernes_files/figure-html/unnamed-chunk-4-1.png)


Ahora para comparar los valores de actividad en los fines de semana contra el resto de días hacemos lo siguiente:

Primero graficamos el valor de las medias de actividad para los dias que no son fin de semana. 


```r
barplot(medias[c(1,2,3,4,5,8,9,10,11,12,15,16,17,18,19,22,23,24,25,26,29,30,31,32,33,36,37,38,39,40,43,44,45,46,47,50,51,52,53,54,57,58,59,60,61)], xlab="dia", ylab="pasos", main="pasos por día que no son fin de semana") 
```

![](Tareaviernes_files/figure-html/unnamed-chunk-5-1.png)

y lo comparamos contra la grafica de los dias de fin de semana:



```r
barplot(medias[c(6,7,13,14,20,21,27,28,34,35,41,42,48,49,55,56)], xlab="día", ylab="pasos", main="pasos por día de fin de semana")
```

![](Tareaviernes_files/figure-html/unnamed-chunk-6-1.png)



Para el caso de los valores no asignados (NA), dado que no se observa una tendencia clara o definida para establecer un criterio de sustitución de los valores NA, los remplazaremos por el valor 0.


```r
pasos[is.na(pasos)]=0
```

Y ahora repetiremos los pasos anteriores con dicha modificación. 

primero calculamos las medias por día:

```r
medias = c(apply(pasos[0:288,1,drop=F],2,mean),apply(pasos[289:576,1,drop=F],2,mean),apply(pasos[577:864,1,drop=F],2,mean),apply(pasos[865:1152,1,drop=F],2,mean),apply(pasos[1153:1440,1,drop=F],2,mean),apply(pasos[1441:1728,1,drop=F],2,mean),apply(pasos[1729:2016,1,drop=F],2,mean),apply(pasos[2017:2304,1,drop=F],2,mean),apply(pasos[2305:2592,1,drop=F],2,mean),apply(pasos[2593:2880,1,drop=F],2,mean),apply(pasos[2881:3168,1,drop=F],2,mean),apply(pasos[3169:3456,1,drop=F],2,mean),apply(pasos[3457:3744,1,drop=F],2,mean),apply(pasos[3745:4032,1,drop=F],2,mean),apply(pasos[4033:4320,1,drop=F],2,mean),apply(pasos[4321:4608,1,drop=F],2,mean),apply(pasos[4609:4896,1,drop=F],2,mean),apply(pasos[4897:5184,1,drop=F],2,mean),apply(pasos[5185:5472,1,drop=F],2,mean),apply(pasos[5473:5760,1,drop=F],2,mean),apply(pasos[5761:6048,1,drop=F],2,mean),apply(pasos[6049:6336,1,drop=F],2,mean),apply(pasos[6337:6624,1,drop=F],2,mean),apply(pasos[6625:6912,1,drop=F],2,mean),apply(pasos[6913:7200,1,drop=F],2,mean),apply(pasos[7201:7488,1,drop=F],2,mean),apply(pasos[7489:7776,1,drop=F],2,mean),apply(pasos[7777:8064,1,drop=F],2,mean),apply(pasos[8065:8352,1,drop=F],2,mean),apply(pasos[8353:8640,1,drop=F],2,mean),apply(pasos[8641:8928,1,drop=F],2,mean),apply(pasos[8929:9216,1,drop=F],2,mean),apply(pasos[9217:9504,1,drop=F],2,mean),apply(pasos[9505:9792,1,drop=F],2,mean),apply(pasos[9793:10080,1,drop=F],2,mean),apply(pasos[10081:10368,1,drop=F],2,mean),apply(pasos[10369:10656,1,drop=F],2,mean),apply(pasos[10657:10944,1,drop=F],2,mean),apply(pasos[10945:11232,1,drop=F],2,mean),apply(pasos[11233:11520,1,drop=F],2,mean),apply(pasos[11521:11808,1,drop=F],2,mean),apply(pasos[11809:12096,1,drop=F],2,mean),apply(pasos[12097:12384,1,drop=F],2,mean),apply(pasos[12385:12672,1,drop=F],2,mean),apply(pasos[12673:12960,1,drop=F],2,mean),apply(pasos[12961:13248,1,drop=F],2,mean),apply(pasos[13249:13536,1,drop=F],2,mean),apply(pasos[13537:13824,1,drop=F],2,mean),apply(pasos[13825:14112,1,drop=F],2,mean),apply(pasos[14113:14400,1,drop=F],2,mean),apply(pasos[14401:14688,1,drop=F],2,mean),apply(pasos[14689:14976,1,drop=F],2,mean),apply(pasos[14977:15264,1,drop=F],2,mean),apply(pasos[15265:15552,1,drop=F],2,mean),apply(pasos[15553:15840,1,drop=F],2,mean),apply(pasos[15841:16128,1,drop=F],2,mean),apply(pasos[16129:16416,1,drop=F],2,mean),apply(pasos[16417:16704,1,drop=F],2,mean),apply(pasos[16705:16992,1,drop=F],2,mean),apply(pasos[16993:17280,1,drop=F],2,mean),apply(pasos[17281:17568,1,drop=F],2,mean))


number=c(1:61)
names(medias)=number
medias
```

```
##          1          2          3          4          5          6 
##  0.0000000  0.4375000 39.4166667 42.0694444 46.1597222 53.5416667 
##          7          8          9         10         11         12 
## 38.2465278  0.0000000 44.4826389 34.3750000 35.7777778 60.3541667 
##         13         14         15         16         17         18 
## 43.1458333 52.4236111 35.2048611 52.3750000 46.7083333 34.9166667 
##         19         20         21         22         23         24 
## 41.0729167 36.0937500 30.6284722 46.7361111 30.9652778 29.0104167 
##         25         26         27         28         29         30 
##  8.6527778 23.5347222 35.1354167 39.7847222 17.4236111 34.0937500 
##         31         32         33         34         35         36 
## 53.5208333  0.0000000 36.8055556 36.7048611  0.0000000 36.2465278 
##         37         38         39         40         41         42 
## 28.9375000 44.7326389 11.1770833  0.0000000  0.0000000 43.7777778 
##         43         44         45         46         47         48 
## 37.3784722 25.4722222  0.0000000  0.1423611 18.8923611 49.7881944 
##         49         50         51         52         53         54 
## 52.4652778 30.6979167 15.5277778 44.3993056 70.9270833 73.5902778 
##         55         56         57         58         59         60 
## 50.2708333 41.0902778 38.7569444 47.3819444 35.3576389 24.4687500 
##         61 
##  0.0000000
```

despues las medianas.


```r
medianas = c(apply(pasos[0:288,1,drop=F],2,median),apply(pasos[289:576,1,drop=F],2,median),apply(pasos[577:864,1,drop=F],2,median),apply(pasos[865:1152,1,drop=F],2,median),apply(pasos[1153:1440,1,drop=F],2,median),apply(pasos[1441:1728,1,drop=F],2,median),apply(pasos[1729:2016,1,drop=F],2,median),apply(pasos[2017:2304,1,drop=F],2,median),apply(pasos[2305:2592,1,drop=F],2,median),apply(pasos[2593:2880,1,drop=F],2,median),apply(pasos[2881:3168,1,drop=F],2,median),apply(pasos[3169:3456,1,drop=F],2,median),apply(pasos[3457:3744,1,drop=F],2,median),apply(pasos[3745:4032,1,drop=F],2,median),apply(pasos[4033:4320,1,drop=F],2,median),apply(pasos[4321:4608,1,drop=F],2,median),apply(pasos[4609:4896,1,drop=F],2,median),apply(pasos[4897:5184,1,drop=F],2,median),apply(pasos[5185:5472,1,drop=F],2,median),apply(pasos[5473:5760,1,drop=F],2,median),apply(pasos[5761:6048,1,drop=F],2,median),apply(pasos[6049:6336,1,drop=F],2,median),apply(pasos[6337:6624,1,drop=F],2,median),apply(pasos[6625:6912,1,drop=F],2,median),apply(pasos[6913:7200,1,drop=F],2,median),apply(pasos[7201:7488,1,drop=F],2,median),apply(pasos[7489:7776,1,drop=F],2,median),apply(pasos[7777:8064,1,drop=F],2,median),apply(pasos[8065:8352,1,drop=F],2,median),apply(pasos[8353:8640,1,drop=F],2,median),apply(pasos[8641:8928,1,drop=F],2,median),apply(pasos[8929:9216,1,drop=F],2,median),apply(pasos[9217:9504,1,drop=F],2,median),apply(pasos[9505:9792,1,drop=F],2,median),apply(pasos[9793:10080,1,drop=F],2,median),apply(pasos[10081:10368,1,drop=F],2,median),apply(pasos[10369:10656,1,drop=F],2,median),apply(pasos[10657:10944,1,drop=F],2,median),apply(pasos[10945:11232,1,drop=F],2,median),apply(pasos[11233:11520,1,drop=F],2,median),apply(pasos[11521:11808,1,drop=F],2,median),apply(pasos[11809:12096,1,drop=F],2,median),apply(pasos[12097:12384,1,drop=F],2,median),apply(pasos[12385:12672,1,drop=F],2,median),apply(pasos[12673:12960,1,drop=F],2,median),apply(pasos[12961:13248,1,drop=F],2,median),apply(pasos[13249:13536,1,drop=F],2,median),apply(pasos[13537:13824,1,drop=F],2,median),apply(pasos[13825:14112,1,drop=F],2,median),apply(pasos[14113:14400,1,drop=F],2,median),apply(pasos[14401:14688,1,drop=F],2,median),apply(pasos[14689:14976,1,drop=F],2,median),apply(pasos[14977:15264,1,drop=F],2,median),apply(pasos[15265:15552,1,drop=F],2,median),apply(pasos[15553:15840,1,drop=F],2,median),apply(pasos[15841:16128,1,drop=F],2,median),apply(pasos[16129:16416,1,drop=F],2,median),apply(pasos[16417:16704,1,drop=F],2,median),apply(pasos[16705:16992,1,drop=F],2,median),apply(pasos[16993:17280,1,drop=F],2,median),apply(pasos[17281:17568,1,drop=F],2,median))

number=c(1:61)
names(medianas)=number
medianas
```

```
##  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 
##  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0 
## 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 46 47 48 49 50 
##  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0 
## 51 52 53 54 55 56 57 58 59 60 61 
##  0  0  0  0  0  0  0  0  0  0  0
```

y por último una grafica comparatoria de actividad diaria.


```r
number=c(1:61)
names(medias)=number
barplot(medias, xlab="día", ylab="pasos", main="comparación de pasos promedio por día")
```

![](Tareaviernes_files/figure-html/unnamed-chunk-10-1.png)


##Discusión##

Respecto al analisis de actividad por dia, se logra observar una tendencia de mayor actividad cerca de la mitad del dia y a las 3/4 partes. 

En la comparacion de graficas entre los fines de semana y el resto de dias podemos observar un ligero aumento de actividad los fines de semana, pasando de 40 la mayoria de las observaciones en comparacion al resto de dias que no son fin de semana, en donde se pueden observar muchas observaciones por debajo de este valor. 

Sin embargo podríamos incluir una comparación de los valores medios de pasos caminados entre los fines de semana y el resto de dias. 


```r
mediaS = mean(medias[c(1,2,3,4,5,8,9,10,11,12,15,16,17,18,19,22,23,24,25,26,29,30,31,32,33,36,37,38,39,40,43,44,45,46,47,50,51,52,53,54,57,58,59,60,61)])
mediaFS=mean(medias[c(6,7,13,14,20,21,27,28,34,35,41,42,48,49,55,56)])
```

Media de pasos diarios entre semana:


```r
mediaS
```

```
## [1] 30.62623
```

Media de pasos en fin de semana


```r
mediaFS
```

```
## [1] 37.69358
```

Con lo que podemos observar que se presenta una mayor actividad los fines de semana en comparación al resto de los días.

En el caso de los valores de las medianas vemos que los valores son cero, lo cual significa que los valores intermedios de las observaciones (12:00 p.m.) corresponden a periodos de inactividad debidas a la actividad diaria (clases, trabajo, descanso).

##Conclusión##

En algunos grupos de datos es posible observar ciertas tendencias en la actividad diaria (pasos), sin embargo de una forma global no se puede definir o establecer una tendencia de dicha actividad, es necesario revisar otro tipo de información ( empleo, pasatiempos, actividades academicas, etc) para atribuir las tendencias a alguna de estas actividades. 


