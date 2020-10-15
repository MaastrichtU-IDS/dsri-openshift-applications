FROM jefferyb/code-server:latest

USER root

RUN apt-get install -y php php-xml php-json php-curl php-bz2 php-yaml php-dev php-symfony php-mbstring

RUN apt-get install -y yarn

RUN apt-get update && apt-get upgrade

RUN apt-get install gfortran build-essential -y

USER 10001