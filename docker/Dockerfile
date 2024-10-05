FROM r-base:4.4.1

LABEL org.opencontainers.image.source=https://github.com/arneso-ssb/docker-rpython
LABEL org.opencontainers.image.description="Container for running both python and R."
LABEL org.opencontainers.image.licenses=MIT

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        git \
        jq \
        libcairo2-dev \
        libcurl4-openssl-dev \
        libfontconfig1-dev \
        libfreetype6-dev \
        libfribidi-dev \
        libharfbuzz-dev \
        libjpeg-dev \
        libpango1.0-dev \
        libpng-dev \
        libssl-dev \
        libtiff-dev \
        libxml2-dev \
        micro \
        nano \
        pipx \
        python-is-python3 \
        python3 \
        python3-dev \
        python3-pip \
        python3-poetry \
        python3-venv \
        sudo \
    && apt-get purge -y --auto-remove \
    && rm -rf /var/lib/apt/lists/*

RUN pipx install nox && pipx inject nox nox-poetry && pipx ensurepath

WORKDIR /root

RUN mkdir settings

COPY packages.json install_packages.R ./settings/
RUN Rscript ./settings/install_packages.R
