# Practica servidor de base de datos con archivo y,l y docker compose
## Informe de dos contenedores creados con archivo yml y docker compose
## 2. Tiempo : 50 minutos
## 3. Fundamentos:

 ### 3.1 Docker
 Docker es una plataforma para poder virtualizar y empaquetar aplicaciones con dependencias en contenedores, que a diferencia de las máquinas virtuales comparten el mismo núcleo del sistema.

 - Imagen -
 Una imagen es un conjunto de instrucciones que describe cómo se debe configurar el contenedor.
  - YAML-
  Los archivos yml son una forma de organizar información de una serie de  pasos para que otras personas la puedan interpretar de una mejor manera. 
## 4. Conocimientos previos.
   
Para realizar esta practica debemos tener conocimientos es:
1. Conocimientos de Docker.
2. Descargado Docker.
3. Uso de la Terminal.
4. Navegador Web.
5. Acceso a Internet.
6. Comprensión de Puertos.
7. Conocimiento de Documentación de Docker.

## 5. Objetivos a alcanzar
   
- Esta practica busca entender como se puede crear dos contenedores con distintas caracteristicas y conectarlos entre si medieante una red.
## 6. Equipo necesario:
  
- Computador.
- Navegador web.
- Docker instalado.

## 7. Material de apoyo.
   
- Documentacion de docker.
- Guia de asignatura.
- Imágnes de docker.
  
## 8. Procedimiento

1. Creacion de los contenedores
  Primero creamos dos contenedores uno que servira como base de datos y otro que va a consumir esta base de datos, para esto ejecuamos los siguientes comandos:
run -d --name database -e POSTGRES_PASSWORD=admin -p 5432:542 postgres
run -d --name pgadmin -p 8089 -e PGADMIN_DEFAULT_EMAIL=kanaula@sudamericano.edu.ec -e PGADMIN_DEFAULT_PASSWORD=admin dpage/pgadmin4
  Con el primer comando logramos crear un contenedor que servira como base de datos con el puerto de 5432.
  Con el segundo contenedor tenemos uno que va a consumir la base de datos de primer contenedor, este contenedor tiene el puerto 8089. En este caso se dio un error ya que el puerto por defecto deberia ser el 8090, pero se coloco uno diferente, esto unicamente va a varias solo en la configuracion por defecto o cundo queremos conectarnos a el debemos tener en cuenta este punto.

Luego de tener creados los contenedores pasamos a crear la red para poder conectar los dos contenedores con el comando:
docker network create ..attchable kanaula

Una vez creados los contenedores y la red pasamos a la interfaz grafica del contenedor de la base de datos mediante la url de localhost con el puerto de este contenedor, que en este caso es e puerto 5432.
Dentro de la interfaz creamos la conexion con los datos que tenemos del contenedor pgadmin.

## 9. Resultados esperados:
    
Con estos pasos y estos comandos logramos tener dos contenedores y una red con lo que podemos conectar estos dos contenedores mediante esta red que tenemos, cabe recalcar que todo esto se forma de manera local o en otras paabras solamente dentro de la computadora.
