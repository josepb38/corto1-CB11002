# Usa una imagen base de OpenJDK 17
FROM openjdk:17

# Establece el directorio de trabajo en el contenedor
WORKDIR /app

# Copia solo los archivos esenciales del proyecto
COPY mvnw pom.xml ./
COPY .mvn .mvn
COPY src src

# Da permisos de ejecución a Maven Wrapper
RUN chmod +x mvnw

# Compila la aplicación dentro del contenedor
RUN ./mvnw clean package -DskipTests

# Expone el puerto en el que correrá la aplicación
EXPOSE 8080

# Ejecuta la aplicación asegurando el nombre correcto del JAR
CMD ["java", "-jar", "target/corto1-0.0.1-SNAPSHOT.jar"]
