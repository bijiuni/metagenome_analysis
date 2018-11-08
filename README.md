# metagenome_analysis
Analyzing a microbial metagenome obtained from radioactive soil


## Bacterial genome assembly


First, in order to assemble the metagenome into contigs, the following SPAdes command was called.
 ```
 /usr/bin/spades.py -1 /data/metagenomes/160523Alm_D16-4703_1_sequence.fastq.gz -2 /data/metagenomes/160523Alm_D16-4703_2_sequence.fastq.gz --meta -o ~/GIT/Computational-Biology/Final -t 1
 ```


In order to quantify the abundance of different microbes, the two metagenome files were uploaded one codex. The results are as follows.

<img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/analysis1.PNG" width="1000"> <img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/analysis2.PNG" width="1000">

<img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/compo1.PNG" width="400"><img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/compo2.PNG" width="400">

<img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/taxo1.PNG" width="1000"><img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/taxo2.PNG" width="1000">

