FROM ubuntu:20.04

RUN apt-get update && \
    apt-get install -y openssh-server supervisor && \
    mkdir -p /var/run/sshd /var/log/supervisor

COPY sshd_config /etc/ssh/
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 22

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/supervisord.conf"]
CMD ["sh", "-c", "service ssh start ; tail -f /dev/null"]