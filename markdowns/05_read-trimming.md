## Read Trimming

Read trimming can be done in a variety of different ways. Choose a
method which best suits your data. Here we are giving examples of
fixed-length trimming and quality-based trimming.

### Quality Based Trimming

Base call quality scores can be used to dynamically determine the trim
points for each read. A quality score threshold and minimum read length
following trimming can be used to remove low quality data.

The previous FastQC results show R1 is fine but R2 has low quality at
the end. There is no adaptor contamination though. We will be using
Skewer to perform the quality trimming.

Run the following command to quality trim a set of paired end data.

```bash
qc$ skewer -l 50  -q 30 -Q 25 -m pe -o qcdemo qcdemo_R1.fastq.gz qcdemo_R2.fastq.gz
```

> **-l:** min length to keep after trimming  
> **-q:** quality threshold used for trimming at 3’ end  
> **-Q:** mean quality threshold for a read  
> **-m:** pair-end mode  

Run FastQC on the quality trimmed file and visualise the quality scores.

Look at the last files generated, are the file names same as the input ?

```bash
qc$ ls -ltr
```

Run Fastqc on the quality trimmed files:

```bash
qc$ fastqc -f fastq qcdemo-trimmed-pair1.fastq
qc$ fastqc -f fastq qcdemo-trimmed-pair2.fastq
```

Visualise the `fastqc` results:

- [qcdemo-trimmed-pair1_fastqc.html](repo:results/qcdemo-trimmed-pair1_fastqc.html){:target="_blank"}
- [qcdemo-trimmed-pair2_fastqc.html](repo:results/qcdemo-trimmed-pair2_fastqc.html){:target="_blank"}

Let’s look at the quality from the second reads. The output should look
like:

Property  | Value    
:----------|:-------------
Filename | qcdemo-trimmed-pair2.fastq
File type | Conventional base calls
Encoding | Sanger / Illumina 1.9
Total Sequences | 742262
Filtered Sequences | 0
Sequence length | 50-150
%GC | 37

**Table 4:** Summary Statistics of QC_demo_R1_trimmed

![image](repo:images/bad_qcdemo_R2_quality_trimmed.png)

**Figure 2:** bad_example_quality_trimmed_plot
