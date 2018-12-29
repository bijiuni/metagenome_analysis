# metagenome_analysis
Effect of soil composition on microbial ecosystems


## Bacterial genome assembly


First, in order to assemble the metagenome into contigs, the following SPAdes command was called.
 ```
 /usr/bin/spades.py -1 /data/metagenomes/160523Alm_D16-4703_1_sequence.fastq.gz -2 /data/metagenomes/160523Alm_D16-4703_2_sequence.fastq.gz --meta -o ~/GIT/Computational-Biology/Final -t 1
 ```

## Introduction

Biological activities, especially microbial behaviors, are crucial for the understanding of contaminant fate. In order to investigate the microbial mutations under the effects of contaminants like nitrate, uranium and technetium, this project constructed phylogenetic trees based on a few selected organisms. Using the phylogenetic method, the mutation rates can be estimated by comparing close relatives and last common ancestors.

## Results

### Taxonomic analysis

Four MG-RAST entries from layer 1 through layer 4 are included to generate a count table of organism with number of annotated contigs for each layer, which is then normalized based on the size differences (rows of annotation) to eliminate cross-layer bias. The top 20 most abundant organisms from each layer are inspected, of which 16 are shared by all four groups.

<img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/a1.PNG"> 
<img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/a2.PNG">

<br>
The sequence corresponding each of the 15 organisms in each layer are extracted out for PhyloSift pipeline, which is customized to metagenomic analysis and does not rely on multiple alignment. However, PhyloSIFT run failed due to perl package inconsistency since 2015, and alternative attempt to extract 16S rRNA via HMMER failed due to low abundance of genetic profile. Instead, similar processing was applied to KO ontology data and 14 representative functions are selected.

<br>

<img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/a3.PNG"> 
<img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/a4.PNG">

<br>

Clustering Analysis were performed on organism distribution and Ontology Enrichment. For the graph below, 3 species of Acidobacterium are closely grouped and 2 species of Roseiflexus are closely grouped, indicating that similar species share similar living condition. The lack of presence of groups in layer2 but abundant in layer 1 and 3 also implies potential competition of niche and cross-layer differentiation.

<br>

<img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/a5.PNG"> 
<img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/a6.PNG">

<br>

From the ontology clustering, aerobic related activity was largely expressed in the two upper layers whereas Anti-microbial effect is stronger in lower 2 layers, demonstrating adaptation of metabolic pathway to environment. Function-wide, 3 Acetyl-CoA related pathway grouped together and each layer has its own signature pathways that should be further investigated. Similar approach was later implemented on the whole set of intersecting set of function and ontology, and it is shown that the two upper/lower layer are more closely related. More layers should be incorporated to make the depth effect more evident.


### Ontology of metabolic characters

To understand the effect of the environment on the microbial ecosystem, we used MG-RAST to analyze the distribution of functional metabolic categories in the Subsystems database. Two separate investigations were conducted. First we considered the distribution of ontologies across all species present in each layer. Then, building on the previous taxonomic analysis, we showed how certain species evolved to colonize specific soil layers.

### Effect of soil on metabolic characters

Here we investigate the link between the evolution of soil composition as a function of depth and the prevalence of metabolic characters. Specifically, our work focussed on three crucial elements for microbe growth: iron, potassium and phosphorus.
Our analysis of soil composition revealed that the iron content increased more than threefold between layer 1 and layer 6. This is consistent with other studies which show iron content increases with soil depth and age. Iron is essential for the vast majority of microbes and is involved in several important metabolic processes. Interestingly, our analysis of iron metabolism ontology showed that the amount of genetic material dedicated to iron acquisition also increased with depth, despite the iron content being higher. This suggests that species requiring high amounts of iron for their metabolic processes live deeper.
Potassium and phosphorus levels both increased with soil depth. Phosphorus deficiency prevents microorganisms growth whilst excess phosphorus  can negatively impact the phosphate metabolism. Hence, intracellular phosphorus content is heavily regulated in living organisms. Potassium rich environments also facilitate the uptake efficiency of potassium. Therefore, as both potassium and phosphorus levels increase with depth, the competition for these chemical species decreases and species dedicate less genetic resources to their metabolism.


<br>

<img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/a7.PNG"> 

<br>

### Species adaptation to specific layers

In order to match the ontology and biological information in each layer, eight groups of bacteria were analyzed against two ontology attributes. Specifically, four groups of photosynthetic bacteria were selected: Cyanobacteria (phylum), Chlorobiaceae (green sulphur family), Chloroflexia (green non-sulphur class), and Chromatiales (purple sulphur order). An increase in depth of the abundance of photosynthetic bacteria was observed, consistent with the increasing photosynthesis in ontology analysis. This result was contrary to expectations since bacterias living deeper have less sunlight. However, not all groups of bacteria contribute to the ontology equally. Chloroflexia, for instance, has decreasing abundance with higher depth. Other ontologies and metabolism of these species could explain their prevalence in lower layers.

<br>

<img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/a8.PNG"> 

<br>

4 groups of nitrogen-fixing bacteria were selected to evaluate nitrogen metabolism in ontology analysis: Rhizobium (genus), Nostoc (genus), Azotobacter (genus), and Clostridium (genus). However, here, the ontology analysis did not match the abundance analysis. The fourth layer had twice as much genetic material dedicated to the a nitrogen metabolism than other layers. However the abundance analysis showed a peak at the fifth layer. This could be due to the other nitrogen-fixation activities not considered in the fourth layer or disturbing factors in the ontology analysis.


## DISCUSSION

Complete metagenomes were successfully uploaded to One Codex. We investigated the similarity between different parts of the metagenome by comparing abundance analysis and individual statistics in both One Codex and MG-RAST..

Although the top phylum were similar in One Codex and MG-RAST, the ranks and proportions of individual phylum varied.. For instance, Proteobacteria in One Codex represented 10% of all reads and only 3.5% in MG-RAST. Several factors could explain these discrepancies: differences in databases, uneven distribution of organisms in metagenomes, and distinct annotation methods. It is also important to note that One Codex includes the unidentified reads in its counts, where MG-RAST does not, which also could explain these differences.

<br>

<img src="https://github.com/bijiuni/metagenome_analysis/blob/master/img/a9.PNG"> 

<br>

Our data was limited by the use of a subset of the overall data (~10-20% of the total data available was used through MG-RAST). The underlying assumption of our work was that the MG-RAST analysis reflected the whole data. However, the One Codex data does suggest that there are some discrepancies. In the future, the confidence intervals of our data could be quantified by taking additional subsets of the overall data set and determining the variance in results between the subsets. 

## CONCLUSION
Our initial metagenomic analyses show that each layer has its own set of bacteria and reveal correlations between soil composition and microbial ecosystems. These preliminary results need to be confirmed by further analysis of the whole metagenome for all layers. In addition, the metagenome of microbial populations in non-contaminated soil would provide a useful comparison. Such an analysis could shed light on the sequence of events that occurred post- contamination in regards to species mutation and migration.


## Authors

* **Paulameena Shultes**
* **Steven Yu**
* **Thomas Galeon**
* **Zach Lyu**
