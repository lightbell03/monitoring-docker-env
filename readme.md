# OpenTelemetry Collector 를 사용한 모니터링 환경을 docker 로 구축하여 테스트

## 참고

fluentd 의 사용을 위해 fluentd container 로 접속해(docker exec -it fluentd /bin/bash) <br />
`sh /script/log_generator.sh &` 명령으로 더미 로그 파일을 만들어주고 exit 해야 합니다.
