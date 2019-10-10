FROM node:9.2.1-alpine

# Install base packages and set timezone ShangHai
RUN apk update && apk add bash tzdata \
    && cp -r -f /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

RUN MKDIR app && CD app && npm install --registry=https://registry.npm.taobao.org
