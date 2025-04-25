FROM mcr.microsoft.com/vscode/devcontainers/base:debian

# Install dependencies
RUN apt-get update && apt-get install -y \
    curl \
    wget \
    pandoc \
    python3 \
    python3-pip \
    libcurl4-openssl-dev \
    libssl-dev \
    git \
    libfontconfig1 \
    libfreetype6-dev \
    && apt-get clean 
    
# Install Quarto
RUN wget https://quarto.org/download/latest/quarto-linux-amd64.deb \
    && dpkg -i quarto-linux-amd64.deb \
    && rm quarto-linux-amd64.deb

# Set default shell
SHELL ["/bin/bash", "-c"]

RUN apt-get update && apt-get install -y \
    build-essential \
    libcurl4-openssl-dev \
    libssl-dev \
    libxml2-dev \
    quarto install tinytex \
    && rm -rf /var/lib/apt/lists/*
