FROM registry.cn-hangzhou.aliyuncs.com/dragonwell/dragonwell8:8.4.4-GA_alpine_x86_64_8u262-b10_slim

MAINTAINER yutons <yuton.yao@qq.com>

# 更换Alpine源为mirrors.huaweicloud.com
RUN echo https://mirrors.huaweicloud.com/alpine/latest-stable/main > /etc/apk/repositories && \
    echo https://mirrors.huaweicloud.com/alpine/latest-stable/community >> /etc/apk/repositories
RUN apk update && apk upgrade

# 解决Docker部署dragonwell后无字体空指针异常
RUN set -xe && apk --no-cache add ttf-dejavu fontconfig

# 解决Docker dragonwell 容器时间与jdk时区不同问题(https://www.cnblogs.com/solooo/p/7832117.html)
ADD localtime /etc/
RUN echo "Asia/Shanghai" > /etc/timezone

