
title: "Actividad tarea."
author: "Eduardo Castro T."
date: "March 14, 2016"
output: html_document
---

#IntroducciÃ³n#

Hoy en dÃ???a por medio de algunos dispositivos es posible monitorear la actividad diaria de una persona. En esta actividad se presentan los datos generados por uno de estos dispositivos, el cual recabÃ³ informaciÃ³n durante los meses de Octubre y Noviembre del aÃ±o 2012. El dispositivo capturÃ³ informaciÃ³n diaria sobre el nÃºmero de pasos que una persona camina en intervalos de 5 minutos.

1.- Como primer paso es necesario descargar el archivo que contiene los datos desde el siguiente [Enlace](https://d396qusza40orc.cloudfront.net/repdata%2Fdata%2Factivity.zip).  

2.- Posteriormente debemos cargar los datos en el ambiente de RStudio.

```{r, echo=TRUE}

pasos=read.csv("/Users/Usuario/Documents/activity.csv")
```

3.- Obtenemos las medias por día en un vector denominado como "medias".

```{r}
medias = c(apply(pasos[0:288,1,drop=F],2,mean),apply(pasos[289:576,1,drop=F],2,mean),apply(pasos[577:864,1,drop=F],2,mean),apply(pasos[865:1152,1,drop=F],2,mean),apply(pasos[1153:1440,1,drop=F],2,mean),apply(pasos[1441:1728,1,drop=F],2,mean),apply(pasos[1729:2016,1,drop=F],2,mean),apply(pasos[2017:2304,1,drop=F],2,mean),apply(pasos[2305:2592,1,drop=F],2,mean),apply(pasos[2593:2880,1,drop=F],2,mean),apply(pasos[2881:3168,1,drop=F],2,mean),apply(pasos[3169:3456,1,drop=F],2,mean),apply(pasos[3457:3744,1,drop=F],2,mean),apply(pasos[3745:4032,1,drop=F],2,mean),apply(pasos[4033:4320,1,drop=F],2,mean),apply(pasos[4321:4608,1,drop=F],2,mean),apply(pasos[4609:4896,1,drop=F],2,mean),apply(pasos[4897:5184,1,drop=F],2,mean),apply(pasos[5185:5472,1,drop=F],2,mean),apply(pasos[5473:5760,1,drop=F],2,mean),apply(pasos[5761:6048,1,drop=F],2,mean),apply(pasos[6049:6336,1,drop=F],2,mean),apply(pasos[6337:6624,1,drop=F],2,mean),apply(pasos[6625:6912,1,drop=F],2,mean),apply(pasos[6913:7200,1,drop=F],2,mean),apply(pasos[7201:7488,1,drop=F],2,mean),apply(pasos[7489:7776,1,drop=F],2,mean),apply(pasos[7777:8064,1,drop=F],2,mean),apply(pasos[8065:8352,1,drop=F],2,mean),apply(pasos[8353:8640,1,drop=F],2,mean),apply(pasos[8641:8928,1,drop=F],2,mean),apply(pasos[8929:9216,1,drop=F],2,mean),apply(pasos[9217:9504,1,drop=F],2,mean),apply(pasos[9505:9792,1,drop=F],2,mean),apply(pasos[9793:10080,1,drop=F],2,mean),apply(pasos[10081:10368,1,drop=F],2,mean),apply(pasos[10369:10656,1,drop=F],2,mean),apply(pasos[10657:10944,1,drop=F],2,mean),apply(pasos[10945:11232,1,drop=F],2,mean),apply(pasos[11233:11520,1,drop=F],2,mean),apply(pasos[11521:11808,1,drop=F],2,mean),apply(pasos[11809:12096,1,drop=F],2,mean),apply(pasos[12097:12384,1,drop=F],2,mean),apply(pasos[12385:12672,1,drop=F],2,mean),apply(pasos[12673:12960,1,drop=F],2,mean),apply(pasos[12961:13248,1,drop=F],2,mean),apply(pasos[13249:13536,1,drop=F],2,mean),apply(pasos[13537:13824,1,drop=F],2,mean),apply(pasos[13825:14112,1,drop=F],2,mean),apply(pasos[14113:14400,1,drop=F],2,mean),apply(pasos[14401:14688,1,drop=F],2,mean),apply(pasos[14689:14976,1,drop=F],2,mean),apply(pasos[14977:15264,1,drop=F],2,mean),apply(pasos[15265:15552,1,drop=F],2,mean),apply(pasos[15553:15840,1,drop=F],2,mean),apply(pasos[15841:16128,1,drop=F],2,mean),apply(pasos[16129:16416,1,drop=F],2,mean),apply(pasos[16417:16704,1,drop=F],2,mean),apply(pasos[16705:16992,1,drop=F],2,mean),apply(pasos[16993:17280,1,drop=F],2,mean),apply(pasos[17281:17568,1,drop=F],2,mean))

number=c(1:60)
names(medias)=number
medias

```

4.- Y hacemos lo mismo para el caso de las medianas.

```{r}
medianas = c(apply(pasos[0:288,1,drop=F],2,median),apply(pasos[289:576,1,drop=F],2,median),apply(pasos[577:864,1,drop=F],2,median),apply(pasos[865:1152,1,drop=F],2,median),apply(pasos[1153:1440,1,drop=F],2,median),apply(pasos[1441:1728,1,drop=F],2,median),apply(pasos[1729:2016,1,drop=F],2,median),apply(pasos[2017:2304,1,drop=F],2,median),apply(pasos[2305:2592,1,drop=F],2,median),apply(pasos[2593:2880,1,drop=F],2,median),apply(pasos[2881:3168,1,drop=F],2,median),apply(pasos[3169:3456,1,drop=F],2,median),apply(pasos[3457:3744,1,drop=F],2,median),apply(pasos[3745:4032,1,drop=F],2,median),apply(pasos[4033:4320,1,drop=F],2,median),apply(pasos[4321:4608,1,drop=F],2,median),apply(pasos[4609:4896,1,drop=F],2,median),apply(pasos[4897:5184,1,drop=F],2,median),apply(pasos[5185:5472,1,drop=F],2,median),apply(pasos[5473:5760,1,drop=F],2,median),apply(pasos[5761:6048,1,drop=F],2,median),apply(pasos[6049:6336,1,drop=F],2,median),apply(pasos[6337:6624,1,drop=F],2,median),apply(pasos[6625:6912,1,drop=F],2,median),apply(pasos[6913:7200,1,drop=F],2,median),apply(pasos[7201:7488,1,drop=F],2,median),apply(pasos[7489:7776,1,drop=F],2,median),apply(pasos[7777:8064,1,drop=F],2,median),apply(pasos[8065:8352,1,drop=F],2,median),apply(pasos[8353:8640,1,drop=F],2,median),apply(pasos[8641:8928,1,drop=F],2,median),apply(pasos[8929:9216,1,drop=F],2,median),apply(pasos[9217:9504,1,drop=F],2,median),apply(pasos[9505:9792,1,drop=F],2,median),apply(pasos[9793:10080,1,drop=F],2,median),apply(pasos[10081:10368,1,drop=F],2,median),apply(pasos[10369:10656,1,drop=F],2,median),apply(pasos[10657:10944,1,drop=F],2,median),apply(pasos[10945:11232,1,drop=F],2,median),apply(pasos[11233:11520,1,drop=F],2,median),apply(pasos[11521:11808,1,drop=F],2,median),apply(pasos[11809:12096,1,drop=F],2,median),apply(pasos[12097:12384,1,drop=F],2,median),apply(pasos[12385:12672,1,drop=F],2,median),apply(pasos[12673:12960,1,drop=F],2,median),apply(pasos[12961:13248,1,drop=F],2,median),apply(pasos[13249:13536,1,drop=F],2,median),apply(pasos[13537:13824,1,drop=F],2,median),apply(pasos[13825:14112,1,drop=F],2,median),apply(pasos[14113:14400,1,drop=F],2,median),apply(pasos[14401:14688,1,drop=F],2,median),apply(pasos[14689:14976,1,drop=F],2,median),apply(pasos[14977:15264,1,drop=F],2,median),apply(pasos[15265:15552,1,drop=F],2,median),apply(pasos[15553:15840,1,drop=F],2,median),apply(pasos[15841:16128,1,drop=F],2,median),apply(pasos[16129:16416,1,drop=F],2,median),apply(pasos[16417:16704,1,drop=F],2,median),apply(pasos[16705:16992,1,drop=F],2,median),apply(pasos[16993:17280,1,drop=F],2,median),apply(pasos[17281:17568,1,drop=F],2,median))

number=c(1:60)
names(medianas)=number
medianas
```




Para analizar los patrones de actividad diaria podemos construir una gráfica que nos muestre la cantidad de pasos por día del año en los diferentes periodos de tiempo. 


```{r}
 plot(x=pasos$yday, y=pasos[,1], xlab="día del año", ylab="número de pasos", main="Pasos por día")

```


o como alternativa podemos graficar las medias de cada uno de los día. 

```{r}
number=c(1:60)
names(medias)=number
barplot(medias, xlab="día", ylab="pasos", main="comparación de pasos promedio por día")
```


Ahora para comparar los valores de actividad en los fines de semana contra el resto de días hacemos lo siguientes. 
Primero graficamos el valor de las medias de actividad para los dias que no son fin de semana. 

```{r}
barplot(medias[c(1,2,3,4,5,8,9,10,11,12,15,16,17,18,19,22,23,24,25,26,29,30,31,32,33,36,37,38,39,40,43,44,45,46,47,50,51,52,53,54,57,58,59,60,61)], xlab="día", ylab="pasos", main="pasos por día que no son fin de semana" )
```

y lo comparamos contra la grafica de los dias de fin de semana:


```{r}
barplot(medias[c(6,7,13,14,20,21,27,28,34,35,41,42,48,49,55,56)], xlab="día", ylab="pasos", main="pasos por día de fin de semana")
```


Ahora para remplazar los valores no asignados (NA), dado que no se observa una tendencia como para establecer un criterio de sustitución de los valores NA, los remplazaremos por el valor 0.

```{r}

pasos[is.na(pasos)]=0
```

Y ahora repetiremos los pasos anteriores con dicha modificación. 

primero calculamos las medianas por día:
```{r}
medias = c(apply(pasos[0:288,1,drop=F],2,mean),apply(pasos[289:576,1,drop=F],2,mean),apply(pasos[577:864,1,drop=F],2,mean),apply(pasos[865:1152,1,drop=F],2,mean),apply(pasos[1153:1440,1,drop=F],2,mean),apply(pasos[1441:1728,1,drop=F],2,mean),apply(pasos[1729:2016,1,drop=F],2,mean),apply(pasos[2017:2304,1,drop=F],2,mean),apply(pasos[2305:2592,1,drop=F],2,mean),apply(pasos[2593:2880,1,drop=F],2,mean),apply(pasos[2881:3168,1,drop=F],2,mean),apply(pasos[3169:3456,1,drop=F],2,mean),apply(pasos[3457:3744,1,drop=F],2,mean),apply(pasos[3745:4032,1,drop=F],2,mean),apply(pasos[4033:4320,1,drop=F],2,mean),apply(pasos[4321:4608,1,drop=F],2,mean),apply(pasos[4609:4896,1,drop=F],2,mean),apply(pasos[4897:5184,1,drop=F],2,mean),apply(pasos[5185:5472,1,drop=F],2,mean),apply(pasos[5473:5760,1,drop=F],2,mean),apply(pasos[5761:6048,1,drop=F],2,mean),apply(pasos[6049:6336,1,drop=F],2,mean),apply(pasos[6337:6624,1,drop=F],2,mean),apply(pasos[6625:6912,1,drop=F],2,mean),apply(pasos[6913:7200,1,drop=F],2,mean),apply(pasos[7201:7488,1,drop=F],2,mean),apply(pasos[7489:7776,1,drop=F],2,mean),apply(pasos[7777:8064,1,drop=F],2,mean),apply(pasos[8065:8352,1,drop=F],2,mean),apply(pasos[8353:8640,1,drop=F],2,mean),apply(pasos[8641:8928,1,drop=F],2,mean),apply(pasos[8929:9216,1,drop=F],2,mean),apply(pasos[9217:9504,1,drop=F],2,mean),apply(pasos[9505:9792,1,drop=F],2,mean),apply(pasos[9793:10080,1,drop=F],2,mean),apply(pasos[10081:10368,1,drop=F],2,mean),apply(pasos[10369:10656,1,drop=F],2,mean),apply(pasos[10657:10944,1,drop=F],2,mean),apply(pasos[10945:11232,1,drop=F],2,mean),apply(pasos[11233:11520,1,drop=F],2,mean),apply(pasos[11521:11808,1,drop=F],2,mean),apply(pasos[11809:12096,1,drop=F],2,mean),apply(pasos[12097:12384,1,drop=F],2,mean),apply(pasos[12385:12672,1,drop=F],2,mean),apply(pasos[12673:12960,1,drop=F],2,mean),apply(pasos[12961:13248,1,drop=F],2,mean),apply(pasos[13249:13536,1,drop=F],2,mean),apply(pasos[13537:13824,1,drop=F],2,mean),apply(pasos[13825:14112,1,drop=F],2,mean),apply(pasos[14113:14400,1,drop=F],2,mean),apply(pasos[14401:14688,1,drop=F],2,mean),apply(pasos[14689:14976,1,drop=F],2,mean),apply(pasos[14977:15264,1,drop=F],2,mean),apply(pasos[15265:15552,1,drop=F],2,mean),apply(pasos[15553:15840,1,drop=F],2,mean),apply(pasos[15841:16128,1,drop=F],2,mean),apply(pasos[16129:16416,1,drop=F],2,mean),apply(pasos[16417:16704,1,drop=F],2,mean),apply(pasos[16705:16992,1,drop=F],2,mean),apply(pasos[16993:17280,1,drop=F],2,mean),apply(pasos[17281:17568,1,drop=F],2,mean))


number=c(1:60)
names(medias)=number
medias
```

despues las medianas.

```{r}
medianas = c(apply(pasos[0:288,1,drop=F],2,median),apply(pasos[289:576,1,drop=F],2,median),apply(pasos[577:864,1,drop=F],2,median),apply(pasos[865:1152,1,drop=F],2,median),apply(pasos[1153:1440,1,drop=F],2,median),apply(pasos[1441:1728,1,drop=F],2,median),apply(pasos[1729:2016,1,drop=F],2,median),apply(pasos[2017:2304,1,drop=F],2,median),apply(pasos[2305:2592,1,drop=F],2,median),apply(pasos[2593:2880,1,drop=F],2,median),apply(pasos[2881:3168,1,drop=F],2,median),apply(pasos[3169:3456,1,drop=F],2,median),apply(pasos[3457:3744,1,drop=F],2,median),apply(pasos[3745:4032,1,drop=F],2,median),apply(pasos[4033:4320,1,drop=F],2,median),apply(pasos[4321:4608,1,drop=F],2,median),apply(pasos[4609:4896,1,drop=F],2,median),apply(pasos[4897:5184,1,drop=F],2,median),apply(pasos[5185:5472,1,drop=F],2,median),apply(pasos[5473:5760,1,drop=F],2,median),apply(pasos[5761:6048,1,drop=F],2,median),apply(pasos[6049:6336,1,drop=F],2,median),apply(pasos[6337:6624,1,drop=F],2,median),apply(pasos[6625:6912,1,drop=F],2,median),apply(pasos[6913:7200,1,drop=F],2,median),apply(pasos[7201:7488,1,drop=F],2,median),apply(pasos[7489:7776,1,drop=F],2,median),apply(pasos[7777:8064,1,drop=F],2,median),apply(pasos[8065:8352,1,drop=F],2,median),apply(pasos[8353:8640,1,drop=F],2,median),apply(pasos[8641:8928,1,drop=F],2,median),apply(pasos[8929:9216,1,drop=F],2,median),apply(pasos[9217:9504,1,drop=F],2,median),apply(pasos[9505:9792,1,drop=F],2,median),apply(pasos[9793:10080,1,drop=F],2,median),apply(pasos[10081:10368,1,drop=F],2,median),apply(pasos[10369:10656,1,drop=F],2,median),apply(pasos[10657:10944,1,drop=F],2,median),apply(pasos[10945:11232,1,drop=F],2,median),apply(pasos[11233:11520,1,drop=F],2,median),apply(pasos[11521:11808,1,drop=F],2,median),apply(pasos[11809:12096,1,drop=F],2,median),apply(pasos[12097:12384,1,drop=F],2,median),apply(pasos[12385:12672,1,drop=F],2,median),apply(pasos[12673:12960,1,drop=F],2,median),apply(pasos[12961:13248,1,drop=F],2,median),apply(pasos[13249:13536,1,drop=F],2,median),apply(pasos[13537:13824,1,drop=F],2,median),apply(pasos[13825:14112,1,drop=F],2,median),apply(pasos[14113:14400,1,drop=F],2,median),apply(pasos[14401:14688,1,drop=F],2,median),apply(pasos[14689:14976,1,drop=F],2,median),apply(pasos[14977:15264,1,drop=F],2,median),apply(pasos[15265:15552,1,drop=F],2,median),apply(pasos[15553:15840,1,drop=F],2,median),apply(pasos[15841:16128,1,drop=F],2,median),apply(pasos[16129:16416,1,drop=F],2,median),apply(pasos[16417:16704,1,drop=F],2,median),apply(pasos[16705:16992,1,drop=F],2,median),apply(pasos[16993:17280,1,drop=F],2,median),apply(pasos[17281:17568,1,drop=F],2,median))

number=c(1:60)
names(medianas)=number
medianas

```

y por último una gráfica comparatoria de actividad diaria.

```{r}
number=c(1:60)
names(medias)=number
barplot(medias, xlab="día", ylab="pasos", main="comparación de pasos promedio por día")
```


#DiscusiÃ³n#

Respecto al analisis de actividad por dia, se logra observar una tendencia de mayor actividad cerca de la mitad del dia y a las 3/4 partes. 

En la comparacion de graficas entre los fines de semana y el resto de dias podemos observar un ligero aumento de actividad los fines de semana, pasando de 40 la mayoria de las observaciones en comparacion al resto de dias que no son fin de semana, en donde se pueden observar muchas observaciones por debajo de este valor. 

#ConclusiÃ³n#

En algunos grupos de datos es posible observar ciertas tendencias en la actividad diaria (pasos), sin embargo de una forma global no se puede definir o establecer una tendencia de dicha actividad. 


