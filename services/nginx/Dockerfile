FROM nginx:1.29.5

RUN apt-get update && \
    apt-get install -y \
    nano \
    curl && \
    apt-get clean && \
    rm -fr /var/lib/apt/lists/*

RUN mkdir -p /etc/nginx/dhparam
RUN curl -o /etc/nginx/dhparam/dhparam https://ssl-config.mozilla.org/ffdhe2048.txt || { echo "Failed to download ssl-config.mozilla.org file"; exit 1; }

RUN mkdir -p /var/www/default
COPY /services/nginx/index.html /var/www/default

RUN mkdir -p /etc/ssl/flor.ru

WORKDIR /var/www/