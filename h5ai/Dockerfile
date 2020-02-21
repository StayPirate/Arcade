FROM tuxmealux/alpine-nginx-php7:latest

LABEL maintainer="Gianluca Gabrielli" mail="tuxmealux+dockerhub@protonmail.com"
LABEL description="h5ai file lister"
LABEL website="https://larsjung.de/h5ai/"

ENV H5AI_VERS=0.29.2

WORKDIR /www

RUN wget https://release.larsjung.de/h5ai/h5ai-${H5AI_VERS}.zip && \
    unzip h5ai-${H5AI_VERS}.zip && \
    rm h5ai-${H5AI_VERS}.zip && \
    chown -R nginx:www-data /www && \
    sed -i "s|index.html index.htm index.php;|index.html index.htm index.php /_h5ai/public/index.php;|g" /etc/nginx/nginx.conf && \
    mkdir /www/files && \
    \
    ###### Install h5ai dependecies ######
    # You can check dependencies status at
    # http://CONTAINER_IP/_h5ai/public/
    # Default password is empty
    apk update && \
    apk add --no-cache \
        zip \
        ffmpeg \
        imagemagick

COPY --chown=nginx:www-data options.json /www/_h5ai/private/conf/