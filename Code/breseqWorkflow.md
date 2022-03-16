**Before proceeding, download the sequence and annotation from GenBank on [NCBI](https://www.ncbi.nlm.nih.gov/genome/1391?genome_assembly_id=300626)**

**Locate bowtie2**<br>

export PATH=$PATH:~/path/to/bowtie2-2.3.5.1-macos-x86_64

**Run breseq** <br>

./breseq -r /path/to/Flavobacterium/GenBank/file/GCF_000016645.1_ASM1664v1_genomic.gb /path/to/forward/paired/read/Fj_anc_S47_R1_001_R1_paired.fastq.gz /path/to/forward/unpaired/read/Fj_anc_S47_R1_001_R1_unpaired.fastq.gz /path/to/reverse/paired/read/Fj_anc_S47_R2_001_R2_paired.fastq.gz -o /path/to/Output -j 8


**Note: the same script (shown above) was repeated for the 5 clonal isolates from *F. johnsoniae* coevolved lines and for the 5 clonal isolates from *F. johnsoniae* monoculture lines.** <br>

**Remove ancestor mutations** <br>

./gdtools SUBTRACT -o /path/for/Flavobacterium/coevolvedLine1/Output/output/FlavoCo1_subtractref_output.gd /path/to/Flavobacterium/coevolvedLine1/Output/output/output.gd /path/to/Flavobacterium/ancestor/Output/output/output.gd

**Note: the same script (shown above) was repeated for the remaining evolved lines.** <br>

**Create summary files** <br>

./gdtools ANNOTATE -o /path/for/Flavobacterium/coevolvedLine1/Output/output/FlavoCo1_subtractref.txt -f TSV -r /path/to/Flavobacterium/GenBank/file/GCF_000016645.1_ASM1664v1_genomic.gb /path/to/Flavobacterium/coevolvedLine1/Output/output/FlavoCo1_subtractref_output.gd


**Note: the same script (shown above) was repeated for the remaining evolved lines.**
