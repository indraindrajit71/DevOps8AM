FROM ubuntu

ENV TZ=Asia/Kolkata
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
ENV USER root
ENV PASS root

#USER root
RUN apt-get update && \
    apt-get install -y mysql-server-8.0
COPY my.cnf /etc/mysql/my.cnf
COPY start.sh start.sh
VOLUME ["/var/lib/mysql"]
CMD ["/start.sh"]
EXPOSE 3306
