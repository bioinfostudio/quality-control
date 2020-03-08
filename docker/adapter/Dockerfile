FROM gcr.io/wise-cycling-267806/qc-base

WORKDIR /home/bioinfo/qc
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/fastq/adaptorQC.fastq.gz
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/fastq/bad_example.fastq
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/fastq/good_example.fastq
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/fastq/qcdemo_R1.fastq.gz
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/fastq/qcdemo_R2.fastq.gz

RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/demo/qcdemo_R1_fastqc.html
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/demo/qcdemo_R1_fastqc.zip
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/demo/qcdemo_R2_fastqc.html
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/demo/qcdemo_R2_fastqc.zip

RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/trim/qcdemo-trimmed-pair1.fastq
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/trim/qcdemo-trimmed-pair1_fastqc.html
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/trim/qcdemo-trimmed-pair1_fastqc.zip
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/trim/qcdemo-trimmed-pair2.fastq
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/trim/qcdemo-trimmed-pair2_fastqc.html
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/trim/qcdemo-trimmed-pair2_fastqc.zip
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/trim/qcdemo-trimmed.log

RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/adapter/adaptorQC.fastq-trimmed.fastq
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/adapter/adaptorQC.fastq-trimmed.log
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/adapter/adaptorQC.fastq-trimmed_fastqc.html
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/adapter/adaptorQC.fastq-trimmed_fastqc.zip
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/adapter/adaptorQC_fastqc.html
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/adapter/adaptorQC_fastqc.zip
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/adapter/bad_example_fastqc.html
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/adapter/bad_example_fastqc.zip
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/adapter/bad_example_trimmed01.fastq
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/adapter/bad_example_trimmed01_fastqc.html
RUN curl -LO https://storage.googleapis.com/bioinfostudio/qc/data/adapter/bad_example_trimmed01_fastqc.zip
# setup the user directory
RUN chown -R bioinfo:bioinfo /home/bioinfo
RUN echo 'export PS1=" \W\$ "' >> /home/bioinfo/.bashrc
# become the bioinfo
USER bioinfo
ENV HOME /home/bioinfo
