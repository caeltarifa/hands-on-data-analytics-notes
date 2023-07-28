# Introducción al uso de Amazon S3 Intelligent-Tiering

## Objetivos

- Crear un bucket de Amazon S3.
- Cargar objetos directamente en la clase de almacenamiento Amazon S3 Intelligent-Tiering.
- Trasladar objetos almacenados en S3 Standard o S3 Standard-Infrequent Access (S3 Standard-IA) a la clase de almacenamiento S3 Intelligent-Tiering.
- Habilitar los niveles opcionales asíncronos de archivo de S3 Intelligent-Tiering y obtener mayores ahorros en costos de almacenamiento para datos a los que se accede con muy poca frecuencia.
- Restaurar sus objetos almacenados en los niveles opcionales de archivo.


|Tiempo de realización|Servicios utilizados|
| :-: | :-: |
|45 minutos|Amazon S3|
|Requisitos previos|Ninguno|


## Paso 1: crear un bucket con S3

1\.1: Iniciar sesión en la consola de Amazon S3

En la barra de búsqueda de servicios de la consola de AWS, ingrese “S3”. Debajo de la sección de resultados de la búsqueda de servicios, seleccione S3.

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.001.png)


1\.2: Crear un bucket de S3

Elija Buckets en el menú de S3 en la barra izquierda y luego seleccione el botón Create bucket.

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.002.png)

1\.3:

- Ingrese un nombre descriptivo globalmente único para el bucket. 
- Seleccione en qué región de AWS desea que se cree el bucket. 
- La configuración predeterminada de Block Public Access (Bloquear acceso público) es adecuada para esta carga de trabajo, así que deje la sección tal como está.

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.003.png)

1\.4:

- La configuración predeterminada Block Public Access (Bloquear acceso público) es adecuada para esta carga de trabajo, así que deje la configuración predeterminada en esta sección.

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.004.png)

1\.5: 

A continuación, deje la configuración predeterminada con las ACL deshabilitadas

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.005.png)

1\.6:

Luego, agregue una etiqueta de bucket para ayudar a realizar un seguimiento de los costos asociados con esta carga de trabajo. 

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.006.png)

1\.7: 

Ahora habilite el cifrado predeterminado para el bucket.

Para esta carga de trabajo, habilite el Server-side encryption (Cifrado del lado del servidor) y aproveche las claves administradas del servicio de Amazon S3 (SSE-S3).

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.007.png)

1\.8:

- En Advanced settings (Configuración avanzada), para esta carga de trabajo no necesitamos Object Lock (Bloqueo de objetos), así que deje esa opción deshabilitada
- seleccione Create bucket (Crear bucket) para crear el bucket de S3

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.008.png)

## Paso 2: cargar datos en la clase de almacenamiento S3 Intelligent-tier

Ahora que ya creó y configuró su bucket, está listo para cargar datos en la clase de almacenamiento Amazon S3 Intelligent-Tiering.

2\.1: Carga de un objeto

Navegue a la consola de S3 y seleccione la opción de menú Buckets. En la lista de buckets disponibles, seleccione el nombre del bucket que acaba de crear.

![ref1]

2\.2:

- A continuación, elija la pestaña **Objects** (Objetos). 
- Desde la sección **Objects** (Objetos), seleccione el botón **Upload** (Cargar).

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.010.png)

2\.3:

Luego, seleccione el botón **Add files** 

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.011.png)

2\.4:

- En la sección Properties (Propiedades), seleccione Intelligent-Tiering. Deje el resto de las opciones con la configuración predeterminada y elija Upload (Cargar).



![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.012.png)

2\.5:

- Una vez que hayan finalizado las operaciones de carga de archivos, verá un resumen de las operaciones que indicará si se completaron correctamente o si presentaron errores. 
- En este caso, el archivo se cargó correctamente. 
- A continuación, seleccione Close (Cerrar).

![ref2]

## Paso 3: 

Trasladar objetos a la clase de almacenamiento Amazon S3 Intelligent-Tiering mediante el uso del ciclo de vida de Amazon S3

Cuando los datos se cargan por medio de programación en Amazon S3, es posible que algunos clientes no sean compatibles con la clase de almacenamiento S3 Intelligent-Tiering. Como resultado, esos clientes cargarán los datos en la clase de almacenamiento Amazon S3 Standard. En este caso, puede utilizar el ciclo de vida de Amazon S3 para realizar una transición inmediata de los objetos de la clase de almacenamiento S3 Standard a la clase de almacenamiento S3 Intelligent-Tiering.

Aprenderá a establecer una configuración de ciclo de vida de S3 en su bucket.

3\.1: 

` `En la lista de buckets disponibles, seleccione el nombre del bucket que creó en el paso 1.


