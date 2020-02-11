FROM asia.gcr.io/wise-cycling-267806/qc-base

ADD https://storage.googleapis.com/bioinfostudio/qc/data/fastq/adaptorQC.fastq.gz /home/bioinfo/qc/
ADD https://storage.googleapis.com/bioinfostudio/qc/data/fastq/bad_example.fastq /home/bioinfo/qc
ADD https://storage.googleapis.com/bioinfostudio/qc/data/fastq/good_example.fastq /home/bioinfo/qc/
ADD https://storage.googleapis.com/bioinfostudio/qc/data/fastq/qcdemo_R1.fastq.gz /home/bioinfo/qc/
ADD https://storage.googleapis.com/bioinfostudio/qc/data/fastq/qcdemo_R2.fastq.gz /home/bioinfo/qc/

# setup the user directory
RUN chown -R bioinfo:bioinfo /home/bioinfo
RUN echo 'export PS1=" \W\$ "' >> /home/bioinfo/.bashrc
# become the bioinfo
USER bioinfo
ENV HOME /home/bioinfo
WORKDIR /home/bioinfo
