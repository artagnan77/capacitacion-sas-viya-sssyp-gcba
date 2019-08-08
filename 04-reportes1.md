---
title: "04-reportes1"
author: "SL"
date: "8/8/2019"
output: html_document
---

# Nuestro primer reporte

Ahora usando la tabla resultante del capítulo anterior, vamos a diseñar nuestro primer reporte.
El objetivo de este capítulo es aprender a realizar un reporte sencillo, para visualizar los datos de la tabla y agregar filtros, tanto fijos como dinámicos. 

## Objeto "Tabla de lista"

* En el panel de objetos a nuestra izquiera, vamos a seleccionar Tablas --> Tabla de lista y arrastramos hacia el area de trabajo de la Página 1.

<div class="figure" style="text-align: center">
<img src="../imagenes/cap4_img1_tabla_lista.png" alt="Tabla de lista"  />
<p class="caption">(\#fig:unnamed-chunk-1)Tabla de lista</p>
</div>

* Tenemos dos formas de agregar columnas, 
  1. Desde el panel general de datos, seleccionando los elementos y arrastrandolos hasta posicionarlos sobre la tabla,
  2. Teniendo seleccionado la tabla, desde el panel "Roles de datos", eligiendo la opción Columnas, Añadir
     Nótese que hay un asterisco rojo que acompaña la sección "Columnas" eso indica que es obligatorio agregar al menos una columna para que el objeto, en este caso una tabla, se pueda construir.
     

<div class="figure" style="text-align: center">
<img src="../imagenes/cap4_img2_agregar_elementos.png" alt="Tabla de lista"  />
<p class="caption">(\#fig:unnamed-chunk-2)Tabla de lista</p>
</div>

* Seleccionamos las columnas que deseamos visualizar en la tabla y hacemos click en "Aceptar"

<div class="figure" style="text-align: center">
<img src="../imagenes/cap4_img3_seleccionar_columnas.png" alt="Tabla de lista"  />
<p class="caption">(\#fig:unnamed-chunk-3)Tabla de lista</p>
</div>

Si todo salió bien, deberíamos estar viendo la tabla con los datos que elegimos. Es importante aclarar que el objeto tabla de lista tiene un límite de registros que se pueden visualizar, en general ese límite es de 40.000 filas. 

## Filtros fijos sobre el objeto
Todos los objetos aceptan este tipo de filtro sobre los datos.

Supongamos que queremos visualizar todos los expedientes cuyo "ESTADO_EXP" -estado actualizado del expediente- sea distinto a "Guarda Temporal":
* Siempre manteniendo el objeto seleccionado, en este caso nuestra tabla, seleccionamos la sección "filtros" del panel de la derecha.

<div class="figure" style="text-align: center">
<img src="../imagenes/cap4_img4_filtros.png" alt="Tabla de lista"  />
<p class="caption">(\#fig:unnamed-chunk-4)Tabla de lista</p>
</div>

* Hacemos click en "Nuevo filtro"
* Seleccionamos el elemento de datos sobre el que queremos aplicar el filtro, en nuestro caso "ESTADO_EXP".
* Destildamos los valores a descartar, "Guarda Temporal" y cualquier otro estado que queramos descartar.

## Filtros sobre la fuente de datos
Si queremos aplicar un filtro que afecte a todo el reporte, conviene utilizar esta opción.
Por ejemplo si quisieramos descartar en todo el reporte los expedientes en "ARCHIVO TEMPORAL".

* Vamos al panel de datos de la izquierda y seleccionamos la opción "Aplicar filtro a la fuente de datos..."
<div class="figure" style="text-align: center">
<img src="../imagenes/cap4_img5_filtros_fuente.png" alt="Tabla de lista"  />
<p class="caption">(\#fig:unnamed-chunk-5)Tabla de lista</p>
</div>
* Llegamos a una pantalla un poco más avanzada para la construcción de filtros.
* Buscamos el elemento de datos sobre el que vamos a aplicar el filtro, en nuestro caso nuevamente "ESTADO_EXP"
* Arrastramos el elemento hacia el panel y lo soltamos en el cuadro "condición"
* Ahora subimos y elegimos la solapa de "Operadores"
* Elegimos dentro del grupo "Comparación" el operador distinto "<>"
* En "cadena" escribimos el valor que queremos descartar, por ejemplo "ARCHIVO TEMPORAL"
* Por último hacemos click en "ACEPTAR"

Si todo funcionó como esperábamos la tabla no nos debería estar mostrando expedientes en ESTADO_EXP = "ARCHIVO TEMPORAL"

## Filtros dinámicos
Ahora vamos a sumar al reporte algunos controles simples para interactuar con la tabla en forma de filtros.
El filtro más comun que existe en todo tablero o reporte es el filtro de fechas y sino esta en modo de filtro, seguramente tendremos un gráfico que muestra alguna evolución temporal de alguna medida.

### Barra deslizante o slider

Supongamos en nuestro caso que queremos agregar un filtro dinámico utilizando la fecha de creación (fecha de caratulación del expediente):
* Vamos al panel de objetos y buscamos dentro del grupo "Controles" la "Barra deslizante". Este control es muy útil para usar en fechas.
* Arrastramos el objeto al area de trabajo intentando que nos quede arriba de la tabla.
* En el panel de roles de datos, seleccionamos "FECHA DE CREACIÓN"
* Por último, para que el control actúe como filtro sobre la tabla, manteniendo seleccionado el objeto, vamos a la sección "Acciones" del panel de la derecha.
* Elegimos la tabla de lista, dentro de "Enlaces de objeto"

<div class="figure" style="text-align: center">
<img src="../imagenes/cap4_img6_filtros_dinamicos_fecha.png" alt="Tabla de lista"  />
<p class="caption">(\#fig:unnamed-chunk-6)Tabla de lista</p>
</div>

Ahora, si modificamos los valores de la barra deslizante, la tabla se debería actualizar, filtrando los datos en base al rango de fechas establecido.


### Lista o lista desplegale

Supongamos ahora que queremos incluir un filtro para seleccionar una o varias tratas.
Para ello podemos usar los controles lista o lista desplegable. El primero nos permitirá elegir varios valores, la lista desplegable en cambio, sólo uno.

* Nuevamente nos dirigimos al panel de objetos, y dentro del grupo de "Controles" seleccionamos y arrastramos hacia el reporte, la "Lista" o "Lista desplegable". En este caso elegiremos "Lista", ya que queremos poder seleccionar varias tratas.
*Tratamos de ubicar el objeto a la izquierda de nuestra tabla:

<div class="figure" style="text-align: center">
<img src="../imagenes/cap4_img7_filtro_lista.png" alt="Tabla de lista"  />
<p class="caption">(\#fig:unnamed-chunk-7)Tabla de lista</p>
</div>

* En el panel de roles de datos, seleccionamos "CODIGO_EXTRACTO"
* Luego, no debemos olvidar generar "la interacción" desde la sección "Acciones" del panel de la derecha al igual que el filtro anterior.

Ahora si elegimos alguna trata, deberíamos ver como se actualiza la tabla.

## Ejercicio de ejemplo con comparación de datos
Si llegamos con el tiempo, podemos hacer un ejercicio para visualizar diferencias entre "ESTADO" y  "ESTADO_EXP"

## Acciones automáticas en todos los objetos
Lo veremos en otro capítulo

## Contenedores
Lo veremos en otro capítulo














