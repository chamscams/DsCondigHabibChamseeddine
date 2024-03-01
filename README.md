FROM ubuntu:20.04

# Mise à jour des packages et installation de OpenJDK 17
RUN apt-get update && \
    apt-get install -y openjdk-17-jdk

# Copie du fichier jar dans l'image Docker
COPY target/otlobtalka-0.0.1-SNAPSHOT.jar otlobtalka-0.0.1-SNAPSHOT.jar

# Exposition du port 8081
EXPOSE 8081

# Commande pour exécuter l'application Java
CMD ["java", "-jar", "otlobtalka-0.0.1-SNAPSHOT.jar"]