![ref1]

3\.2:

Seleccione la pestaña Management (Administración) 

Seleccione Create lifecycle rule (Crear regla de ciclo de vida) en la sección Lifecycle rules (Reglas de ciclo de vida).


![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.014.png)

3\.3: Crear una regla de ciclo de vida

- Cuando crea una regla de ciclo de vida de S3, tiene la opción de limitar el alcance de la regla por prefijo, etiqueta o tamaño de objeto al especificar un tamaño de objeto mínimo y máximo entre 0 bytes y 5 TB.
- De forma predeterminada, los objetos de menos de 128 KB nunca se trasladan a la clase de almacenamiento S3 Intelligent-Tiering porque no son aptos para la designación automática de niveles.

Para esta carga de trabajo, queremos aplicar la regla de ciclo de vida a todos los objetos del bucket y, por lo tanto, no aplicaremos ningún filtro.

- Ingrese un nombre de regla de ciclo de vida descriptivo.
- Seleccione Apply to all objects in the bucket (Aplicar a todos los objetos del bucket).
- Seleccione la casilla de verificación I acknowledge that this rule will apply to all objects in the bucket (Acepto que esta regla se aplicará a todos los objetos del bucket).
- En Lifecycle rule actions (Acciones de la regla de ciclo de vida), seleccione la casilla de verificación Move current versions of objects between storage classes (Mover versiones actuales de objetos entre clases de almacenamiento).
- En la sección Transition current versions of objects between storage classes (Traslado de versiones actuales de objetos entre clases de almacenamiento), seleccione Intelligent-Tiering como Choose storage class transitions (Elegir transiciones de clase de almacenamiento) e ingrese “0” como Days after object creation (Días después de la creación del objeto).
- Finalmente, elija Create rule (Crear regla).

![ref3]

![ref4]

En este paso, creamos una regla de ciclo de vida para realizar una transición inmediata de los archivos cargados en la clase de almacenamiento S3 Standard a la clase de almacenamiento S3 Intelligent-Tiering.

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.017.png)

Paso 4: activar los niveles opcionales asíncronos de archivo de Amazon S3 Intelligent-Tiering

## Paso 4: Activar los niveles opcionales asíncronos de archivo de Amazon S3 Intelligent-Tiering

Para ahorrar aún más en los datos que no requieren una recuperación inmediata, puede activar los niveles opcionales de acceso de archivo profundo y de acceso de archivo asíncronos. Cuando se activan estos niveles, los objetos a los que no se accede durante 90 días consecutivos se trasladan directa y automáticamente al nivel de acceso de archivo con un ahorro en los costos de almacenamiento de hasta el 71 %. Los objetos a los que no se accede durante 180 días consecutivos se trasladan al nivel de acceso de archivo profundo con un ahorro en los costos de almacenamiento de hasta el 95 %.

Para acceder a los objetos archivados en los niveles opcionales de acceso de archivo profundo y de acceso de archivo asíncronos, primero debe restaurarlos. El paso 6 de este tutorial lo guiará a través del proceso de restauración.

Para esta carga de trabajo, activaremos solo el nivel de acceso de archivo profundo como se muestra a continuación:

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.018.png)

4\.1: 

En la lista de buckets disponibles, seleccione el nombre del bucket que creó en el paso 1.

![ref5]

4\.2: 

Seleccione la pestaña Properties (Propiedades).

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.020.png)

4\.3:

Vaya a la sección Intelligent-Tiering Archive configurations (Configuraciones de archivo de Intelligent-Tiering) y elija Create configuration (Crear configuración).

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.021.png)

4\.4:

En la sección Archive configuration settings (Ajustes de configuración de archivo), especifique un nombre de configuración descriptivo para su configuración de archivo de S3 Intelligent-Tiering.

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.022.png)

4\.5:

- Para esta carga de trabajo, queremos archivar solo un subconjunto del conjunto de datos en función de las etiquetas de objeto. Para hacerlo, en Choose a configuration scope (Elegir un alcance de configuración), seleccione Limit the scope of this configuration using one or more filters (Limitar el alcance de esta configuración con uno o más filtros).
- En la sección Object Tags (Etiquetas de objeto), elija Add tag (Agregar etiqueta) e ingrese “opt-in-archive” (archivo opcional) como Key (Clave) y “true” (verdadero) como Value (Valor) de la etiqueta.
- Asegúrese de que el estadode la configuración sea Enable (Habilitar).

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.023.png)

4\.6:

