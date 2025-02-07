# FROM otel/opentelemetry-collector

# COPY ./config/config.yaml /etc/otelcol/config.yaml

# EXPOSE 19100

# ENTRYPOINT [ "/otelcol" ]
# CMD [ "--config", "/etc/otelcol/config.yaml" ]

# FROM --platform=linux/amd64 ubuntu:latest

# RUN apt-get install
# RUN apt-get update -y

# # change work directory
# WORKDIR /home/ubuntu

# # install wget
# RUN apt-get install wget -y

# # install otel-collector
# RUN wget https://github.com/open-telemetry/opentelemetry-collector-releases/releases/download/v0.118.0/otelcol_0.118.0_linux_amd64.deb
# RUN dpkg -i otelcol_0.118.0_linux_amd64.deb

# # copy config file
# COPY ./config/config.yaml /etc/otelcol/config.yaml

# # run
# ENTRYPOINT [ "/usr/bin/otelcol" ]
# CMD [ "--config=/etc/otelcol/config.yaml" ]

FROM otel/opentelemetry-collector-contrib:latest

COPY ./config/config.yaml /etc/otelcol-contrib/config.yaml