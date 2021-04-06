FROM alpine:latest

RUN apk update

RUN apk add zsh vim tmux git perl

RUN sed -i -e "s/bin\/ash/bin\/zsh/" /etc/passwd

RUN git clone --depth=1 https://github.com/amix/vimrc.git ~/.vim_runtime && \
    sh ~/.vim_runtime/install_awesome_vimrc.sh

RUN cd && git clone https://github.com/gpakosz/.tmux.git && \
    ln -s -f .tmux/.tmux.conf

RUN mkdir -p "$HOME/.zsh" && \
    git clone https://github.com/sindresorhus/pure.git "$HOME/.zsh/pure" && \
    echo "fpath+=$HOME/.zsh/pure" >> $HOME/.zshrc && \
    echo "autoload -U promptinit; promptinit" >> $HOME/.zshrc && \
    echo "prompt pure" >> $HOME/.zshrc

ENTRYPOINT ["/bin/zsh"]
