FROM nginx:1.27.2-alpine-slim

RUN mkdir -p /usr/share/nginx/html/status
COPY index.html /usr/share/nginx/html/status/
RUN echo "server { \
    listen 80; \
    location /status { \
        alias /usr/share/nginx/html/status; \
        index index.html; \
    } \
}" > /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]