---
title: "03-UnionFuentes"
author: "SL"
date: "8/8/2019"
output: html_document
---

# Union de fuentes de datos

Hay muchos supuestos o situaciones en los que podemos necesitar hacer una combinación de diferentes fuentes de datos. Incluso cuando hablamos de Datawarehouse o BI, siempre en algún momento haremos referencia a integrar diferents fuentes de datos.

En este capítulo, haciendo uso de las tablas que subimos en el capítulo anterior, vamos a practicar los famosos "JOINS" o uniones de datos.

En general vamos a tener la mayoría de las tablas que necesitamos disponibles en el Datawarehouse, ya que esta tarea de hacer las "uniones" nos viene ya resuelta por el equipo de BI. 

Pero no siempre es así. Supongamos que un sector nos pasa un listado de expedientes con algún problema o situación particular y necesitamos obtener más datos asociados a ese listado de expedientes o bien combinar este listado con datos actualizados de SADE, que sabemos que tenemos disponible en la plataforma.

Supongamos que ese listado fue el primer excel que subimos en el capítulo anterior: <b>"CURSO_BI_GCBA_EXPEDIENTES"</b>


## Cómo hacer una union de tablas

* Una forma de hacer una unión de fuentes de datos en SAS Viya es dentro de un reporte. Esta es la opción que veremos en esta práctica.

1. Iniciamos un nuevo reporte usando la opción del menú: "Explorar y visualizar datos"

<div class="figure" style="text-align: center">
<img src="./imagenes/cap3_union_1_nuevo_report.png" alt="Explorar y visualizar datos"  />
<p class="caption">(\#fig:unnamed-chunk-1)Explorar y visualizar datos</p>
</div>

<div class="figure" style="text-align: center">
<img src="./imagenes/cap3_union_2.png" alt="Nuevo reporte"  />
<p class="caption">(\#fig:unnamed-chunk-2)Nuevo reporte</p>
</div>

2. Desde el panel de datos, hacemos click en "Seleccione para añadir fuente de datos".
Otra opción es hacer click en el icono de la derecha, "Acciones" y seleccionar "Añadir fuente de datos"

3. En la siguiente ventana "Abrir fuente de datos" buscamos nuestra tabla, para ello basta con escribir las primeras letras para filtrar el listado de tablas disponibles hasta que podamos encontrar la tabla deseada:

<div class="figure" style="text-align: center">
<img src="./imagenes/cap3_union_3.png" alt="Selección de tabla"  />
<p class="caption">(\#fig:unnamed-chunk-3)Selección de tabla</p>
</div>

4. Seleccionamos nuestra tabla, "CURSO_BI_GCBA_EXPEDIENTES" y presionamos "Aceptar"

5. Volvemos al icono que nos abre las opciones de datos y elegimos en este caso "Nueva unión de fuentes de datos..."

<div class="figure" style="text-align: center">
<img src="./imagenes/cap3_union_5bis.png" alt="Nueva unión de fuentes de datos"  />
<p class="caption">(\#fig:unnamed-chunk-4)Nueva unión de fuentes de datos</p>
</div>

6. En la siguiene pantalla, debemos:
* Elegir la segunda tabla en "Fuente de datos 2"
  En este caso vamos a elegir la segunda tabla que subimos en el capítulo anterior que contiene datos de domicilios asociados a los expedientes.
* Asignar un nombre a la tabla resultado que crearemos con la unión

<div class="figure" style="text-align: center">
<img src="./imagenes/cap3_union_6.png" alt="Segunda tabla"  />
<p class="caption">(\#fig:unnamed-chunk-5)Segunda tabla</p>
</div>


* Elegir el tipo de unión

<div class="figure" style="text-align: center">
<img src="./imagenes/cap3_union_8_tipo_union.png" alt="Tipo de unión"  />
<p class="caption">(\#fig:unnamed-chunk-6)Tipo de unión</p>
</div>
En este caso elegiremos la opción "Union izquierda" ya que no queremos perder datos de la tabla 1, que es la que debemos analizar, es la tabla que nos pasó el usuario para verificar.

<i>Explicar las diferencias de los distintos tipos de unión</i>


* Seleccionar las columnas que deseamos incluir en la unión

<div class="figure" style="text-align: center">
<img src="./imagenes/cap3_union_9_sel_columnas.png" alt="Selección de columnas"  />
<p class="caption">(\#fig:unnamed-chunk-7)Selección de columnas</p>
</div>

Si todo salió bien, deberíamos ver nuestra tabla resultado en la lista de fuentes de datos del reporte.


## Guardar reporte

Siempre es sano a medida que avanzamos ir guardando los cambios.
Guardamos el reporte en  nuestra carpeta personal "MyFolder".

<div class="figure" style="text-align: center">
<img src="./imagenes/cap3_union_10_Guardar_Reporte.png" alt="Guardar reporte"  />
<p class="caption">(\#fig:unnamed-chunk-8)Guardar reporte</p>
</div>

## Nueva unión de datos

Para reforzar este punto y además sumar otras columas a nuestra tabla, vamos a realizar una nueva unión, utilizando como segunda fuente de datos la tabla "DIM_EXPEDIENTE_ELECTRONICO". Esta tabla tiene todos los expedientes de SADE y datos principales asociados a los mismos, como ser el estado actualizado, la fecha de caratulación, el usuario, la repartición, etc.

Como mínimo seleccionamos estas columnas para la práctica:

<div class="figure" style="text-align: center">
<img src="./imagenes/cap3_union_11_union_con_dim_sel_columns.png" alt="Selección de columnas"  />
<p class="caption">(\#fig:unnamed-chunk-9)Selección de columnas</p>
</div>

Y por último, nuevamente elegimos "Unión izquierda", porque queremos mantener todos los registros de la primera tabla.
<i>Explicar más este punto</i>

<div class="figure" style="text-align: center">
<img src="./imagenes/cap3_union_12_left_join.png" alt="Left Join"  />
<p class="caption">(\#fig:unnamed-chunk-10)Left Join</p>
</div>

Para esta nueva unión usaremos el nombre <b>CURSO_BI_EXPEDIENTES</b>
Si todo salió bien deberíamos ver agregada la nueva fuente de datos al reporte.

Genial, explotaremos esta tabla en los capítulos siguientes!

