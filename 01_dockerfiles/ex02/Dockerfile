FROM ruby:2.3.4

# Mise à jour et installation des dépendances
RUN apt-get update -y
RUN apt-get upgrade -y
RUN gem install rails
RUN apt-get install sqlite3 -y

# Ports
ONBUILD EXPOSE 3000

# Copy de l'app dans le conaineur
ONBUILD COPY . /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install

# Migration DB
ONBUILD RUN rails db:migrate
ONBUILD RUN rails db:seed

#USAGE

#docker build -t ft-rails .
#docker build -t main -f start.Dockerfile .
#docker run -it -p 3000:3000 main
