FROM debian

RUN apt-get update && apt-get dist-upgrade -y && apt-get install -y supervisor curl nginx vim

RUN curl -L https://github.com/kelseyhightower/confd/releases/download/v0.11.0/confd-0.11.0-linux-amd64 -o /usr/bin/confd
RUN chmod +x /usr/bin/confd

ADD confd/templates/ /etc/confd/templates/
ADD confd/conf.d/ /etc/confd/conf.d/

ADD supervisor/ /etc/supervisor/conf.d/

CMD ["supervisord","-n"]
