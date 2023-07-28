# Almacenamiento Amazon S3 Glacier

## Objetivos

- Cómo crear un *bucket* de Amazon S3.
- Cómo cargar objetos en las clases de almacenamiento de Amazon S3 Glacier.
- Cómo restaurar los objetos almacenados en las clases de almacenamiento Amazon S3 Glacier Flexible Retrieval o Amazon S3 Glacier Deep Archive.

## Lab Setup

|Tiempo de realización|Servicios utilizados|
| :-: | :-: |
|30 minutos|Amazon S3|


## Paso 1: crear un bucket con S3

1\.1: Iniciar sesión en la consola de Amazon S3

En la barra de búsqueda de servicios de la consola de AWS, ingrese “S3”. Debajo de la sección de resultados de la búsqueda de servicios, seleccione S3.

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.001.png)


1\.2: Crear un bucket de S3

Elija Buckets en el menú de S3 en la barra izquierda y luego seleccione el botón Create bucket.

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.002.png)

1\.3:

- Ingrese un nombre descriptivo globalmente único para el bucket. 
- Seleccione en qué región de AWS desea que se cree el bucket. 
- La configuración predeterminada de Block Public Access (Bloquear acceso público) es adecuada para esta carga de trabajo, así que deje la sección tal como está.

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.003.png)

1\.4:

- Luego, habilite el control de versiones del bucket para proteger los datos de eliminaciones o sobrescrituras accidentales o maliciosas de los usuarios. 
- Agregue algunas etiquetas para ayudar a llevar un seguimiento del costo asociado con los datos de archivo a lo largo del tiempo.

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.004.png)

1\.5: Luego, tiene la opción de habilitar el cifrado “en reposo” predeterminado para el bucket. La configuración aquí se aplicará a cualquier objeto cargado en el bucket en el que no haya definido los detalles de cifrado en reposo durante el proceso de carga. 

Habilite el cifrado del lado del servidor aprovechando las claves administradas del servicio de S3 (SSE-S3).

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.005.png)

1\.6:

- Ahora tiene la opción de habilitar el bloqueo de objetos de S3 en la sección Advanced settings (Configuración avanzada). Con el bloqueo de objetos de S3, puede almacenar objetos mediante el uso de un modelo de escritura única y lectura múltiple (WORM). El bloqueo de objetos de S3 puede ayudar a prevenir la eliminación o la sobrescritura de los objetos. Es apropiado habilitar el bloqueo de objetos de S3 a fin de garantizar que los usuarios no autorizados no eliminen de manera prematura los datos archivados importantes.
- Elija la opción Enable (Habilitar) y marque la casilla de verificación para reconocer que habilita las configuraciones del bloqueo de objetos de S3. 
- Luego, seleccione el botón Create bucket (Crear bucket).


1\.7: Configurar el bloqueo de objetos de S3

A continuación, la consola de S3 presentará un anuncio que le indicará que el bucket se creó correctamente. La consola de S3 también presentará un mensaje que le informará que se necesita configuración adicional para habilitar la característica de bloqueo de objetos de S3. Seleccione el enlace **Bucket details** presentado en el mensaje. Al hacer esta selección, se abrirá la pestaña **Properties**.

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.007.png)

1\.8:

- En la pestaña del bucket Properties, navegue hacia la sección **Object Lock** y seleccione el botón **Edit** . Aquí, puede establecer los valores predeterminados para los objetos cargados al bucket.
- Para este ejemplo, desea habilitar la retención de todos los objetos cargados a este bucket durante cinco años. Seleccione Enable (Habilitar) en la opción **Default retention**
- Elija el modo de gobernanza al seleccionar la opción Governance (Gobernanza) en **Default retention mode** 
- Ingrese “5” como el periodo de retención predeterminado
- Por último, seleccione **Years** para la unidad de medida y luego el botón **Save changes**.

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.008.png)

## Paso 2: cargar de datos al bucket

Ahora que ya creó y configuró el bucket, está listo para cargar datos de archivo en las clases de almacenamiento de Amazon S3 Glacier. 

2\.1: Carga de objetos

Navegue a la consola de S3 y seleccione la opción de menú Buckets. En la lista de buckets disponibles, seleccione el nombre del bucket que acaba de crear.

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.009.png)

2\.2: A continuación, elija la pestaña **Objects** (Objetos). 

Desde la sección **Objects** (Objetos), seleccione el botón **Upload** (Cargar).

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.010.png)

2\.3: Luego, seleccione el botón **Add files** 

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.011.png)

2\.4: En la sección Properties (Propiedades), seleccione la clase de almacenamiento de S3 a la que desea cargar su archivo. 

Seleccione Glacier Deep Archive, ya que el conjunto de datos de ejemplo necesita retenerse durante cinco años y existe una baja probabilidad de que se acceda a los datos con frecuencia.

Deje el resto de las opciones con la configuración predeterminada y seleccione el botón Upload (Cargar). 

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.012.png)

2\.5: Se mostrará un anuncio que le brindará información sobre el estado de carga del archivo.

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.013.png)

2\.6: Una vez que hayan finalizado las operaciones de carga de archivos, verá un resumen de las operaciones

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.014.png)

## Paso 3: Restaurar los datos

Ya que ha cargado los datos correctamente a S3 Glacier Deep Archive, revisemos el proceso de restauración de los datos.

3\.1: Iniciar la restauración de objetos

Navegue a la consola de S3 y seleccione la opción de menú Buckets.

En el menú Objects (Objetos), seleccione el nombre del archivo de prueba que acaba de cargar.

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.015.png)

3\.2: En la página Initiate restore, definirá la cantidad de días que desea que la copia restaurada esté disponible.

Luego, podrá elegir entre la recuperación estándar o en lotes.

Elija la opción **Standard retrieval** (Recuperación estándar).
Seleccione el botón **Initiate restore** (Iniciar restauración) para continuar.

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.016.png)

3\.4: Se mostrará una página de resumen que indicará si la solicitud de restauración se efectuó correctamente o si ocurrió algún error.  Seleccione el botón **Close** (Cerrar) para continuar.

En esta restauración estándar desde S3 Glacier Deep Archive, tendrá que esperar cerca de 12 horas para que el objeto temporal se restaure a la clase de almacenamiento Amazon S3 Standard-IA.

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.017.png)

3\.5: Verificar que se haya completado la restauración

- Ahora puede verificar que el objeto se haya restaurado después de esperar cerca de 12 horas para que se complete la operación de restauración.
- Aquí puede observar que el estado de restauración del objeto aparece como Completed (Completado).
- También se muestra la fecha de vencimiento de la restauración
- Este objeto estará disponible hasta el tiempo especificado en la sección **Restoration expiry date**.

![](resources/simpleStorage1/Aspose.Words.3cc80c03-2de5-4309-aa62-4637cd4a87b9.018.png)

## Paso 4: eliminar los recursos

4\.1: Eliminar el objeto de prueba

4\.2: Eliminar el bucket de prueba