Dockerized
========

Dockerized dotfiles for \*NIX (Mac OS X and Linux) systems.

Usage
------------

### Installation:

```bash
wget https://github.com/mcdulltii/dotfiles/blob/master/docker/Dockerfile
docker build . --name docker_zsh
docker run -it docker_zsh
```

Troubleshooting
------------

* In the case where tmux is unable to run due to invalid LC_ALL, LC_CTYPE or LANG
    * Try `apt install locales` and `dpkg-reconfigure locales` with option en_US.UTF8

