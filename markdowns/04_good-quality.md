## Good Quality Data

View the FastQC report [qcdemo_R1_fastqc.html](repo:results/qcdemo_R1_fastqc.html){:target="_blank"}
to see examples of a good quality data and compare the quality plot with that of the bad example.

Sequencing errors can complicate the downstream analysis, which normally
requires that reads be aligned to each other (for genome assembly) or to
a reference genome (for detection of mutations). Sequence reads
containing errors may lead to ambiguous paths in the assembly or
improper gaps. In variant analysis projects sequence reads are aligned
against the reference genome. The errors in the reads may lead to more
mismatches than expected from mutations alone. But if these errors can
be removed or corrected, the read alignments and hence the variant
detection will improve. The assemblies will also improve after
pre-processing the reads to remove errors.
