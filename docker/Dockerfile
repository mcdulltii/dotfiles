FROM node:15.13.0-stretch

RUN apt update && \
    apt install python3 python3-pip -y

RUN apt install tmux vim -y

RUN apt install locales -y && \
    echo "US/Pacific" > /etc/timezone && \
    dpkg-reconfigure -f noninteractive tzdata && \
    sed -i -e 's/# en_US.UTF-8 UTF-8/en_US.UTF-8 UTF-8/' /etc/locale.gen && \
    echo 'LANG="en_US.UTF-8"'>/etc/default/locale && \
    dpkg-reconfigure --frontend=noninteractive locales && \
    update-locale LANG=en_US.UTF-8

RUN pip3 install wheel setuptools && \
    pip3 install pynvim

RUN curl -fsSL https://raw.githubusercontent.com/mcdulltii/dotfiles/master/etc/install | bash

ENTRYPOINT ["zsh"]
