# Use VS Code base image (Debian)
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
    build-essential \
    libxml2-dev \
    && apt-get clean

# Install Quarto
RUN wget https://quarto.org/download/latest/quarto-linux-amd64.deb \
    && dpkg -i quarto-linux-amd64.deb \
    && rm quarto-linux-amd64.deb

# Install TinyTeX via Quarto (correct method)
RUN quarto install tinytex

# Set default shell to bash
SHELL ["/bin/bash", "-c"]

# Clean up apt caches and unnecessary files
RUN rm -rf /var/lib/apt/lists/*

# Optional: Set environment variables for Quarto
ENV PATH="/opt/quarto/bin:$PATH"
