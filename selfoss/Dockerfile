FROM jenserat/selfoss

RUN apt-get update && apt-get install -y --no-install-recommends \
  cron \
  && rm -rf /var/lib/apt/lists/*

RUN echo "*/15 *  * * *  root  curl -s http://localhost/update\n" >> /etc/crontab

COPY entrypoint.sh /
ENTRYPOINT ["cron && apache2-foreground"]
