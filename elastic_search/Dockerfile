FROM --platform=linux/amd64 ubuntu:latest

# 설치 시 사용자 입력 방지 설정
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get install
RUN apt-get update
RUN apt-get install wget -y sudo
RUN apt-get install net-tools -y sudo

RUN useradd -ms /bin/bash elastic
USER elastic
WORKDIR /home/elastic

RUN wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-8.4.2-linux-x86_64.tar.gz
RUN tar zxvf elasticsearch-8.4.2-linux-x86_64.tar.gz

RUN ln -s ./elasticsearch-8.4.2 ./elastic

COPY ./config/elasticsearch.yml ./elastic/config/elasticsearch.yml

RUN sed -i '/-Xms[0-9]g/c\-Xms2g' ./elastic/config/jvm.options
RUN sed -i '/-Xmx[0-9]g/c\-Xmx2g' ./elastic/config/jvm.options

RUN sed -i 's/enabled: true/enabled: false/' ./elastic/config/elasticsearch.yml

EXPOSE 9200
EXPOSE 9300
CMD ["./elastic/bin/elasticsearch"]