FROM biocontainers/biocontainers:vdebian-buster-backports_cv1

USER root
RUN apt-get update --fix-missing
RUN apt-get install -t buster-backports -y \
    curl \
    git \
    build-essential \
    nano \
    man \
    less \
    fastqc \
    fastx-toolkit

RUN git clone https://github.com/relipmoc/skewer.git && cd skewer && make && make install
RUN apt-get clean && apt-get purge && rm -rf /var/lib/apt/lists/* /tmp/*

# create a non-root user
RUN useradd -ms /bin/bash bioinfo 
