FROM debian:9

# Téléchargement, MAJ et installation des paquets indispensables
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install vim wget curl git zsh gcc valgrind -y

# Instalation de OMZ et Sublivim
RUN curl -L http://install.ohmyz.sh | sh
RUN curl https://raw.githubusercontent.com/reversTeam/Sublivim/master/installer.sh | sh

# Creation de l'espace de travail
RUN cd home && mkdir WORKSPACE && cd WORKSPACE
WORKDIR /home/WORKSPACE

#Téléchargement des repos de travail
RUN git clone https://gde-pass:***@github.com/gde-pass/gnl.git
RUN git clone https://gde-pass:***@github.com/gde-pass/init.git
RUN git clone https://gde-pass:***@github.com/gde-pass/docker-1.git
RUN git clone https://gde-pass:***@github.com/gde-pass/libft.git

ENTRYPOINT ["zsh"]
