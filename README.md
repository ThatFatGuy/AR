# AR
Specific codes for Attika to use

> Make bowtie2 in path so it can be used by other programs

```bash
export PATH=/usr/local/bin/bowtie2-2.2.8/:$PATH

```

> Navigate to directory

```bash
cd ../../staff_groups/lamontlab/OGF1374

```

> Run BREseq on TRIMMED samples

```bash
./breseq/bin/breseq -j 20 -r PAO1.gbff -o sampleX_output trimmed_forward_reads.fastq.gz \
trimmed_reverse_reads.fastq.gz

```

>outputs will be in sampleX_output/output/summary.html - enjoy. Sam
