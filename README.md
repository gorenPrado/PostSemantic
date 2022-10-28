# Reports Winby

Carpeta con todos los reports creados en JasperSoft para Winby

# Añadir carpeta de reports ha tu Jasper Local

Para crear un enlace entre tu jasper y la carpeta de reports de winby desde jasper lo primero es crear un nuevo proyecto
para eso vamos a File/Archivo --> New/Nuevo --> General (si no se ve buscar por project en el buscador que tiene el asistente) --> Project/Proyecto
una vez elegido el Proyecto desmarcamos la opcion de "Use default location"/"Usar localizacion por defecto" y buscamos la ruta de la carpeta de reports 
ha dia de hoy es esta "/trabajos/azure.devops/Winby/winby/src/Winby.Service.Api/reports" le damos un nombre a la carpeta del proyecto y finalizamos con el asistente
ahora la carpeta del proyecto de winby y la de jasper estan unidas y los cambios que se realicen en un lado se veran en el otro.

# Nomenclatura Metodos en el Back

Actualmente para diferenciarlos de metodos de creacion de pdfs que tenemos en la aplicación y para evitar confusiones uso
el prefijo de RunReportStream para crear todos los metodos que tengan que ver con las llamadas a Jasper.

# Consideraciones a tener trabajando en local

Para que jasper pueda crear los reports que estan definidos en el back se necesitan de 2 cosas
-1ª: Que el AppSettings apunte al id del recurso de Jasper que pertenezca a una carpeta padre de los Informes ejemplo:"qcompusoft_winby_es" o "Winby"
-2º: Que la bbdd que se esta usando coincida con la que tiene la carpeta a la que se esta llamando
Luego de que estas 2 cosas esten bien solo hay que confirmar que la ruta usada en el appService coincide con la del informe en el servidor.

# Reports

Los reports que se creen que tengan nombres identificativos y que esten en las carpetas de los modulos de Winby que los van a consumir.

## Subreports

Los subreports que puedan ser genericos lo ideal es tenerlos en una carpeta comun para que se puedan consumir siempre desde el mismo sitio 
actualmente estan en la carpeta "SubReportsComunes"
Si el report que se esta haciendo necesita uno especial para su uso gardarlo en la misma carpeta que el report o en una carpeta dentro de la que se genera al subir el report.

### Subida de Subreports al servidor de Jasper

Primero vas a la web del servidor de Jasper y buscamos la carpeta en la que queremos tener el subreport ya sea en la comun o la que pertenece al report
hacemos click derecho sobre la carpeta y vamos a "Agregar recurso" y dentro de las opciones que salen al poner el raton encima buscamos la opcion de "JRXML"
nos abrira la pagina del recurso y veremos un boton de subir archivo, clickamos y buscamos donde se encuentra fisicamente el subreport que hemos creado cuando haciamos el report
se le puede cambiar el nombre pero eso a gustos.
Una vez puesto ya en el servidor vamos al report ya creado y modificamos la ruta de acceso del subreport para ello clickamos en el subreport puesto como componente en el report
vamos a su pestaña de "Subreport" y en expression clickamos en la carpeta y elegimos la opcion que nos dice de coger un recurso de JasperReports Server y seguimos el asistente
para elegir la carpeta donde localizamos nuestro subreport y ya estaria para usar sin necesidad de que este en local.
