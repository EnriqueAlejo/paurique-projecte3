FROM ubuntu:22.10

RUN apt-get update && \
	apt-get install -y apache2 openssl supervisor && \
	mkdir -p /var/lock/apache2 /var/run/apache2 && \
	rm -rf /var/lib/apt/lists/*

RUN ln -s /etc/apache2/sites-available/default-ssl.conf /etc/apache2/sites-enabled/default-ssl.conf

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

VOLUME ["/var/log/apache2"]

EXPOSE 443a

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/supervisord.conf"]
CMD ["sh", "-c", "service apache2 start ; tail -f /dev/null"]