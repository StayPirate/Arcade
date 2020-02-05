FROM alpine

LABEL maintainer="Gianluca Gabrielli" mail="tuxmealux+dockerhub@protonmail.com"
LABEL description="rsync on Alpinelinux"
LABEL website="https://github.com/StayPirate/Arcade"

RUN apk add --no-cache rsync && \
    mkdir -p /mnt/{remote,local}

CMD ["sh"]
