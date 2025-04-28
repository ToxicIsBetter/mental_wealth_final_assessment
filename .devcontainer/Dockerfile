# Use VS Code base image (Debian)
FROM mcr.microsoft.com/vscode/devcontainers/base:debian

# Install dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
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
    build-essential \
    libxml2-dev \
    ca-certificates \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Install Quarto
RUN wget -q https://quarto.org/download/latest/quarto-linux-amd64.deb \
    && dpkg -i quarto-linux-amd64.deb \
    && rm -f quarto-linux-amd64.deb

# Install TinyTeX via Quarto
RUN quarto install tinytex \
    && quarto check tinytex

# Set environment variables for Quarto and TinyTeX
ENV PATH="/opt/quarto/bin:/opt/tinytex/bin/x86_64-linux:$PATH"

# Set default shell to bash
SHELL ["/bin/bash", "-c"]
