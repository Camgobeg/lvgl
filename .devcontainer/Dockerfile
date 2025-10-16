# Ubuntu 24.04 tabanlı bir container oluştur
FROM ubuntu:24.04

# Locale ve temel ayarlar
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y \
    sudo curl wget git vim build-essential locales \
    && locale-gen en_US.UTF-8

# Kullanıcı oluştur (Codespaces uyumlu)
ARG USERNAME=codespace
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && apt-get install -y sudo \
    && echo "$USERNAME ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers.d/$USERNAME

USER $USERNAME
WORKDIR /home/$USERNAME
