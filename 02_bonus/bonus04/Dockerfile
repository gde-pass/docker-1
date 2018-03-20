FROM debian:8

ENV DEBIAN_FRONTEND noninteractive

# Ports
EXPOSE 28015
EXPOSE 28016

# Installation des dépendances
RUN apt-get update -y && apt-get upgrade -y && apt-get install sudo
RUN sudo dpkg --add-architecture i386 
RUN sudo apt-get install mailutils postfix curl wget file gzip bzip2 bsdmainutils python util-linux tmux lib32gcc1 unzip binutils bc lib32z1 -y

# Ajout d'un utilisateur
RUN adduser rustserver --disabled-password --gecos GECOS
RUN su - rustserver
WORKDIR /home/rustserver

# Récupération du serveur
RUN su - rustserver -c "wget https://gameservermanagers.com/dl/rustserver"

# On rend le script exécutable et on instal le serveur
RUN chmod +x rustserver
RUN su - rustserver -c "yes | ./rustserver install"

# Mise à jour du serveur (Optionnel)
#RUN ./rustserver force-update

CMD su - rustserver -c "./rustserver start"

# Build avec :
# docker build -t dockerrust .

# Lancer avec :
# docker run -d -p 28015:28015 -p 28016:28016 --name dockerrust dockerrust
