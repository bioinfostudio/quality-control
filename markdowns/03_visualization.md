## Quality Visualisation

We have a file for a good quality and bad quality statistics. FastQC
generates results in the form of a zipped and unzipped directory for
each input file.

Execute the following command on the two files:

```bash
$ fastqc -f fastq qcdemo_R1.fastq.gz
$ fastqc -f fastq qcdemo_R2.fastq.gz
```

View the FastQC report file of the bad data: [qcdemo_R2_fastqc.html](repo:results/qcdemo_R2_fastqc.html){:target="_blank"}

The report file will have a Basic Statistics table and various graphs
and tables for different quality statistics e.g.:

Property  | Value         
:----------|:-------------
Filename |qcdemo_R2.fastq.gz
File type | Conventional base calls
Encoding | Sanger / Illumina 1.9
Total Sequences | 1000000
Filtered Sequences | 0
Sequence length | 150
%GC | 37

**Table 2:** Summary statistics for bad_example_untrimmed

![image](repo:images/bad_qcdemo_R2.png)

**Figure 1:** bad_example_untrimmed_QC_plot

A Phred quality score (or Q-score) expresses an error probability. In
particular, it serves as a convenient and compact way to communicate
very small error probabilities. The probability that base A is wrong
(P(A)) is expressed by a quality score, Q(A), according to the
relationship:

\[Q(A) =-10 log10(P(A))\]

The relationship between the quality score and error probability is
demonstrated with the following table:


Quality score, Q(A) | Error probability, P(A) | Accuracy of base call
--------------------|:---------------------|:----------
10 | 0.1 | 90%
20 | 0.01 | 99%
30 | 0.001 | 99.9%
40 | 0.0001 | 99.99%
50 | 0.00001 | 99.999%

**Table 3:** Quality Error Probabilities
