# lab2distribuidos

README
1. Disponibilizar servicio de entorno analítico.
2. Integrantes:        Nicolas Alarcon 
                        Sandra Hernández
3.  Para realizar proyectos de investigación en los cuales trabajan un gran números de ingenieros es necesario que todos tengan acceso a los datos y avances se sus colegas de esta manera se lograría un avance mucho más eficiente del proyecto además de tener menos probabilidad de errores ya que los datos serán actualizados en “tiempo real”.  Por todo lo mencionado anteriormente se deben tener los servicios como la Base de datos, herramientas para procesamiento big data (spark), interfaz de pruebas de código (jupyter notebook) y el soporte para lenguajes de programación python y R en un servidor de AWS la cual brinda seguridad y accesibilidad de los datos a través de todo el mundo.


4. Habilitar un servidor de AWS el cual tenga todas las herramientas mencionadas anteriormente y que puedan ser accesadas por todos los ingenieros de un proyecto dado.


user : ubuntu
ip: 13.59.44.23
ssh -i "kpLab.pem" ubuntu@13.59.44.23
kplab.pem adjuntado




5.  a) Las principales barreras que se presentaron a la hora de realizar la actividad fueron la falta de conocimientos sobre las diferentes tecnologías a ocupar así como también el tiempo de creación de un cuenta en AWS, pero sobre todo la poca experiencia en el uso y manejo de las diferentes herramientas.
El tiempo dedicado al trabajo fue en gran medida a la comprensión y lectura de cómo funcionan y que son las diferentes tecnologías así como al tiempo para corregir los diferentes errores en la instalacion y configuracion de estas.




6. 


  

Jupyter notebook montado en el servidor


  

Ejecutando un  código python en jupyter.








  

                        Bucket S3 creado para la implementación


  

Spark ejecutando al el servidor


7. link: 


Introduciendo en el servidor el comando 
jupyter notebook --ip=0.0.0.0 --no-browser --port=8890
y percatandose que el puerto 8890 esté abierto en nuestro servidor. este se puede acceder mediante la ip publica del servidor (http://13.59.44.238:8890) 


8.
* Paso 1: Habilitar una máquina virtual al la nube en AWS.
   * Crear una cuenta en AWS
   * Solicitar el servicio EC2 para crear un MV
   * Generar la key-par para acceso a la máquina virtual: “kpLab.pem”
   * Crear una MV con sistema operativo ubuntu
* Paso 2: Instalar las diferentes tecnologías solicitadas S3, jupyter, spark, python y R.
   * Antes que todo se debe instalar java jdk: “sudo apt-get install default-jdk”
   * Instalar scala:                 “install scala”
   * Instalar git:                 “install git”
   * Descargar Spark:         “wget https://www-us.apache.org/dist/spark/spark-2.4.3/spark-2.4.3-bin-hadoop2.7.tgz”
   * Instalar Spark:         “sudo tar xvf spark-2.4.3-bin-hadoop2.7.tgz -C/usr/local”
   * Instalar Anaconda: esta posee múltiples herramientas entre las que se encuentra Júpiter: paso a paso para su instalación en el siguiente link: https://linuxize.com/post/how-to-install-anaconda-on-ubuntu-18-04/
   * Modificar archivo ~/.bashrc agregando al final de este lo siguiente:
export JAVA_HOME=/usr/lib/jvm/default-java  
export SBT_HOME=/usr/share/sbt-launcher-packaging/bin/sbt-launch.jar  
export SPARK_HOME=/usr/lib/spark
export PATH=$PATH:$JAVA_HOME/bin
export PATH=$PATH:$SBT_HOME/bin:$SPARK_HOME/bin:$SPARK_HOME/sbin
export PYSPARK_DRIVER_PYTHON=jupyter
export PYSPARK_DRIVER_PYTHON_OPTS='notebook'
export PYSPARK_PYTHON=python2.7
export PYTHONPATH=$SPARK_HOME/python:$PYTHONPATH
   * Crear un Buckets de S3 de acceso público
   * vincular S3 con spark.