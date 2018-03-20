FROM debian:jessie

#Pour n'avoir aucune question auquel on ne pourrait répondre.
ENV DEBIAN_FRONTEND noninteractive


# Télecharge et install tous les paquest et dépendances nécéssaires.
RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install sudo -y
RUN apt-get install curl -y
RUN sudo apt-get install curl python-software-properties -y
RUN sudo apt-get install nodejs -y
RUN curl -sL https://deb.nodesource.com/setup_9.x | sudo bash -
RUN sudo npm install -g coinmon


CMD coinmon -c eur

#USAGE
# docker build -t coinvalue .
# docker run -it coinvalue
