# bundle the entire stack with the command: docker build -t myimage .
# docker run -it --rm -v /var/run/docker.sock:/var/run/docker.sock:ro -v docker-compose.yml:/docker-compose.yml myimage   
ARG DOCKER_VERSION=20.10.12
FROM docker:${DOCKER_VERSION}

WORKDIR /the/workdir/path
ARG COMPOSE_VERSION=2.2.3
RUN mkdir -p /root/.docker/cli-plugins \
 && wget https://github.com/docker/compose/releases/download/v${COMPOSE_VERSION}/docker-compose-linux-x86_64 -O /root/.docker/cli-plugins/docker-compose \
 && chmod u+x /root/.docker/cli-plugins/docker-compose
 
ENV PATH="/root/.docker/cli-plugins:${PATH}"

COPY docker-compose.yml /the/workdir/path/docker-compose.yml
COPY envs /the/workdir/path/envs

ENTRYPOINT [ "docker-compose", "-f","/the/workdir/path/docker-compose.yml", "up"]