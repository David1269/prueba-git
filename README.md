#  google_image
## Descripcion
Nombre del modulo: Google images
Este módulo de Odoo 16 facilita la integración de imágenes a los productos utilizando la API de Google Custom Search. Permite buscar imágenes asociadas a los productos a través de códigos de barras y también proporciona la funcionalidad para cargar imágenes adicionales para ser utilizadas en el módulo de e-commerce de Odoo 16.

## Para que se va a usar
El proyecto consiste en un modulo de odoo16 al que se le implementara Google api “Custom Search” para traer imágenes de Google usando el código de barras de los productos.Esto con la finalidad de ayudar a que el departamento de almacén minimice tiempos y agilice procesos de registros de productos, haciendo automático el proceso de la carga de elementos multimedia.
<span style="color:red">Este texto está en rojo</span>
## Requisitos

Los requerimientos para realizar el proyecto es primeramente de la parte de odoo, se deben de instalar unos cuantos modulos:
1.- Modulo de inventario: Se necesita crear este modulo para heredar de el el modelo de product.template para poder usar elementos de la plantilla de productos,vistas,clases, ids y demas elementos de los que dispone el modelo. Este ademas de instalarlo en la interface de odoo se tiene que agregar como dependencia en el manifest.

2.- Modulo de venta: Este modulo se necesita para heredar tambien elementos y secciones que se van a necesitar para poder agregar imagenes en el apartado de imagenes adicionales del producto.

3.- Modulo de ecomerce: Este modulo es necesario ya que con este los elementos guardados de las imagenes adicionales y demas, se puedan agregar a este modulo para la venta en linea.

4.- Modulo para leer codigos de barra: Ese modulo se necesita para poder leer codigos de barras con un lector. Este ademas de instalarlo en la interface de odoo se tiene que agregar como dependencia en el manifest.

De parte externa:

1.- Api de google
Para la api se tienen que seguir una serie de pasos para poder configurar u obtener la llave los cuales son:
    1.1 Vaya a la página de Google Cloud Platform API & Services para generar credenciales de API para la búsqueda personalizada de Google. Aqui el enlace https://console.developers.google.com/ 
    1.2 Inicie sesión con su cuenta de Google.
    1.3 Seleccione o cree un proyecto API para almacenar las credenciales. Nómbrelo con un título específico (por ejemplo, imágenes de Odoo).
    1.4 En la sección de credenciales, haga clic en Crear credenciales y seleccione Clave API
Y listo una vez echo esto deberia de obtener una llave.¡Guardelo!

2.- Buscador de api de google (Custom search)
Para el buscador se siguen estos pasos: 
    2.1 Vaya al Motor de Búsqueda Programable de Google y haga clic en Comenzar. Inicie sesión con su cuenta de Google. Aqui el enlace https://programmablesearchengine.google.com/
    2.2 Seleccione el idioma y el nombre del motor de búsqueda. Nómbrelo con un título específico (por ejemplo, Imágenes de Odoo).
    2.3 Valide el formulario haciendo clic en Crear, después vaya al modo de edición del motor de búsqueda que creó (haciendo clic en Panel de control en la página de confirmación o en el nombre de su motor de búsqueda en la página de inicio).
    2.4 En la pestaña de elementos básicos, asegúrese de habilitar la búsqueda de imágenes, SafeSearch y buscar en toda la web.
Y listo una vez echo esto deberia de obtener una el id del buscador programable.¡Guardelo!

3.- Python: 
De python los requerimientos son simplemente librerias que en algunos casos es necesario instalar desde la terminal del proyecto:
    3.1 requests: para esta libreria debemos de tenerlo importado primeramente en el archivo de modelo python como "import requests" si en dado caso odoo le manda un error que mencione que la libreria no esta instalada, abra una nueva terminal en VSCode y coloque el comando pip install requests y listo
    3.2 


## Instalación
1.- Clona o descarga el repositorio del módulo.
2.- Coloca el directorio del módulo en la ruta de addons de tu instalación de Odoo.
3.- Reinicia el servidor Odoo.
4.- Instala el módulo desde la interfaz de administración de Odoo.

## Configuración
1.- Una vez instalado, dirígete a la configuración de Odoo. Busca el menú de configuración del módulo de imágenes de productos.
2.- Completa los parámetros de la API de Google Custom Search, incluyendo la API Key, ID del buscador, número de imágenes a obtener, tipo de archivo y tamaño de imagen.
Uso
# Actualización de Imágenes Principales de Productos
En la vista de productos, se proporciona un botón "Traer imágenes" que permite actualizar la imagen principal de un producto basado en su nombre utilizando la API de Google Custom Search.
# Carga de Imágenes Adicionales
Además de la imagen principal, este módulo permite cargar múltiples imágenes adicionales para cada producto. Utilizando el código de barras del producto, el sistema realizará una búsqueda y cargará las imágenes correspondientes.
# Integración con el Módulo de e-Commerce de Odoo 16
Las imágenes asociadas a los productos se integran automáticamente con el módulo de e-commerce de Odoo 16, proporcionando una experiencia visual completa para los clientes.