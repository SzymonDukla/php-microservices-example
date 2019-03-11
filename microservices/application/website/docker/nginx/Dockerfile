FROM nginx:latest

COPY ./nginx.conf /etc/nginx/
COPY ./conf.d/service.conf /etc/nginx/sites-available/

RUN mkdir -p /etc/nginx/sites-enabled/ \ 
    ln -s /etc/nginx/sites-available/service.conf /etc/nginx/sites-enabled/service.conf \
    && rm /etc/nginx/conf.d/default.conf

RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf

RUN usermod -u 33 www-data

CMD ["nginx"]

EXPOSE 80
EXPOSE 443
