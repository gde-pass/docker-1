FROM debian

# Installation des dépendances
RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install git -y
RUN apt-get install make -y
RUN apt-get install gcc -y

# Récupération des sources de l'app
RUN git clone https://github.com/klange/nyancat.git

# Déplacement dans le répertoire de l'app
WORKDIR nyancat

# Make de l'app
RUN make && cd src

CMD ./src/nyancat

#USAGE
# docker build -t nyancat
# docker run -it nyancat
