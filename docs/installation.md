# Commandline Arguments & Installation

## Required Dependencies
* Linux-based computer, server, or cluster.
* [Docker](https://docs.docker.com/engine/install/)


## Commandline Arguments and Description

| Command | Description |
| :---: | :---: |
| Required |
| -o | <output directory\> name of the directory where you would like your hamrlinc run output files to be saved |
| -c | <filenames for each fastq.csv\> a csv file that corresponds each SRA ID (or name of fastq file) to your desired nomenclature for each read. An example file is provided in the pipeline repo |
| -g | <reference genome.fa\> a fasta file of the genome of the model organism. We currently support only genome and annotation files sourced from ENSEMBLE |
| -i | <reference genome annotation.gff3\> a gff3 file of the genome of the model organism, note we require gff3 instead of gtf |
| -l | <read length\> an integer, the read length of this sequencing experiment, if non-unanimous use the shortest length |
| -s | <genome size in bp\> an integer, the number of base pairs of the genome of this model organism |
| Optional |
| -n | \[number of threads\] default=4 |
| -d | \[raw fastq folder\] a path to a folder containing raw fastq files if needed, in such case, -c csv should have each fastq file as key |
| -a | \[use Tophat2 instead of STAR\] default uses STAR |
| -b | \[Tophat2 library choice: fr-unstranded, fr-firststrand, fr-secondstrand\] default=fr-firststrand |
| -f | \[filter\] default=filter_SAM_number_hits.pl |
| -k | \[activates modification analysis (left arm)\] |
| -p | \[activates lincRNA identification (inner right arm)\] |
| -u | \[activates regular featurecount (outer right arm)\] |
| -v | \[evolinc option: M or MO\] default=M |
| -Q | \[HAMR: minimum qualuty score\] default=30 |
| -C | \[HAMR: minimum coverage\] default=50 |
| -E | \[HAMR: sequencing error\] default=0.01 |
| -P | \[HAMR: maximum p-value\] default=1 |
| -F | \[HAMR: maximum FDR\] default=0.05 |
| -T | </path/to/transposable_elements_file\> only required under evolinc MO option |
| -G | </path/to/CAGE_RNA_file\> only required under evolinc MO option |
| -D | </path/to/known_lincRNA_file\> only required under evolinc MO option |
| -m | \[HAMR model\] default=euk_trna_mods.Rdata |
| -h | \[help message\]|

## Pulling HAMRLINC Docker Image
To run HAMRLINC, you need to first pull the docker image for the pipeline to your computer. If you are not familiar with container technology and would like to learn the basics, please check out [CyVerse Container & Cloud Native Camp Documentation](https://cc.cyverse.org/). It is open source and free. Dig in!

Pull HAMRLINC docker image. This should take a few minutes depending on your internet speed.
```
docker pull chosenobih/hamrlinc:v0.1
```
After building the conatiner, run the code below to be sure that you now have the image on your computer
```
docker image ls
```