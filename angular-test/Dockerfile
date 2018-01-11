FROM vonbraunlabs/angular:latest

RUN apk add --no-cache \
    python \
    build-base \
    openjdk8-jre-base \
    # chromium dependencies
    udev \
    ttf-freefont \
    chromium-chromedriver \
    chromium

ENV CHROME_BIN /usr/bin/chromium-browser