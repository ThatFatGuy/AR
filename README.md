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

>Trim files using Trimmomatic

```bash
java -jar /usr/local/bin/Trimmomatic-0.35/trimmomatic-0.35.jar PE -threads 20 -phred33 sample_read1.fastq.gz \
sample_read2.fastq.gz output1_forward_paired.fq.gz output1_forward_unpaired.fq.gz \
output1_reverse_paired.fq.gz output1_reverse_unpaired.fq.gz \
ILLUMINACLIP:/usr/local/bin/Trimmomatic-0.35/adapters/TruSeq3-PE.fa:2:30:10 LEADING:5 TRAILING:5 SLIDINGWINDOW:4:20 MINLEN:20

```

> Run BREseq on TRIMMED samples

```bash
./breseq/bin/breseq -j 20 -r PAO1.gbff -o sampleX_output trimmed_forward_reads.fastq.gz \
trimmed_reverse_reads.fastq.gz

```

>outputs will be in sampleX_output/output/summary.html - enjoy. Sam


>Random R plot stuff (includes my sample names - make sure you change these)

```R
datplot <- ggplot(data, aes(x=stage, y=r, fill=factor(restistance))) +
  geom_boxplot(fill=('White'))+
  geom_dotplot(binaxis='y', stackdir='center', dotsize=0.8)+
  scale_fill_brewer(palette='RdBu')+
  labs(x="Resistance selection", y="Growth rate")

```

>making faceted graphs for genome coverage

```R
sp <- ggplot(data, aes(x=position, y=coverage)) + geom_line (colour=sample, group=sample)
sp
sp <- sp + facet_grid(sample ~ .)
sp

```



