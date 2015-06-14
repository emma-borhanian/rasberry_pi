# Weechat for rasberry pi dockerfile

FROM resin/rpi-raspbian:wheezy

RUN apt-get update && \
    apt-get install -y apt-transport-https=0.9.7.9+rpi1+deb7u7 \
                       cpanminus=1.5015-1
RUN echo 'deb https://weechat.org/raspbian wheezy main' >/etc/apt/sources.list.d/weechat.list && \
    apt-get update && \
    # need --force-yes because weechat packages are not authenticated
    apt-get install -y --force-yes weechat-curses=1.2 weechat-plugins=1.2

RUN cpanm Encode~1.9801

EXPOSE 8001

ENV LANG C.UTF-8
ENV TERM rxvt-unicode
ENV HOME /
ENV TZ US/Pacific

CMD weechat -r "/set relay.network.password \"$WEECHAT_PASSWORD\";/set logger.file.mask \"\$plugin.\$name.log\";/relay add weechat 8001"
