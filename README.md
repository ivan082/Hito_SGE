Proyecto de Encuestas sobre Consumo de Alcohol

Este proyecto tiene como objetivo gestionar encuestas sobre el consumo de alcohol y su impacto en la salud. A continuación, te explico cómo puedes configurar y ejecutar la aplicación en tu máquina.

Requisitos

1. Instalar Python

Este proyecto está desarrollado en Python, así que primero necesitas tener Python instalado en tu computadora. Si no lo tienes, puedes descargarlo desde la página oficial: [Descargar Python](https://www.python.org/downloads/). Asegúrate de tener la versión 3.x de Python instalada.

Para verificar que Python está instalado correctamente, abre una terminal (o la línea de comandos) y ejecuta el siguiente comando:

python --version

Esto debería mostrarte la versión de Python que tienes instalada.

2. Instalar Tkinter

Tkinter es una librería de Python que se usa para crear la interfaz gráfica de usuario (GUI) de nuestra aplicación. En la mayoría de las instalaciones de Python, Tkinter ya está incluido. Para asegurarte de que lo tienes, puedes probar el siguiente comando en la terminal:

python -m tkinter

Si no se abre una pequeña ventana, significa que no tienes Tkinter instalado. En ese caso, puedes instalarlo dependiendo de tu sistema operativo:

- Windows: Tkinter debería venir preinstalado con Python.
- Linux: Usa el siguiente comando para instalarlo:

  sudo apt-get install python3-tk

3. Instalar MySQL

Este proyecto usa MySQL para almacenar las respuestas de las encuestas. Si no tienes MySQL instalado, sigue estos pasos:

1. Descarga MySQL desde su sitio oficial: [MySQL Downloads](https://dev.mysql.com/downloads/installer/).
2. Durante la instalación, asegúrate de seleccionar las opciones de "Servidor MySQL" y "MySQL Workbench".
3. Asegúrate de configurar una contraseña para el usuario `root` y guárdala porque la necesitarás más adelante.

Una vez instalado, puedes acceder a MySQL a través de la terminal o MySQL Workbench.

4. Instalar MySQL Connector para Python

Para conectar Python con MySQL, necesitamos instalar el conector de MySQL. Abre la terminal y ejecuta este comando:

pip install mysql-connector-python

Esto instalará el conector necesario para que la aplicación se comunique con la base de datos.

5. Instalar Pandas y Matplotlib

Este proyecto también usa `pandas` para manejar los datos y `matplotlib` para generar gráficos. Para instalarlos, ejecuta los siguientes comandos:

pip install pandas
pip install matplotlib

Estas librerías te permitirán visualizar los resultados de las encuestas en forma de gráficos.

Conectar la Aplicación con MySQL

Para que la aplicación se conecte correctamente a MySQL, necesitas editar los detalles de la conexión en el archivo de Python. La función `conectar()` maneja la conexión. Aquí tienes un ejemplo de cómo debe lucir:

def conectar():
    return mysql.connector.connect(
        host="localhost",  # Generalmente 'localhost'
        user="tu_usuario",  # El usuario que configuraste en MySQL
        password="tu_contraseña",  # La contraseña que elegiste
        database="encuestas_db"  # El nombre de la base de datos
    )

Reemplaza `"tu_usuario"` y `"tu_contraseña"` por los datos correctos. Si no tienes la base de datos `encuestas_db` aún, sigue el paso a continuación.

Crear la Base de Datos y la Tabla

1. Abre MySQL Workbench o usa la terminal para acceder a MySQL:

   mysql -u root -p

2. Introduce la contraseña que configuraste durante la instalación de MySQL.

3. Crea una base de datos para las encuestas:

   CREATE DATABASE encuestas_db;

4. Usa esa base de datos:

   USE encuestas_db;

5. Crea la tabla donde se almacenarán las encuestas:

   CREATE TABLE ENCUESTA (
       idEncuesta INT AUTO_INCREMENT PRIMARY KEY,
       edad INT,
       sexo VARCHAR(10),
       bebidasSemana INT,
       cervezasSemana INT
   );

Esto configura la base de datos para almacenar los resultados de las encuestas.

Ejecutar el Proyecto

Sigue estos pasos para ejecutar la aplicación en tu computadora:

1. Abre la terminal y navega hasta la carpeta donde guardaste los archivos del proyecto. Usa el comando `cd` para ir a la carpeta correcta:

   cd ruta/del/proyecto

2. Ejecuta el archivo Python que contiene la aplicación:

   python mi_aplicacion.py

Esto abrirá la interfaz gráfica de la aplicación.

Uso de la Aplicación

Una vez que la aplicación esté ejecutándose, podrás realizar las siguientes operaciones:

Crear Encuestas

- Ingresa los datos de la encuesta (edad, sexo, bebidas y cervezas por semana).
- Haz clic en "Crear Encuesta" para guardar los datos en la base de datos.

Ver Encuestas

- Haz clic en "Ver Encuestas" para ver todas las encuestas guardadas en la base de datos.

Actualizar Encuestas

- Selecciona una encuesta de la lista.
- Cambia los valores que deseas actualizar y haz clic en "Actualizar Encuesta" para guardar los cambios.

Eliminar Encuestas

- Selecciona una encuesta de la lista y haz clic en "Eliminar Encuesta" para eliminarla de la base de datos.

Ver Gráficos

- Haz clic en "Generar Gráfico" para ver un gráfico con los datos de las encuestas, como el consumo de bebidas o cervezas por semana.

Conclusión

Con estos pasos, deberías poder ejecutar y usar la aplicación sin problemas. Si encuentras algún error o tienes dudas, revisa los mensajes de la consola o consulta el código para más detalles. ¡Espero que encuentres útil esta guía y que puedas aprovechar la aplicación para tus proyectos!
