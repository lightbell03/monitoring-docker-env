FROM prom/prometheus

COPY ./config/prometheus.yaml /etc/prometheus/prometheus.yaml

EXPOSE 9090

ENTRYPOINT [ "/bin/prometheus" ]
CMD [ "--config.file=/etc/prometheus/prometheus.yaml", "--web.enable-remote-write-receiver", "--storage.tsdb.retention.time=1m" ]