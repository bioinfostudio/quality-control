## Adapter Clipping

Sometimes sequence reads may end up getting the leftover of adapters and
primers used in the sequencing process. It’s good practice to screen
your data for these possible contamination for more sensitive alignment
and assembly based analysis.

This is particularly important when read lengths can be longer than the
molecules being sequenced. For example when sequencing miRNAs.

Various QC tools are available to screen and/or clip these
adapter/primer sequences from your data. Apart from `skewer` which will be
using today the following two tools are also useful for trimming and
removing adapter sequence:

- [Cutadapt](https://cutadapt.readthedocs.io/en/stable/)
- [Trimmomatic](http://www.usadellab.org/cms/?page=trimmomatic)


Here we are demonstrating `Skewer` to trim a given adapter sequence.

```bash
qc$ fastqc -f fastq  adaptorQC.fastq.gz
```
View [adaptorQC_fastqc.html](repo:results/adaptorQC_fastqc.html){:target="_blank"}

```bash
qc$ skewer -x TGGAATTCTCGGGTGCCAAGGT -l 10 -L 35 -q 30 adaptorQC.fastq.gz
```

> **-x:** adaptor sequence used  
> **-l:** min length to keep after trimming  
> **-L:** max length to keep after trimming, in this experiment we were expecting only small RNA fragments  
> **-q:** quality threshold used for trimming at 3’ end. Use -m option to control the end you want to trim  

Run FastQC on the adapter trimmed file and visualise the quality scores.
Fastqc now shows adaptor free results.

```bash
qc$ fastqc adaptorQC.fastq-trimmed.fastq
```

View [adaptorQC.fastq-trimmed_fastqc.html](repo:results/adaptorQC.fastq-trimmed_fastqc.html){:target="_blank"}


### Fixed Length Trimming

**We will not cover fixed length trimming but provide the following for
your information.**

Low quality read ends can be trimmed using a
fixed-length trimming. We will use the `fastx_trimmer` from the
FASTX-Toolkit. Usage message to find out various options you can use
with this tool. Type `fastx_trimmer -h` at anytime to display help.

We will now do fixed-length trimming of the `bad_example.fastq` file
using the following command. You should still be in the qc directory, if
not cd back in.

```bash
qc$ fastqc -f fastq bad_example.fastq
qc$ fastx_trimmer -h
qc$ fastx_trimmer -Q 33 -f 1 -l 80 -i bad_example.fastq -o bad_example_trimmed01.fastq
```

We used the following options in the command above:

> **-Q 33:** indicates the input quality scores are Phred+33 encoded  
> **-f:** first base to be retained in the output  
> **-l:** last base to be retained in the output  
> **-i:** input FASTQ file name  
> **-o:** output file name  

Run FastQC on the trimmed file and visualise the quality scores of the
trimmed file.

```bash
qc$ fastqc -f fastq bad_example_trimmed01.fastq
```

[bad_example_trimmed01_fastqc.html](repo:results/bad_example_trimmed01_fastqc.html){:target="_blank"}

The output should look like:

Property  | Value        
:----------|:-------------
Filename | bad_example_trimmed01.fastq
File type | Conventional base calls
Encoding | Sanger / Illumina 1.9
Total Sequences | 40000
Filtered Sequences | 0
Sequence length | 80
%GC | 48

**Table 5:** Summary Statistics of bad_example_trimmed summary

![image](repo:images/bad_example_trimmed_to_80bp.png "reaaaaaa")

**Figure 3:** bad_example_trimmed_plot
