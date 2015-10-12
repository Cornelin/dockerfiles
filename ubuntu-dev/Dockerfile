# Use ubuntu:14.04 as base image.
FROM ubuntu:14.04

MAINTAINER Lancelot Prigent "lancelot.prigent@gmail.com"

# Install basic packages.
RUN apt-get update && \
    apt-get install -y \
    	zsh \
    	curl \
    	wget \
    	git \
    	htop \
    	unzip \
    	vim && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Install oh-my-zsh and define zsh as default shell
RUN wget --no-check-certificate http://install.ohmyz.sh -O - | /bin/zsh || true && chsh -s /bin/zsh

# Apply custom theme, disable auto-update and fix backspace displaying space in the prompt
RUN sed -i 's/ZSH_THEME="robbyrussell"/ZSH_THEME="agnoster"/g' /root/.zshrc &&\
    sed -i 's/# DISABLE_AUTO_UPDATE=true/DISABLE_AUTO_UPDATE=true/g' /root/.zshrc &&\
    echo TERM=xterm >> /root/.zshrc

# Apply custom .gitconfig
# COPY /root/.gitconfig /root/.gitconfig

CMD ["/bin/zsh"]
