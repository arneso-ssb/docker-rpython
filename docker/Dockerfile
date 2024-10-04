FROM r-base:4.4.1

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
        python3-pip \
        python3-poetry \
        python3-venv \
        sudo \
    && apt-get purge -y --auto-remove \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /root

RUN mkdir settings

COPY packages.json install_packages.R ./settings/
RUN Rscript ./settings/install_packages.R
