FROM ubuntu:16.04

# Port serveur minecraft
EXPOSE 25565

# Installation des dépendances
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install default-jdk -y
RUN apt-get install wget -y

# Creation d'un dossier minecraft
RUN mkdir minecraft
RUN cd minecraft

# Téléchargement de l'archive serveur minecraft
RUN wget https://s3.amazonaws.com/Minecraft.Download/versions/1.12.2/minecraft_server.1.12.2.jar

# Accepte End User License Agreement
RUN echo "eula=true" > eula.txt

CMD java -Xmx1024M -Xms1024M -jar minecraft_server.1.12.2.jar nogui

#USAGE

#docker build -t dockercraft .
#docker run -d -p 25565:25565 dockercraft
