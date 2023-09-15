# MissingAlpinePackages
Missing alpine packages for apk add chromium-switchcraft

We have some packages, which need for install chromium-switchshader on alpine linux 3.18
For x86_64 architecture we need following packages:

https://dl-cdn.alpinelinux.org/alpine/v3.18/main/x86_64/gtk-update-icon-cache-3.24.38-r1.apk

https://dl-cdn.alpinelinux.org/alpine/v3.18/community/x86_64/xdg-utils-1.1.3-r4.apk

https://dl-cdn.alpinelinux.org/alpine/v3.18/community/x86_64/ffmpeg-libavcodec-6.0-r15.apk

https://dl-cdn.alpinelinux.org/alpine/v3.18/community/x86_64/ffmpeg-libavformat-6.0-r15.apk

Using this (previously downloaded) packages in dockerfile:

COPY ./apk/* /tmp/

RUN touch repo.list

RUN apk add --repositories-file=repo.list --allow-untrusted --no-network --no-cache /tmp/ca-certificates-20171114-r3.apk /tmp/libcurl-7.61.1-r1.apk /tmp/libssh2-1.8.0-r3.apk /tmp/nghttp2-libs-1.32.0-r0.apk /tmp/curl-7.61.1-r1.apk

