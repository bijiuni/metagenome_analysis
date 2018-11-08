# metagenome_analysis
Analyzing a microbial metagenome obtained from radioactive soil


## Bacterial genome assembly


First, in order to assemble the metagenome into contigs, the following SPAdes command was called.
 ```
 /usr/bin/spades.py -1 /data/metagenomes/160523Alm_D16-4703_1_sequence.fastq.gz -2 /data/metagenomes/160523Alm_D16-4703_2_sequence.fastq.gz --meta -o ~/GIT/Computational-Biology/Final -t 1
 ```

<br>
In order to quantify the abundance of different microbes, the two metagenome files were uploaded one codex. The results are as follows.
<br>

<img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/analysis1.PNG" width="1000"> <img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/analysis2.PNG" width="1000">

<br>
From the above graph we can see that the most dominant composition in _160523Alm_D16-4703_1_sequence.fastq.gz_(hereafter referred as sequence 1) is Actinomyces odontolyticus (27.88%) while the most dominant composition in _160523Alm_D16-4703_2_sequence.fastq.gz_(hereafter referred as sequence 2) is Armatimonadetes bacterium (16.48%). 

The bacterial repository in sequence 2 is obviously more diverse, with 22 spicies marked as at least low abundance.

<br>

<img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/compo1.PNG" width="1000"><img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/compo2.PNG" width="1000">

<br>

The composition graph again confirms the summary obtained above. It is worth noting that the percentages of bacterials that are not in the top ten are high in both sequences (31.64% and 40.76% respectively).

The noticeable difference is that Actinomyces odontolyticus, which is the most abundant organism in sequence 1, only covers 4.49% in sequence 2.

The obvious overlappings are:
* Armatimonadetes bacterium 13_1_40CM_64_14; 	
* Candidatus Rokubacteria bacterium 13_1_20CM_2_69_58
* Acidobacteria bacterium 13_1_20CM_2_60_10
* Acidobacteria bacterium 13_1_40CM_2_60_7

<br>

<img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/taxo1.PNG" width="1000"><img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/taxo2.PNG" width="1000">

<br>

In both sequences, most organisms other than archea are in the bacteria superkingdom.

The pylums that are common in both sequences are Candidatus Rokubacteria, Proteobacteria, Actinobacteria, and Frimicutes.
