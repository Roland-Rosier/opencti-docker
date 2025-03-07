# Use the DOCKER_MIRROR defined for the docker compose file
ARG DOCKER_MIRROR

# Example from:
# https://ourcodeworld.com/articles/read/2083/how-to-remove-redis-warning-on-docker-memory-overcommit-must-be-enabled
FROM ${DOCKER_MIRROR}redis:7.4.2

RUN apt update && apt install procps -y

WORKDIR /redis

# COPY empty-docker-entrypoint.sh /usr/local/bin/empty-docker-entrypoint.sh
# RUN chmod +x /usr/local/bin/empty-docker-entrypoint.sh
COPY docker-entrypoint.sh /usr/local/bin/docker-entrypoint.sh
RUN chmod +x /usr/local/bin/docker-entrypoint.sh

#RUN chmod +x /usr/local/bin/empty-docker-entrypoint.sh

COPY redis.conf /usr/local/etc/redis/redis.conf

# COPY init.sh ./

#RUN chmod +x init.sh

# Remove old entrypoint because we now want init.sh to start the server
#ENTRYPOINT [ "/usr/local/bin/empty-docker-entrypoint.sh" ]
