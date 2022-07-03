#
# VSCode devcontainer for development with: Ubuntu + Ruby + Jekyll
#
ARG UBUNTU_VERSION=20.04

FROM ubuntu:$UBUNTU_VERSION

ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8
RUN unset DISPLAY
ENV DEBIAN_FRONTEND=noninteractive

########
# Setup apt
########

# switch to automatic mirror select mode, makes building much faster down here
RUN sed -i 's http://archive.ubuntu.com/ubuntu/ mirror://mirrors.ubuntu.com/mirrors.txt ' /etc/apt/sources.list

# install apt utilities, sudo (for non-root user) and some dev and networking debugging utilities
# note that we don't clear out the APT-GET cache -- one often needs to install packages inside the devcontainer.
RUN apt-get update && apt-get -y upgrade \
 && apt-get -qqy install software-properties-common apt-transport-https gnupg2 \
 && apt-get -qqy install sudo git curl iputils-ping

########
# Setup vscode user
########

# create the non-root user that we're going to use for dev
# -m: create home
# -s: set shell
# -G sudo: add to sudo group
RUN useradd -ms /bin/bash -G sudo vscode
# the whole sudo group does not need to supply password when sudoing
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

# Set the default user
USER vscode
# in-case base image sets this to root, we have to reset to vscode's home (USER
# statement not sufficient)
ENV HOME=/home/vscode

########
# Setup Ruby & Jekyll
########

RUN sudo apt-get install -qqy ruby-full zlib1g-dev
RUN sudo apt-get install -qqy --no-install-recommends build-essential

# Configure gems to install into home directory
RUN ( echo '# Install Ruby Gems to ~/gems' \
 && echo 'export GEM_HOME="$HOME/gems"' \
 && echo 'export PATH="$HOME/gems/bin:$PATH"'; ) >> $HOME/.bashrc

# default command to run if nothing else is specified
CMD ["/bin/bash"]
