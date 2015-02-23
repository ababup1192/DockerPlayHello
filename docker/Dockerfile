FROM dockerfile/java
MAINTAINER Mirai Watanabe <ababup1192@gmail.com>
EXPOSE 9000 50080
ADD files /
RUN \
 apt-get update && \
 apt-get install -y supervisor && \
 apt-get install python-setuptools && \
 easy_install superlance && \
 rm -rf /var/lib/apt/lists/* && \
 sed -i 's/^\(\[supervisord\]\)$/\1\nnodaemon=true/' /etc/supervisor/supervisord.conf
WORKDIR /etc/supervisor/conf.d
CMD ["supervisord", "-c",  "/etc/supervisor/supervisord.conf"]
