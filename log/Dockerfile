FROM --platform=linux/amd64 ubuntu:latest

COPY ./script/log_generator.sh /
RUN mkdir /script

CMD [ "sh", "/log_generator.sh", "&" ]