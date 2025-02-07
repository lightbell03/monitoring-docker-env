FROM --platform=linux/amd64 ubuntu:latest

# ENV DOCKER_VERSION=5:27.5.1-1~ubuntu.24.04~noble

RUN apt-get update 
RUN apt-get install -y apt-transport-https ca-certificates curl gnupg lsb-release

# Docker GPG Key 추가
RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -

# Docker 공식 저장소 추가
# RUN echo "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list

RUN echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Docker 설치
RUN apt-get update 
RUN apt-get install -y docker-ce docker-ce-cli containerd.io

# Docker 데몬 실행을 위한 디렉토리 설정
RUN mkdir -p /var/lib/docker /var/run/docker

# privileged 모드 필요 없이 실행할 수 있도록 dockerd를 background에서 실행
CMD ["dockerd", "--host=unix:///var/run/docker.sock"]