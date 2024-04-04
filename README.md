**Matthew Morassutti** 
**BIOL 550 SPR'24 Project Proposal** UPDATED

**Draft Title:**
Resolving the ranges of _Marmota_ using Ultraconserved Elements

**Question and Relevance**

This project will aim to unravel the eevolutionary history of marmots (_Marmota sp._) by addressing their phylogenetic relationships. By using ultraconserved elements (UCEs) from all 15 extant marmot species, this project will pinpoint the divesification of marmots. The relevance of this project lies in understanding how marmots rapidly diversified during the Pleistocene in response to a changing climate in cold, seasonal environments. By improving our understanding of evolutionary dynamics in response to past environmental changes I will inform our understanding of species' responses to ongoing climate change and alterations to habitat. This helps us to better conserve these species by helping us know species relationships and cryptic diversity. 

**Focal Organism Introduction**

Marmots (_Marmota sp._) are a genus of large-bodied ground squirrels known for their rapid diversification during the Pleistocene epoch (Kerhoulas et al. 2015). Adapted to survive harsh, cold winters, they inhabit a wide range of habitats across the Holarctic region, from North America to the European Alps (Barash, 1974; Armitage, 1981; Arnold, 1992; Krysť ufek
and Vohraliḱ , 2013). Despite their broad geographic distribution, marmots show relatively little morphological evolution since their radiation, indicating a high degree of conservatism in their body plan (Hafner 1984). Their ecological versatility allows them to occupy various elevations and biomes, from sea level to high-altitude, hypoxic conditions (Bai et al. 2019). Marmots have been the subject of biological research due to their diverse social organizations, making them valuable models for understanding social behaviors in response to environmental challenges (Barash 1974).

**Methods Overview**

Using 95% and 75% supermatrices from Mills et al. 2023, UCE reads for Marmots will be partitioned using the entropy-based method SWSC-en, designed specifically for UCE Loci (Tagliacollo and Lanfear, 2018). PartitionFinder2 will be used to consolidate and identify the best substitution model for each partition. Maximum likelihood trees will be estimated for the concatenated dataset using IQ-TREE (Nguyen et al. 2015) with branch supports obtained using the oltrafast bootstrap method (UFboot; Hoang et al. 2017) and the SH-like approximate likelihood ratio test (SH-aLRT; Anisimova et al. 2011), both with 1000 replicates. 
  
A coalescent-based method will be used to estimate a phylogeny. UCE loci will be sorted by number of parsimony-informative sites using the _'phyluce_get_informative_sites'_ script, and th dataset will be reduced to the top quartile of loci. A maximum-likelihood gene tree will then be generated for each UCE locus in the reduced dataset using IQ-TREE, with branch supports obtained using UFboot and SH-aLRT. All branches with less than 10% will be collapsed (Zhang et al. 2018). Gene trees will be used to estimate a species tree with ASTRAL-III (Rabiee et al. 2019). For species that do not form monophyletic groups, individuals will be left as operational taxonomic units (OTUs) rather than categorizing individuals by species (will not use the -a flag option). 

Divergence times will be estimated from the UCE data using the program MCMCTree (Yang and Rannala 2006), in PAML v4.9j (Yang 2007). Node ages will be calibrated using a set of eight fossils and three additional outgroups as in Mills et al. 2023 Table 1. The UCE 75% complete alignment will be used as the input for the MCMCTree and tree topology will be fixed to the result of the 75% complete matrix. The root of the tree will be constrained to a minimum age of 40.4 Ma (based on the oldest known sciurid fossil, _Douglassciurus oaxacensis_; Ferusquia-Villafranca et al. 2018) and a maximum age of 56 Ma (based on _Acritoparamys_, te oldest stem member of Sciuromorpha; Ivy, 1990; Korth 1994). All other fossils used in Mills et al. 2023 will be used to place minimum dates on internal nodes. MCMCTree analysis will be completed with a two-step approach, established by dos Reis et al. 2012, and outlined in Mills et al. 2023. 

**Works Cited**
Armitage, K.B., 1981. Sociality as a life-history tactic of ground squirrels. _Oecologia_ 48, 36–49.

Arnold, W., 1992. Adaptation to the cold. The physiology of marmot hibernation. Proceedings of the 1st international 
symposium on Alpine marmot and genera _Marmota_, Turin, 31-40.

