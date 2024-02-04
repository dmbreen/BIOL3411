# How to analyze genomes for genomes mini project

## Downloading your sequence
### From NCBI: 
1. Begin by downloading the NCBI command line tools and make them executable. <br> <br>
curl -o datasets https://ftp.ncbi.nlm.nih.gov/pub/datasets/command-line/v2/linux-amd64/datasets <br>
curl -o dataformat https://ftp.ncbi.nlm.nih.gov/pub/datasets/command-line/v2/linux-amd64/dataformat <br>
chmod +x datasets dataformat 

2. Now download the genome using its accession number. for ambystoma: <br> <br>	
./datasets download accession GCA_002915635.3

### From Axolotl-omics.org:
wget https://www.axolotl-omics.org/dl/AmexG_v6.0-DD.fa.gz

## Generating the reverse complement of a sequence.
1. Once you have isolated the .fa or .fasta file for your sequence, load the relevant modules (emboss and seqtk) into your working directory. <br> <br>
module load emboss/6.6.0 <br>
module load seqtk

2. Generate the reverse compliment of a sequence into a new file reversecompliment.txt <br> <br>
revseq AmexG_v6.0-DD.fa reversecompliment.txt

## Predicting the amino acid sequence of a sequence.
1. Once again, determine the name of the file you wish to translate and load the relevant modules (emboss and seqtk) <br> <br>
module load emboss/6.6.0 <br>
module load seqtk

2. Generate the predicted amino acid translation of a sequence into a new file AAsequence.txt <br> <br>
transeq AmexG_v6.0-DD.fa AAsequence.txt

## Determining the GC content of a sequence.
1. Determine the name of the file you wish to determine the GC content of and load emboss and seqtk. <br> <br>
module load emboss/6.6.0 <br>
module load seqtk

2. Using the command infoseq displays basic information about sequences, inlcuding GC content. <br> <br>
infoseq AmexG_v6.0-DD.fa
