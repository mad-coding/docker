FROM python:2.7-alpine3.9

COPY docker-entrypoint.sh healthcheck.sh aria2c aria2.conf supervisord.conf /

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.tuna.tsinghua.edu.cn/g' /etc/apk/repositories && \
    apk add --no-cache \
        vim \
        git \
        gcc \
        bash \
        lsof \
        dcron \
        tzdata \
        musl-dev \
        supervisor && \
    mv /aria2c /usr/local/bin && \
    git clone https://github.com/abbeyokgo/PyOne.git /etc/PyOne && \
    sed -n "1,`grep -n "}" /etc/PyOne/update.sh | tail -1 | cut -d: -f1`p" /etc/PyOne/update.sh > /update.sh && \
    chmod +x /docker-entrypoint.sh /healthcheck.sh /update.sh /usr/local/bin/aria2c && \
    pip install -r /etc/PyOne/requirements.txt -i  https://pypi.douban.com/simple/

WORKDIR /root/PyOne
VOLUME [ "/data", "/root/PyOne" ]
ENTRYPOINT ["/docker-entrypoint.sh"]
