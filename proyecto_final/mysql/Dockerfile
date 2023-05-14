# Utiliza una imagen base de Ubuntu
FROM ubuntu:latest

# Actualiza los paquetes del sistema e instala MySQL Server
RUN apt-get update && \
    apt-get install -y mysql-server && \
    rm -rf /var/lib/apt/lists/*

# Establece las variables de entorno para la configuración de MySQL
ENV MYSQL_DATABASE=taskhub
ENV MYSQL_USER=paurique
ENV MYSQL_PASSWORD=reyney15
ENV MYSQL_ROOT_PASSWORD=reyney15

# Copia el archivo SQL de inicialización a la carpeta de inicio de MySQL
COPY mydatabase.sql /docker-entrypoint-initdb.d/

# Expone el puerto 3306 para que pueda ser accesible desde el host
EXPOSE 3306

# Comando de inicio de MySQL cuando se ejecuta el contenedor
CMD ["mysqld"]