Anisimova M., Gil M., Dufayard J. F., Dessimoz C., Gascuel O. 2011. Survey of branch support methods demonstrates accuracy, power, and robustness of fast likelihood-based approximation schemes. _Systematic Biology_, 60, 685–699.

Bai, L., Liu, B., Ji, C., Zhao, S., Liu, S., Wang, R., Wang, W., Yao, P., Li, X., Fu, X., Yu, H., 2019. Hypoxic and cold adaptation insights from the Himalayan marmot genome. _iScience_, 11, 519–530.

Barash, D.P., 1974. The evolution of marmot societies: a general theory. _Science_, 185, 415–420.

Ferrusquia-Villafranca, I., Flynn, L.J., Ruiz-Gonzalez, J.E., Torres-Hernandez, J.R., Martinez-Hernandez, E., 2018. New Eocene rodents from northwestern Oaxaca, southeastern Mexico, and their paleobiological significance. J. _Vertebrate Paleontology_, 38, 1514615.

Hafner, D.J., 1984. Evolutionary relationships of the Nearctic _Sciuridae_. In: Murie, J.O., Michener, G.R. (Eds.), The Biology of Ground-Dwelling Squirrels. University of Nebraska Press.

Hoang, D. T., Chernomor, O., von Haeseler, A., Minh, B. Q., Vinh, L. S., 2017. UFBoot2: Improving the ultrafast bootstrap approximation. _BioRxiv_, 35, 518–522.

Ivy, L.D., 1990. Systematics of Late Paleocene and Early Eocene _Rodentia_ (_Mammalia_) from the Clarks Fork Basin, Wyoming. Contributions from the Museum of Paleontology, University of Michigan 28, 21–70.

Kerhoulas, N. J., Arbogast, B. S. 2010. Molecular systematics and Pleistocene biogeography of Mesoamerican flying squirrels. _Journal of Mammalogy_, 91, 654–667. 

Korth, W.W., 1994. The Tertiary record of rodents in North America. In: _Topics in Geobiology_, vol. 12. Springer Science & Business Media.

Krysť ufek, B., Vohraliḱ , V., 2013. Taxonomic revision of the Palaearctic rodents (_Rodentia_). Part 2. Sciuridae: _Urocitellus_, _Marmota_ and _Sciurotamias_. _Lynx series nova_, 44, 27–138

Mills, K. K., Everson, K. M., Hildebrandt, K. P. B., Brandler, O. V., Steppan, S. J., Olson, L. E. 2023. Ultraconserved elements improve resolution of marmot phylogeny and offer insights into biogeographic history. _Molecular Phylogenetics and Evolution_, 107785. 

Nguyen, L.-T., Schmidt, H. A., Von Haeseler, A., Minh, B. Q. 2015. IQ-TREE: A Fast and Effective Stochastic Algorithm for Estimating Maximum-Likelihood Phylogenies. _Molecular Biology and Evolution_, 32, 1, 268–274. 

Rabiee, M., Sayyari, E., Mirarab, S. 2019. Multi-allele species reconstruction using ASTRAL. _Molecular Phylogenetics and Evolution_, 130, 286–96.

dos Reis M., Inoue J., Hasegawa M., Asher R.J., Donoghue P.C., Yang Z. Phylogenomic datasets provide both precision and accuracy in estimating the timescale of placental mammal phylogeny. Proc Biol Sci. 2012 Sep 7; 279(1742): 3491-500. 

Tagliacollo, V. A., Lanfear, R. 2018. Estimating improved partitioning schemes for ultraconserved elements. _Molecular Biology and Evolution_, 35, 1798–1811.

Yang, Z., Rannala, B., 2006. Bayesian estimation of species divergence times under a molecular clock using multiple fossil calibrations with soft bounds. _Molecular Biology and Evolution_, 23, 212–226.

Yang, Z., 2007. PAML 4: phylogenetic analysis by maximum likelihood. _Molecular Biology and Evolution_, 24, 1586–1591.

Zhang, Y. M., Williams, J. L., Lucky, A. 2019. Understanding UCEs: A comprehensive primer on using ultraconserved elements for arthropod phylogenomics. _Insect Systematics and Diversity_, 3, 1–3.
