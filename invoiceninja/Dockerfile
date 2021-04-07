FROM invoiceninja/invoiceninja:alpine-4

USER root

RUN apk --no-cache add nginx supervisor && \
    rm /etc/nginx/conf.d/default.conf && \
    chown -R invoiceninja:invoiceninja /var/lib/nginx && \
    chown -R invoiceninja:invoiceninja /var/log/nginx && \
    chown -R invoiceninja:invoiceninja /usr/lib/nginx && \
    touch /run/nginx.pid && \
    chown invoiceninja:invoiceninja /run/nginx.pid

COPY nginx.conf /etc/nginx/nginx.conf

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

USER invoiceninja

WORKDIR /var/www/app

EXPOSE 80

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]
