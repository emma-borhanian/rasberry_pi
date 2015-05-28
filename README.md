# Personal setup/maintenance scripts for rasberry pi

1. http://blog.hypriot.com/getting-started-with-docker-on-your-arm-device
2. setup .env file:
    ```shell
    HOST=# device host

    USER_ROOT=root
    AUTHORIZED_KEYS_ROOT=# ssh public key for root user

    USER_COUNT=1

    USER_1=emma
    AUTHORIZED_KEYS_1=# ssh public key for user 1
    WEECHAT_PASSWORD_1=# weechat password for user 1
    WEECHAT_PORT_1=# weechat port for user 1
    ...
    ```
3. run `./bin/setup && ./bin/test`

# Dependencies

* on Mac OS, need a better xpath implementation, see https://github.com/concept-not-found/homebrew-tap

* Maintenance

* update image http://blog.hypriot.com/getting-started-with-docker-and-mac-on-the-raspberry-pi/
* update version numbers in `/setup/docker-weechat/Dockerfile`
* run `/bin/setup && ./bin/test` (idempotent)

# Reference

* https://github.com/diogomonica/docker-bench-security
* http://oleaass.com/installing-configuring-and-hardening-weechat-on-linux/
* https://www.debian.org/doc/manuals/securing-debian-howto/index.en.html
* http://www.shellcheck.net/
