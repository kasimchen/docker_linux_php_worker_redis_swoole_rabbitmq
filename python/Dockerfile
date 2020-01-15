#
#--------------------------------------------------------------------------
# Image Setup
#--------------------------------------------------------------------------
#
# To edit the 'php-fpm' base Image, visit its repository on Github
#    https://github.com/Laradock/php-fpm
#
# To change its version, see the available Tags on the Docker Hub:
#    https://hub.docker.com/r/laradock/php-fpm/tags/
#
# Note: Base Image name format {image-tag}-{php-version}
#

FROM registry.cn-beijing.aliyuncs.com/xxf/python3:1

MAINTAINER CHENHUAN <chenhuan@liaosearch.com>

COPY ./sources.list.stretch /etc/apt/sources.list

ENV TZ Asia/Shanghai

WORKDIR /usr/src/app

COPY ./requirements.txt .

RUN sudo apt-get update \
&&apt-get -y install python-devel

RUN pip install --no-cache-dir -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple/

COPY . .

EXPOSE 5010

WORKDIR /usr/src/app/cli

ENTRYPOINT [ "sh", "start.sh" ]