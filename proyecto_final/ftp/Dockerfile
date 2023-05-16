FROM ubuntu:latest
RUN apt-get update && \
    apt-get install -y vsftpd
    
COPY vsftpd.conf /etc/vsftpd.conf

EXPOSE 21

CMD ["/usr/sbin/vsftpd", "/etc/vsftpd.conf", "-obackground=NO"]
