---
title: "06-mapas"
author: "SL"
date: "8/8/2019"
output: html_document
---

# Mapas

<<Este capítulo esta en construcción, falta completar.>>

El objetivo de este capítulo es explicar paso a paso como crear una visualización de datos sobre mapas geográficos.
Para esto haremos uso de tablas que ya estan precargadas en SAS Viya, y que reunen la información de los polígonos. 

<<Explicar un poco el tema proveedores de polígonos y los datos que debemos tener en nuestro set de datos>>

1. Nuevo reporte, opción "Explorar y visualizar datos"
2. Agregamos la tabla CAS al reporte:


<div class="figure" style="text-align: center">
<img src="../imagenes/cap6_img_01.- Agrego la CAS.png" alt="Añadir fuente de datos"  />
<p class="caption">(\#fig:unnamed-chunk-1)Añadir fuente de datos</p>
</div>

3. Generamos el elemento calculado "SECCION_MANZANA"

<div class="figure" style="text-align: center">
<img src="../imagenes/cap6_img_02.- Genero el elemanto calculado SECCION_MANZANA.png" alt="Añadir fuente de datos"  />
<p class="caption">(\#fig:unnamed-chunk-2)Añadir fuente de datos</p>
</div>

4. Generamos el elemento calculado, Elemento greográfico, "SECCION_MANZANA"

<div class="figure" style="text-align: center">
<img src="../imagenes/cap6_img_03.- Genero área geografica SECCION_MANZANA.png" alt="Añadir fuente de datos"  />
<p class="caption">(\#fig:unnamed-chunk-3)Añadir fuente de datos</p>
</div>

5. Generamos el elemento calculado "SECCION_MANZANA_PARCELA"

<div class="figure" style="text-align: center">
<img src="../imagenes/cap6_img_04.- Genero el elemanto calculado SECCION_MANZANA_PARCELA.png" alt="Añadir fuente de datos"  />
<p class="caption">(\#fig:unnamed-chunk-4)Añadir fuente de datos</p>
</div>

6. Generamos el elemento calculado, Elemento greográfico, "SECCION_MANZANA_PARCELA_GEO"

<div class="figure" style="text-align: center">
<img src="../imagenes/cap6_img_05.- Genero el área geografica SECCION_MANZANA_PARCELA_GEO.png" alt="Añadir fuente de datos"  />
<p class="caption">(\#fig:unnamed-chunk-5)Añadir fuente de datos</p>
</div>

7. Generamos la jerarquía con los elementos geográficos

<div class="figure" style="text-align: center">
<img src="../imagenes/cap6_img_06.- Genero la jerarquia.png" alt="Añadir fuente de datos"  />
<p class="caption">(\#fig:unnamed-chunk-6)Añadir fuente de datos</p>
</div>

8. Seleccionamos el grafico "Mapa Geo"

9. Asociamos la jerarquía creada como rol de datos del mapas

<div class="figure" style="text-align: center">
<img src="../imagenes/cap6_img_07.- Asocio  jerarquia como Rol del mapa.png" alt="Añadir fuente de datos"  />
<p class="caption">(\#fig:unnamed-chunk-7)Añadir fuente de datos</p>
</div>

10. Creamos otroa mapa y le asociamos el rol "ManzanaGEO"

<div class="figure" style="text-align: center">
<img src="../imagenes/cap6_img_08.- Asocio  manzanaGEO como Rol del derecho.png" alt="Añadir fuente de datos"  />
<p class="caption">(\#fig:unnamed-chunk-8)Añadir fuente de datos</p>
</div>

11. Generamos la interacción automática entre todos los objetos
<div class="figure" style="text-align: center">
<img src="../imagenes/cap6_img_09.- Agrego Filtro Todos contra todos.png" alt="Añadir fuente de datos"  />
<p class="caption">(\#fig:unnamed-chunk-9)Añadir fuente de datos</p>
</div>

<div class="figure" style="text-align: center">
<img src="../imagenes/cap6_img_10.- Navego y fltro.png" alt="Añadir fuente de datos"  />
<p class="caption">(\#fig:unnamed-chunk-10)Añadir fuente de datos</p>
</div>
