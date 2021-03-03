# Base images 基础镜像
FROM csighub.tencentyun.com/official/tlinux-2.2-base
#FROM 9.30.0.98:5000/baseimage/tlinux-64bit-v2.2-gcc4.8.5.20170926:2.00


# 环境初始化
# 配置代理
# 修改yum源
# 安装cmake3和gcc7.3
# 安装bazel1.1.0
RUN rpm -Uvh --replacepkgs https://mirrors.tencent.com/tlinux/rpm/tlinux-release-2-11.tl2.x86_64.rpm \
    && yum clean all \
    && yum makecache \
    && yum install -y cmake3 \
    && ln -s /usr/bin/cmake3 /usr/bin/cmake \
    && yum --enablerepo=tlinux-testing install -y tlinux-release-gcc-update \
    && yum remove -y tlinux12-compat compat-gcc-44-c++ \
    && yum update -y gcc \
    && yum install -y curl-devel \
    && yum install -y mysql-devel \
    && yum install -y gperftools \
    && yum install -y gperftools-devel \
    && yum install -y openssl \
    && yum install -y openssl-devel \

WORKDIR /

EXPOSE 36000
