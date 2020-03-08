FROM gcr.io/wise-cycling-267806/qc-base

WORKDIR /home/bioinfo/qc 
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/fastq/adaptorQC.fastq.gz
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/fastq/bad_example.fastq
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/fastq/good_example.fastq
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/fastq/qcdemo_R1.fastq.gz
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/fastq/qcdemo_R2.fastq.gz

# setup the user directory
RUN chown -R bioinfo:bioinfo /home/bioinfo
RUN echo 'export PS1=" \W\$ "' >> /home/bioinfo/.bashrc
# become the bioinfo
USER bioinfo
ENV HOME /home/bioinfo
WORKDIR /home/bioinfo
