FROM asia.gcr.io/wise-cycling-267806/qc-base

ADD https://storage.cloud.google.com/bioinfostudio/qc/data/fastq/adaptorQC.fastq.gz /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/fastq/bad_example.fastq /home/bioinfo/qc
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/fastq/good_example.fastq /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/fastq/qcdemo_R1.fastq.gz /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/fastq/qcdemo_R2.fastq.gz /home/bioinfo/qc/

ADD https://storage.cloud.google.com/bioinfostudio/qc/data/demo/qcdemo_R1_fastqc.html /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/demo/qcdemo_R1_fastqc.zip /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/demo/qcdemo_R2_fastqc.html /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/demo/qcdemo_R2_fastqc.zip /home/bioinfo/qc/

ADD https://storage.cloud.google.com/bioinfostudio/qc/data/trim/qcdemo-trimmed-pair1.fastq /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/trim/qcdemo-trimmed-pair1_fastqc.html /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/trim/qcdemo-trimmed-pair1_fastqc.zip /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/trim/qcdemo-trimmed-pair2.fastq /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/trim/qcdemo-trimmed-pair2_fastqc.html /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/trim/qcdemo-trimmed-pair2_fastqc.zip /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/trim/qcdemo-trimmed.log /home/bioinfo/qc

ADD https://storage.cloud.google.com/bioinfostudio/qc/data/adapter/adaptorQC.fastq-trimmed.fastq /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/adapter/adaptorQC.fastq-trimmed.log /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/adapter/adaptorQC.fastq-trimmed_fastqc.html /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/adapter/adaptorQC.fastq-trimmed_fastqc.zip /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/adapter/adaptorQC_fastqc.html /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/adapter/adaptorQC_fastqc.zip /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/adapter/bad_example_fastqc.html /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/adapter/bad_example_fastqc.zip /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/adapter/bad_example_trimmed01.fastq /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/adapter/bad_example_trimmed01_fastqc.html /home/bioinfo/qc/
ADD https://storage.cloud.google.com/bioinfostudio/qc/data/adapter/bad_example_trimmed01_fastqc.zip /home/bioinfo/qc/
# setup the user directory
RUN chown -R bioinfo:bioinfo /home/bioinfo
RUN echo 'export PS1=" \W\$ "' >> /home/bioinfo/.bashrc
# become the bioinfo
USER bioinfo
ENV HOME /home/bioinfo
WORKDIR /home/bioinfo/qc