Los objetos en la clase de almacenamiento S3 Intelligent-Tiering se pueden archivar en el nivel de acceso de archivo profundo después de que no se haya accedido a ellos durante un periodo de entre seis meses y dos años. Para esta carga de trabajo, queremos archivar los objetos a los que no se ha accedido durante seis meses, a fin de asegurarnos de archivar solo los datos que no se utilizan. Para hacerlo, en la sección Archive rule actions (Acciones de la regla de archivo), seleccione Deep Archive Access tier (Nivel de acceso de archivo profundo), ingrese 180 como el número de días consecutivos sin acceso antes de archivar los objetos en el nivel de acceso de archivo profundo y seleccione Create (Crear).

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.024.png)


## Paso 5: cargar un archivo con el nivel opcional de acceso de archivo profundo habilitado

En el paso 4, habilitamos el nivel de acceso de archivo profundo solo para los objetos con la etiqueta “opt-in-archive:true”. Ahora aprenderá cómo aplicar la etiqueta correcta durante el proceso de carga para habilitar el nivel de acceso de archivo profundo.

5\.1:

En la lista de buckets disponibles, seleccione el nombre del bucket que creó en el paso 1.

![ref1]

5\.2: 

A continuación, seleccione la pestaña Objects (Objetos). Luego, desde la sección Objects (Objetos), seleccione Upload (Cargar).

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.025.png)

5\.3: 

Elija Add files (Agregar archivos). Navegue a su sistema de archivos local para ubicar el archivo que desea cargar. Seleccione el archivo apropiado y luego elija Open (Abrir). Su archivo aparecerá en la sección Files and folders (Archivos y carpetas).

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.026.png)

5\.4:

En la sección Properties (Propiedades), seleccione Intelligent-Tiering. Para obtener más información acerca de la clase de almacenamiento Amazon S3 Intelligent-Tiering

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.027.png)

5\.5:

Debido a que queremos que el archivo se archive después de seis meses sin acceso, en la sección Tags – optional (Etiquetas: opcional), seleccione Add tag (Agregar etiqueta) e ingrese “opt-in-archive” (archivo opcional) en Key (Clave) y “true” (verdadero) en Value (Valor), y elija Upload (Cargar).

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.028.png)

5\.6:

- Una vez que hayan finalizado las operaciones de carga de archivos, verá un resumen de las operaciones que indicará si la carga se completó correctamente o si presentó errores. 
- En este caso, el archivo se cargó correctamente. 
- Seleccione Close (Cerrar).

![ref2]

## Paso 6: restaurar los datos archivados en el nivel opcional de acceso de archivo profundo

Antes de poder descargar un archivo almacenado en el nivel de acceso de archivo profundo, debe iniciar la solicitud de restauración y esperar hasta que el objeto se mueva al nivel de acceso frecuente.

En este paso, aprenderá cómo restaurar un archivo.

6\.1:

En la lista de buckets disponibles, seleccione el nombre del bucket que creó en el paso 1.

![ref5]

6\.2: 

En la pestaña Objects (Objetos), seleccione el archivo almacenado en el nivel de acceso de archivo profundo de Intelligent-Tiering.

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.029.png)

6\.3:

En la pestaña Properties (Propiedades), notará que los botones Download (Descargar) y Open (Abrir) están atenuados, y un anuncio le notifica que para acceder el archivo primero debe restaurarlo.

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.030.png)

6\.4:

Para iniciar la restauración, elija Initiate restore (Iniciar restauración).

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.031.png)

6\.5:

- En el siguiente formulario de Initiate restore (Iniciar restauración), puede seleccionar el tipo de restauración.
- La recuperación masiva suele tardar 48 horas, mientras que la recuperación estándar normalmente se completa en 12 horas; ambas opciones están disponibles sin cargo.
- Para esta carga de trabajo, seleccione la opción Standard retrieval (Recuperación estándar), ya que se debe completar la restauración en 12 horas.
- Seleccionar Initiate restore (Iniciar restauración) para iniciar la restauración.

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.032.png)

6\.6:

- Después de iniciar la restauración, verá un resumen de las operaciones que indicará si se inició correctamente o si presentó errores. 
- En este caso, la restauración se ha iniciado correctamente. 
- Seleccione Close (Cerrar).

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.033.png)

6\.7:

En la pestaña Properties (Propiedades) del archivo, puede monitorear el estado del proceso de restauración.

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.034.png)

6\.8:

Una vez que se haya completado la operación de restauración (generalmente dentro de las 12 horas), podrá descargar el archivo al seleccionar Download (Descargar).

![](resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.035.png)

## Paso 7: eliminar los recursos

7\.1: Eliminar el objeto de prueba

7\.2: Eliminar el bucket de prueba

[ref1]: resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.009.png
[ref2]: resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.013.png
[ref3]: resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.015.png
[ref4]: resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.016.png
[ref5]: resources/simpleStorage2/Aspose.Words.c3b6511c-bfee-497b-90c2-bf2c5784dcc8.019.png
