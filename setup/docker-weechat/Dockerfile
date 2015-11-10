# Weechat for rasberry pi dockerfile

FROM resin/rpi-raspbian:jessie

RUN apt-get update && \
    apt-get install -y apt-transport-https=1.0.9.8.1 \
                       cpanminus=1.7014-1 \
                       make=4.0-8.1 \
                       gcc=4:4.9.2-2
RUN sudo apt-key adv --keyserver keys.gnupg.net --recv-keys 11E9DE8848F2B65222AA75B8D1820DB22A11534E && \
    sudo bash -c "echo 'deb https://weechat.org/raspbian jessie main' >/etc/apt/sources.list.d/weechat.list" && \
    sudo bash -c "echo 'deb-src https://weechat.org/raspbian jessie main' >>/etc/apt/sources.list.d/weechat.list" && \
    apt-get update && \
    apt-get install -y weechat-curses=1.3 weechat-plugins=1.3

RUN cpanm Encode~2.78

EXPOSE 8001

ENV LANG C.UTF-8
ENV TERM rxvt-unicode
ENV HOME /
ENV TZ US/Pacific

CMD weechat -r "\
/set relay.network.password \"$WEECHAT_PASSWORD\";\
/set logger.file.mask \"\$plugin.\$name.log\";\
/relay add weechat 8001;\
/script install socket_notify.rb;\
/script autoload socket_notify.rb;\
"
