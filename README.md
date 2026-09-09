Api Flash - Gestión de Productos nube

Cada método tiene una función: 

GET: consulta la información de los productos.

POST: crea o agrega nuevos productos.

PUT: actualiza la información de un producto existente.

DELETE: elimina un producto.


Antes de todo para poder realizar el programa debemos realizar lo siguiente:
1. Debemos comprobar que Python este instalado ejecutando el comando: python --version
2. También debemos verificar la instalación de Git con el comando: git --version
3. Debemos tener instalado también el postman ya que con el realizaremos las pruebas de los diferentes endpoints.


Proceso para ejecutar el proyecto
1. Clonar el repositorio
   Primero se debe descargar el proyecto desde GitHub utilizando los comandos
   git clone https://github.com/botellosamara-ship-it/class.git para descargar el repositorio
   cd api para poder ingresar a la carpeta del proyecto

2. Debemos crear el entorno virtual el cual almacenará el entorno virtual del proyecto con el comando: python -m venv .env
   
3. Luego de crear el entorno virtual lo debemos activar con el comando .\env\Scripts\Activate.ps1
4. Ahora las dependencias se deben instalar con el comando pip install flask
5. Ejecutar la aplicación
   Para ejecutar el programa debemos usar el comando python app.py
   la terminal deberá arrojarnos un mensaje el cual seleccionaremos con control y click y correrá, el mensaje es similar a http://127.0.0.1:5000


La terminal deberá estar abierta para realizar las pruebas desde Postman

Las pruebas en Postman con los endpoints se utilizara el URL obtenido anteriormente http:http://127.0.0.1:5000


GET: Nos ayuda a obtener la lista completa de los productos 

Abrimos Postman.

Creamos una nueva solicitud.

Seleccionamos el método GET.

Escribimos la URL: http://127.0.0.1:5000/api/productos

Presionamos el botón Send.

Postman mostrará la información de los productos registrados.


POST: Nos ayuda a crear o agregar un nuevo producto 

Abrimos una nueva solicitud en Postman.

Seleccionamos el método POST.

Escribimos la URL: http://127.0.0.1:5000/api/productos

Seleccionamos la pestaña Body.

Seleccionamos raw.

Seleccionamos JSON como tipo de contenido.

Escribimos los datos correspondientes al nuevo producto.

Presionamos Send.

La API procesará la información y creará el nuevo producto.

Ejemplo de la solicitud

{

    "nombre": "Laptop",
    
    "precio": 1200
}



PUT:Nos ayuda a modificar la información de un producto que ya se encuentra registrado 

Abrimos una nueva solicitud en Postman.

Seleccionamos el método PUT.

Escribimos la URL: http://127.0.0.1:5000/productos/3

Seleccionamos Body.

Seleccionamos raw.

Seleccionamos JSON.

Escribimos la nueva información del producto.

Presionamos Send.

La API actualizará la información del producto.

Ejemplo de la solicitud

{

    "id":2, 
    
    "nombre": "Mouse",
    
        "precio": 25

}


DELETE: Nos ayuda a eliminar un producto registrado

Abrimos una nueva solicitud en Postman.

Seleccionamos el método DELETE.

Escribimos la URL: http://127.0.0.1:5000/productos/2

Presionamos Send.


Ahora a continuación realizaremos los pasos para subirlo a la nube
1. Ahora tenemos que abrir Render.com y conectarla con github
2. En la terminal Visual Code ponemos el comando pip install gunicorn el cual es el que pone nuestro API de Flask en producción dentro de Render.com
3. Luego en la terminal debemos poner el comando pip freeze > requirements.txt
   actualizamos el github
usamos el paso a paso del git git add . git commit -m "Actualización" git push

Ingresamos a render
entramos a la pagina de render e iniciamos sesion con github creamos un new web service conectamos con nuestro repositorio en el Start Command ponemos gunicorn app:app y le damos deploy web service

creacion del web server
si todo sale bien y lo hicimos de manera correcta se debería observar que: El repositorio fue descargado. Las dependencias fueron instaladas. El build terminó correctamente. La aplicación inició. El servicio quedó disponible.

Obtener la URL de la aplicación
Una vez finalizado correctamente el despliegue, Render proporciona una URL pública bajo el dominio: https://nombre-del-servicio.onrender.com Los Web Services de Render reciben automáticamente un subdominio onrender.com. También es posible configurar posteriormente un dominio propio.

Verificar la aplicación
Abrir la URL proporcionada por Render: https://nombre-del-servicio.onrender.com y comprobar: La página carga correctamente. Los endpoints de la API responden. El frontend puede comunicarse con el backend. La conexión con la base de datos funciona. Las variables de entorno están disponibles. No aparecen errores en los logs. Si se trata de una API, también se pueden probar endpoints como: GET /api/health en nuestro caso seria: https://class-wfze.onrender.com/ y listo, compruebas ponindo lops ends del get, post, put and get y todo deberia funcionar correctamente
<img width="639" height="419" alt="image" src="https://github.com/user-attachments/assets/92038c80-9c36-45bf-a0b1-807ba1d6af85" />
<img width="1878" height="978" alt="Captura de pantalla 2026-09-09 135727" src="https://github.com/user-attachments/assets/23c706c4-94a1-4ec6-916c-cdd034e8bb4e" />
