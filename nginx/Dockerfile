FROM ubuntu:latest

RUN apt-get update && apt-get install -y nginx

RUN rm /etc/nginx/sites-enabled/default

COPY ./nginx.conf /etc/nginx/nginx.conf

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]
