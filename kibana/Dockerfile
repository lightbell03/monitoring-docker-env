FROM --platform=linux/amd64 ubuntu:latest

RUN apt-get install
RUN apt-get update
RUN apt-get install wget -y sudo

RUN useradd -ms /bin/bash kibana
USER kibana
WORKDIR /home/kibana

RUN wget https://artifacts.elastic.co/downloads/kibana/kibana-8.4.2-linux-x86_64.tar.gz
RUN tar zxvf kibana-8.4.2-linux-x86_64.tar.gz
RUN ln -s kibana-8.4.2 kibana

COPY ./config/kibana.yml ./kibana/config/kibana.yml

CMD [ "./kibana/bin/kibana" ]