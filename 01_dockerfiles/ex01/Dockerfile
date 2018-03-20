# Image de base
FROM debian:9

ENV DEBIAN_FRONTEND noninteractive

# MAJ des paquets et installation de wget && bzip2;
RUN apt-get update -y && apt-get upgrade -y \
&& apt-get install wget -y \
&& apt-get install bzip2 -y

# Ajout utilisateur TS
RUN useradd teamspeak
CMD /home/teamspeak

# Telechargement du clien TS et Extraction du client
RUN wget http://dl.4players.de/ts/releases/3.0.12.4/teamspeak3-server_linux_amd64-3.0.12.4.tar.bz2
RUN tar xvfj teamspeak3-server_linux_amd64-3.0.12.4.tar.bz2

#Suppresion des packages useless et archive de bzip2
RUN apt-get remove bzip2 wget -y \
&& rm -rf teamspeak3-server_linux_amd64-3.0.12.4.tar.bz2

# Ouverture des ports
EXPOSE 9987/udp 10011 30033 41144

# Copie du .ini dans le dossier approprié.
WORKDIR teamspeak3-server_linux_amd64
COPY ts3server.ini /home/teamspeak/teamspeak3-server_linux_amd64/ts3server.ini

#Connexion en tant que USER teamspeak
USER teamspeak

#Execution du client TS
ENTRYPOINT [ "sh" , "ts3server_minimal_runscript.sh", "inifile=ts3server.ini" ]

# Build docker image with:
# docker build -t TS path/to/Dockerfile

# Then start the dockerised image with:
# docker run -it --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 -p 41144:41144 TS
