FROM node:15.13.0-stretch

RUN apt update && \
    apt install python3 python3-pip -y

RUN apt install tmux vim -y

RUN pip3 install wheel setuptools && \
    pip3 install pynvim

RUN curl -fsSL https://raw.githubusercontent.com/mcdulltii/dotfiles/master/etc/install | bash

ENTRYPOINT ["zsh"]
