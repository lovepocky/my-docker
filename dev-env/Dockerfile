FROM ubuntu:16.10

RUN echo '\n\
deb http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse \n\
deb http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse \n\
deb http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse \n\
deb http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse \n\
##测试版源 \n\
deb http://mirrors.aliyun.com/ubuntu/ xenial-proposed main restricted universe multiverse \n\
# 源码\n\
deb-src http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse \n\
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse \n\
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse \n\
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse\n\
##测试版源\n\
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-proposed main restricted universe multiverse\n\
# Canonical 合作伙伴和附加\n\
deb http://archive.canonical.com/ubuntu/ xenial partner\n\
#deb http://extras.ubuntu.com/ubuntu/ xenial main\n\
\n'\
>> /etc/apt/sources.list


RUN cat /etc/apt/sources.list
RUN apt update

RUN apt install -y byobu
RUN apt install -y zsh
RUN apt install -y curl wget
RUN apt install -y git
RUN apt install -y vim
RUN apt install -y emacs

WORKDIR /root

ENV TERM=xterm-256color

# oh-my-zsh
#RUN curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh | bash -
#RUN sed -i -e "s/robbyrussell/ys/g" ~/.zshrc

# locale settings
RUN locale-gen zh_CN.UTF-8
ENV LC_ALL=zh_CN.UTF-8

# byobu settings
#RUN cat 'set -g default-terminal "xterm-256color"' > ~/.byobu/profile.tmux

RUN echo '\n\
# install oh-my-zsh  \n\
curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh | bash -  \n\
sed -i -e "s/robbyrussell/ys/g" ~/.zshrc \n\
# byobu settings \n\
#set -g default-terminal "xterm-256color" \n\
\n\
' >> /opt/setup_seed.sh

CMD zsh
