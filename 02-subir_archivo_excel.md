---
output:
  pdf_document: default
  html_document: default
---
# Subir nuestros datos a SAS Viya

Como vimos anteriormente, la plataforma de BI nos permite acceder a una base de datos integrada de muchas y variadas fuentes de datos. Los datos de las diferentes fuentes se encuentran integrados en un solo modelo de datos, lo que permite la explotación integral de la información.

Una de las fuentes principales del Datawarehouse que mantenemos en la Subsecretaria es la base de datos del ecosistema SADE.

Un usuario de self-service podrá acceder a las tablas que este autorizado en función de su sector/rol dentro de la organización.

Pero a veces el usuario necesita trabajar con otro set de datos, proveniente otro sector o bajado desde otra fuenta de datos. En estos casos puede subir su propio set de datos, dede un archivo CSV o una planilla excel y luego no sólo trabajar con estos datos sino también en caso de aplicar, combinarlos con tablas ya disponibles en la plataforma.

## Subir un archivo excel 

Lo primero que debemos hacer antes de subir una planilla excel es verificar que sea lo más limpia posible para evitar errores, la planilla debe contener los datos en forma de tabla, con sus columnas y registros, sin filas vacías y con el menor formato posible.

El archivo elegido en nuestro caso contiene una tabla con 3 columnas:

* EXPEDIENTE_CALC
* CODIGO_EXTRACTO
* ESTADO_EXP

<div class="figure" style="text-align: center">
<img src="../imagenes/cap1_subir_excel_img_0.1.png" alt="Archivo excel a subir"  />
<p class="caption">(\#fig:unnamed-chunk-1)Archivo excel a subir</p>
</div>

Podría tratarse de un archivo provisto por otro sector requiriendo cierta información para los expedientes incluídos en el mismo. O bien una lista de expedientes que necesitamos cotejar versus los datos de la base de Expediente Electrónico de SADE.

### Nuestra propia tabla CAS
Los pasos a seguir para construir nuestra propia tabla CAS a partir del archivo serían los siguientes:

1. Vamos a la sección "Gestionar Datos"

2. Hacemos click en el "Menú de Aplicaciones":
<div class="figure" style="text-align: center">
<img src="../imagenes/cap1_subir_excel_img_1.3.png" alt="Menu de aplicaciones"  />
<p class="caption">(\#fig:unnamed-chunk-2)Menu de aplicaciones</p>
</div>

3. Elegimos la opción "Gestionar Datos":
<div class="figure" style="text-align: center">
<img src="../imagenes/cap1_subir_excel_img_2.2.png" alt="Opción del menú Gestionar Datos"  />
<p class="caption">(\#fig:unnamed-chunk-3)Opción del menú Gestionar Datos</p>
</div>

En esta sección podemos ver todas las tablas CAS disponibles que tenemos.

4. Para subir nuesro archivo y construir nuestra propia tabla CAS debemos hacer click en Importar:
<div class="figure" style="text-align: center">
<img src="../imagenes/cap1_subir_excel_img_3.png" alt="Importar"  />
<p class="caption">(\#fig:unnamed-chunk-4)Importar</p>
</div>

5. Seleccionamos "Archivo local":
<div class="figure" style="text-align: center">
<img src="../imagenes/cap1_subir_excel_img_4.2.png" alt="Subir archivo local"  />
<p class="caption">(\#fig:unnamed-chunk-5)Subir archivo local</p>
</div>

Ahora se nos abrirá el "wizard" de windows para que naveguemos por nuestras carpetas y seleccionemos el archivo. 

Una vez seleccionado, le damos al botón de "Abrir" y se abrirá la siguiente pantalla para ultimar los detalles de nuestra importación:
<div class="figure" style="text-align: center">
<img src="../imagenes/cap1_subir_excel_img_5.png" alt="Subir archivo local"  />
<p class="caption">(\#fig:unnamed-chunk-6)Subir archivo local</p>
</div>

6. Por último hacemos click en "Importar elemento".
Si todo esta bien, el sistema arrojará un mensaje indicando que el proceso terminó correctamente.
Asimismo, si ahora vamos a ver las tablas disponibles, deberíamos encontrar nuestra tabla cargada.


## Subir un archivo csv 

Google nos dirá: "Los archivos CSV son un tipo de documento en formato abierto sencillo para representar datos en forma de tabla, en las que las columnas se separan por comas y las filas por saltos de línea."

Si navegamos por "BA Data" https://data.buenosaires.gob.ar/ u otro sitio de intercambio de información, encontraremos que los set de datos disponibles en general se presentan en este formato.

Seguramente tengamos menos problemas al operar con archivos de este tipo.

### Pasos para subir un archivo CSV

Repetimos todos los pasos que vimos al subir un excel hasta el punto 5.
La pantalla a la que llegamos en este caso, presenta algunas opciones que debemos considerar, dependiendo de como este armardo nuestro archivo CSV.

* Delimitador
En nuestro archivo de ejemplo, el delimitador de columnas es ";", por lo tanto debemos modificar el valor por defecto ";":
<div class="figure" style="text-align: center">
<img src="../imagenes/cap1_2_subir_csv_1.1.png" alt="Subir archivo local"  />
<p class="caption">(\#fig:unnamed-chunk-7)Subir archivo local</p>
</div>

<div class="figure" style="text-align: center">
<img src="../imagenes/cap1_2_subir_csv_1.png" alt="Subir archivo local"  />
<p class="caption">(\#fig:unnamed-chunk-8)Subir archivo local</p>
</div>

También podemos indicar si la primera fila contiene o no los nombres de las columnas.
Una vez configuradas todas las opciones en base al archivo que vamos a subir, hacemos click en "Importar elemento".
Y si todo salió bien, llegamos al final del proceso, con un mensaje que indica que todo salió bien:
<div class="figure" style="text-align: center">
<img src="../imagenes/cap1_2_subir_csv_3.0_OK.png" alt="Subir archivo local"  />
<p class="caption">(\#fig:unnamed-chunk-9)Subir archivo local</p>
</div>


### Posibles errores

Si obtenemos un error feo, como el siguiente:
<div class="figure" style="text-align: center">
<img src="../imagenes/cap1_2_subir_csv_2.1_ERROR.png" alt="Subir archivo local"  />
<p class="caption">(\#fig:unnamed-chunk-10)Subir archivo local</p>
</div>
Tenemos un problema de encoding en el archivo, esto pasa cuando el archivo se guardo con un juego de caracteres diferente al que le indicamos a SAS al momento de subir el archivo. Un formato muy común y el que vamos a usar es "UTF-8" este cambio lo podemos hacer desde un editor de texto, como "Notepad++"

<div class="figure" style="text-align: center">
<img src="../imagenes/cap1_2_subir_csv_2.2_CORREGIR_ENCODING.png" alt="Subir archivo local"  />
<p class="caption">(\#fig:unnamed-chunk-11)Subir archivo local</p>
</div>










