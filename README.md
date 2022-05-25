# Base de Datos. Unidad 5 actividad complementaria 2
### 1) Instalación de Java y Maven
En Windows 10 deberás instalar Java 15 y Maven

Java

https://download.java.net/java/GA/jdk15.0.1/51f4f36ad4ef43e39d0dfdbaf6549e32/9/GPL/openjdk-15.0.1_windows-x64_bin.zip

Maven

https://downloads.apache.org/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip

Deberás descomprimir cada archivo en una ubicación de tu elección y crear 
las variables de ambiente JAVA_HOME y MAVEN_HOME como se muestra en estas imágenes.
Las rutas deberán ser modificadas a tu entorno.

![image](https://user-images.githubusercontent.com/50935905/170385270-2783d9c6-c554-43a8-8fa1-1f197a79aa9d.png)

![image](https://user-images.githubusercontent.com/50935905/170385292-8b50de96-bb5d-45e9-b9e7-c79ebc0c7151.png)

Se deberá modificar la variable path y agregar las rutas %JAVA_HOME%/bin y %MAVEN_HOME%/bin

![image](https://user-images.githubusercontent.com/50935905/170385311-429fab51-d6e6-4ca4-b2da-a7a9d2717189.png)

Para comprobar que se ha realizado correctamente la instalación, en una consola de PowerShell o Terminal,
teclear
```
java -version
```
y
```
mvn --version
```

La salida de cada comando deberá ser similar a la siguiente imagen
![CONSOLA](./images/consola.png "CONSOLA")

### 2) Descarga del proyecto

Deberás descarga el proyecto en zip de https://github.com/tiempor3al/proyecto-api, y descomprimirlo  en la ubicación de tu elección.

![image](https://user-images.githubusercontent.com/50935905/170385348-ce1b860f-9143-4430-9d4b-1f772730f1cb.png)
  
### 3) Modificación de las credenciales de la base de datos

Para que el proyecto se conecte a la base de datos que tienen instalada en su equipo, deberán modificar el archivo application.properties 
que se encuentra en /src/main/resources con los datos correspondientes a su base de datos:

```
quarkus.datasource.username = fca
quarkus.datasource.password = fca01
quarkus.datasource.jdbc.url = jdbc:mysql://192.168.1.112:33700/fca
```

Para la url, la sintaxis es
```
jdbc:mysql://<dirección_ip>:<puerto>/<nombre_de_la_base>
```
Por ejemplo para conectarse a la base de datos "prueba" en localhost, la sintáxis 
de la url será:
```
jdbc:mysql://localhost:3306/prueba
```
Nota: el puerto 3306 es el estándar para MariaDB / MySQL

![image](https://user-images.githubusercontent.com/50935905/170385375-a16b27a1-a44a-4723-8d59-a5579190251b.png)


### 4) Compilación del proyecto

En PowerShell o Terminal, navegar al directorio donde se descargó el proyecto y ejecutar el comando:

```
./mvnw.cmd quarkus:dev
```

Este comando descargará las librerías requeridas para el proyecto, y ejecutará la aplicación Web en modo "desarrollo" en el puerto 8090.

![image](https://user-images.githubusercontent.com/50935905/170385421-52b81cd3-f16a-42b2-b390-3c71717aec14.png)

El modo "desarrollo" habilita la opción "hot reload". Es decir, se pueden modificar los archivos y se recompilaran mientras se ejecuta la aplicación.

5) Actividades
a) Ejecutar la aplicación y navegar a http://localhost:8090 en el navegador de tu elección.
![image](https://user-images.githubusercontent.com/50935905/170385621-2cb16ce6-6686-4073-8d18-d962ae059b4a.png)

b) Navegar al explorador de Swagger integrado, con http://localhost:8090/docs
![image](https://user-images.githubusercontent.com/50935905/170385658-cfc951c7-839d-4bf3-b208-972d3a21aa32.png)


