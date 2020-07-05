
FROM ubuntu:18.04

ENV DEBIAN_FRONTEND=noninteractive

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN apt-get update \
    && apt-get install -y \
    # version control system(s)
    git \
    #mercurial cvs subversion \
    # hardware build tools
    iverilog \
    #verilator \
    # hardware synthesis tools
    #qflow \
    # hardware debug tools
    gtkwave \
    # build tools/utilities
    gputils \
    make gcc libc6-dev \
    python3-pip \
    latexmk texlive-latex-recommended texlive-fonts-recommended texlive-formats-extra \
    #tcl-dev python3 python-pip build-essential autoconf \
    #python2.7-dev libyaml-dev libyaml-dev  python-yaml libelf-dev \
    #gperf bison flex clang libreadline-dev gawk \
    #libffi-dev graphviz xdot pkg-config \
    --no-install-recommends \
    && pip3 install -U Sphinx \
    && pip3 install Pillow \
    && pip3 install sphinx_rtd_theme \
    #&& pip install pytest \
    #&& pip install tap.py \
    #&& pip install fusesoc \
    && groupadd --gid $USER_GID $USERNAME \
    && useradd -s /bin/bash --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && apt-get install -y sudo --no-install-recommends \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME\
    && chmod 0440 /etc/sudoers.d/$USERNAME \
    && apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

ENV DEBIAN_FRONTEND=dialog

RUN uname -a
