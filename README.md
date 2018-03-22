# PDSB-Project Proposal
## Neha Savant
#### March 21, 2018


Many people in the landscape and population genetic field use cluster analysis and genetic distance metrics to analyze genetic structure in different species, but many are also interested in visualizing this structure. Further, scientists are also interested in taking genetic data from known locations and extending this information to other parts of the landscape that they were not able to sample. Creating a resistance map from interpolated genetic data will be of particular interest for those who want to take their genomic data and create useful figures to communicate their research findings. 

For my project, I am curious about how to visualize a resistance map of the genomic structure of long-tail salamanders across the northern New Jersey landscape. The species is considered state-threatened and can be found in caves, ponds, streams and sprinhouses in northern New Jersey. The species is further threatened by a pipeline proposed to be built across its stream habitats. This resistance map will be useful for outlining important areas for this species' connectivity and will assist managers in understanding how to mitigate the impacts of this pipeline on the salamanders' natural gene flow. 

I will be using ddRAD sequencing data (protocol from Peterson et al. 2012) from salamander DNA samples that I collected last summer. About 1/3 of samples were collected from ponds, while another 2/3 were collected from streams for a total of 266 individuals. Approximately 45 individuals come from a finely sampled four mile stretch of stream. All individuals have been georeferenced; the stream sites cover 88 sq mi (45 sq mi without an outlier population) while the pond sites cover approximately 38 sq mi extent.  The data is currently available as raw reads as well as in various format after being filtered through Stacks v.1.48 populations script (VCF, genid, structure). 

I plan to use a suite of tools in Python and R. I am open to using other tools I find as I move forward with this project, but will start with the following methodology:

1. Use [ipyrad] to filter the RAD reads. I may also start with structure files outputed from Stacks. 
2. Run the cluster analysis using [STRUCTURE] (Pritchard et al. 2000) on several different K values. Then determine a useful K value for the rest of the analysis. 
3. Use [CLUMPP] in R to estimate admixture coefficients (Leroy et al. 2013; Jakobsson & Rosenberg 2007)
4. Interpolate admixture coefficients using TESS package in R (Chen et al. 2007)
5. Visualize the data on a map.

I am still reading through and working through ways to spatially interpolate the data across a map. Current methods do not use georeferenced data. 

## Literature Cited

Chen, C., Durand, E., Forbes, F., & François, O. (2007). Bayesian clustering algorithms ascertaining spatial population structure: a new computer program and a comparison study. Molecular Ecology Resources, 7(5), 747-756.

Jakobsson, M., & Rosenberg, N. A. (2007). CLUMPP: a cluster matching and permutation program for dealing with label switching and multimodality in analysis of population structure. Bioinformatics, 23(14), 1801-1806.

Leroy, T., Lemaire, C., Dunemann, F., & Le Cam, B. (2013). The genetic structure of a Venturia inaequalis population in a heterogeneous host population composed of different Malus species. BMC evolutionary biology, 13(1), 64.

Pritchard, J. K., Stephens, M., & Donnelly, P. (2000). Inference of population structure using multilocus genotype data. Genetics, 155(2), 945-959.


[CLUMPP]: https://rosenberglab.stanford.edu/clumpp.html
[ipyrad]: http://ipyrad.readthedocs.io/analysis.html
[STRUCTURE]: https://web.stanford.edu/group/pritchardlab/structure.html


