**Matthew Morassutti** 
**BIOL 550 SPR'24 Project** 
**Final Report**

**Title:**
Resolving the divergence times of _Marmota_ using Ultraconserved Elements

**_NOTE_** Files were too large to upload to GitHub. Find all files used as input data on Google Drive at the link below: 
https://drive.google.com/drive/folders/1Pbm9jUuTzk7BnbZsyBBpceDEt0-SzYdO?usp=sharing

**Question and Relevance**

This project will aim to unravel the evolutionary history of marmots (_Marmota sp._) by addressing their phylogenetic relationships. By using ultraconserved elements (UCEs) from all 15 extant marmot species, this project will pinpoint the diversification of marmots by providing a time calibrated phylogeny for the genus and 10 other taxa. The relevance of this project lies in understanding how marmots rapidly diversified during the Pleistocene in response to a changing climate in the cold, seasonal environments of the Holarctic. 

By improving our understanding of evolutionary dynamics in response to past environmental changes I will inform our understanding of species' responses to ongoing climate change and alterations to habitat. This helps us to better conserve these species by helping us know species relationships and cryptic diversity. I will also compare the results of this project’s analysis to those estimated by the study from which the dataset for this project was obtained to display how different analyses may yield different results. 

**Focal Organism Introduction**

Marmots (_Marmota sp._) are a genus of large-bodied ground squirrels known for their rapid diversification during the Pleistocene epoch (Kerhoulas _et al._ 2015). Adapted to survive harsh, cold winters, they inhabit a wide range of habitats across the Holarctic region, from North America to the European Alps (Figure 1, Barash 1974, Armitage 1981, Arnold 1992, Krysťufek and Vohraliḱ 2013). Despite their broad geographic distribution and occupation of a variety of habitats and elevations, marmots show relatively little morphological evolution since their radiation, indicating a high degree of conservatism in their body plan (Hafner 1984). Their ecological versatility allows them to occupy various elevations and biomes, from sea level to high-altitude, hypoxic conditions (Bai _et al._ 2019). They are usually associated with rocky slopes, meadows, and steppes (Bai _et al._ 2019). Marmots have been the subject of biological research due to their diverse social organizations, making them valuable models for understanding social behaviors in response to environmental challenges (Barash 1974).

Marmots belong to the tribe Marmotini, commonly known as ground squirrels, and the subtribe Marmotina, which contains the two extant genera _Marmota_ and _Cynomys_. The Marmotini tribe contains the subtribes Tamiina, Marmotina, Spermophilina, and seven basal and _incertae sedis_ genera (Herron _et al._ 2004). 

![FIgure1_Map](https://github.com/mmorassutti/biol550_project/assets/160165592/754fd5d0-e26a-4f1c-95ab-336c0263c1f0)
**Figure 1.** Map of candidate representatives from all 15 extant species of _Marmota_ included in the dataset obtained from authors of Mills _et al._ 2023.

**Methods Overview**

For this project, a concatenated supermatrix of UCE loci from 51 candidates representing all 15 extant species of _Marmota_ was obtained from researchers who completed the analysis shown in Mills et al. 2023. This supermatrix also contained UCE data from 10 outgroups. These outgroups are sourced from candidates representing family Aplodontiidae (_Aplodontia rufa_), family Gliridae (_Glis glis_, _Graphiurus murinus_, and _Mucardinis avellanarius_), members of subfamily Sciurinae from family Sciuridae (_Sciurus carolinensis_, _Sciurus vulgaris_), a member of tribe Xerini which is sister to tribe Marmotini (_Xerus inauris_), a member of subtribe Spermophilina of trine Marmotini (_Ictidomys tridecemlineatus_), a basal genus of Marmotini (_Urocitellus parryii_), and a genus within the same subtribe Marmotina as _Marmota_ (_Cynomys gunnisoni_). These data were shared by the authors of Mills et al. 2023 in a concatenated supermatrix of 75% of UCE  loci from these genomes, which removes any loci that were not present in at least 75% of the OTUs in the dataset.

To prepare the 75% supermatrix from Mills et al. 2023, researchers partitioned UCE reads for Marmots using the entropy-based method SWSC-en, designed specifically for UCE Loci (Tagliacollo and Lanfear, 2018). For this project, a list of UCE loci and their respective number of parsimony-informative sites was obtained in phyluce 1.7.3 using the _'phyluce_align_get_informative_sites'_ script (Faircloth 2016). The list of UCE loci were sorted in Excel based on the number of parsimony-informative sites, and the top 10% of loci were selected for use in this analysis. Maximum likelihood trees were estimated for the concatenated dataset using IQ-TREE (Nguyen _et al._ 2015) with branch supports obtained using the ultrafast bootstrap method (UFboot; Hoang _et al._ 2017) and the SH-like approximate likelihood ratio test (SH-aLRT; Anisimova _et al._ 2011), both with 1000 replicates. Researchers in Mills _et al._ 2023 used PartitionFinder2 to consolidate and identify the best substitution model for each partition. For the purpose of this project, and due to limitations in computation power, the GTR+Γ substitution model (Yang 1994) was used for all loci in the data in IQ-TREE. 

The maximum-likelihood tree obtained for this project was compared to a phylogeny from the reference paper that was estimated using a coalescent-based method (Figure 5 in Mills _et al._ 2023, Figure 4 in this report).  Researchers sorted UCE loci by number of parsimony-informative sites using the _'phyluce_align_get_informative_sites'_ script, and the dataset was reduced to the top quartile of loci. A maximum-likelihood gene tree was then generated for each UCE locus in the reduced dataset using IQ-TREE (Nguyen _et al._ 2015), with branch supports obtained using UFboot (Hoang _et al._ 2017) and SH-aLRT (Anisimova _et al._ 2011). All branches with less than 10% were collapsed (Zhang _et al._ 2018). Gene trees will be used to estimate a species tree with ASTRAL-III (Rabiee _et al._ 2019). For species that did not form monophyletic groups, individuals were left as operational taxonomic units (OTUs) rather than categorizing individuals by species (did not use the -a flag option). 

Divergence times in Mills _et al._ 2023 were estimated from the UCE data using the program MCMCTree (Yang and Rannala 2006), in PAML v4.9j (Yang 2007). Node ages were calibrated using a set of eight fossils and three additional outgroups, all listed in Mills _et al._ 2023 Table 1. The UCE 75% complete alignment was used as the input for the MCMCTree and tree topology was fixed to the result of the 75% complete matrix. The root of the tree was constrained to a minimum age of 40.4 Ma (based on the oldest known sciurid fossil, _Douglassciurus oaxacensis_; Ferusquia-Villafranca _et al._ 2018) and a maximum age of 56 Ma (based on _Acritoparamys_, the oldest stem member of Sciuromorpha; Ivy 1990, Korth 1994). All other fossils used in Mills _et al._ 2023 were used to place minimum dates on internal nodes for the analysis of that study. MCMCTree analysis was completed with a two-step approach, established by dos Reis _ 2012, and outlined in Mills _et al._ 2023.

For this project, the time calibration was completed in R using the Analyses of Phylogenetics and Evolution package (_ape_; Paradis and Schliep 2019). Because of a polytomy at the base of the phylogeny formed by _Aplodontia rufa_, Gliridae, and Sciuridae, only four of the fossils from Mills _et al._ 2023 were used for the time calibration in this project. The fossils used in this project include _Palaeosciurus goti_ (Quercy, France; 28.4 Ma; _Xerus_ - Marmotini, McKenna and Bell 1997), _Miospermophilus_ (Colorado, USA; 16.0 Ma; _Spermophilus_ - _Marmota_; Black 1963), _Marmota bobak_ (Kantemirovka, Russia; 0.5 Ma; _M. bobak_ - _M. baibacina_; Gromov _et al._ 1965, Erbajeva and Alexeeva 2009), and _Marmota marmota_ (Castile, Spain;	1.2 Ma; _M. marmota - sister clade; Gil and Sesé 1991). The ML tree was loaded in R using the _‘read.tree’_ function in _ape_. The placement on nodes for these fossils was determined using Mills _et. al_ 2023 Figure 7 (Figure 5 in this report) as a reference and the _‘get.MRCA’_ function in _ape_, giving the most visually similar node placement for these fossils to the reference species tree as possible. Node age estimates were obtained from these fossils using the _‘chronopl’_ function in _ape_, which uses a semi-parametric method based on penalized likelihood (Sanderson 2002). In _‘chronopl’_ a smoothing parameter of 1 was used, minimum ages were set to the minimum ages of fossils listed above, maximum ages were arbitrarily set to ages 5 million years greater than the minimum ages, and both age parameters were concatenated with their respective node labels. The _‘write.tree’_ function in _ape_ was used to write a chronogram file, to which a scale bar and scale axis were added in FigTree (Rambaut 2018). 

**Results**

The 75% concatenated supermatrix obtained from researchers for Mills _et al._ 2023 consisted of 61 taxa and 1192 loci. This supermatrix was reduced to 61 taxa and 119 loci. This nexus file was used to obtain a cladogram with nodes labeled with bootstrap support values (Figure 2). Of the 58 nodes with bootstrap support values, 31 show a score of 100, 13 nodes showed scores from 90-99, 9 showed scores from 70-89, and 6 nodes showed scores from 50-69. The cladogram shown in Figure 2 has tip labels that include GenBank accession numbers or other labels for the taxa which were irrelevant to this analysis, so the taxa in the nexus file were re-labeled with numeric codes where there were multiple candidates for a species. A cladogram showing the taxonomic hierarchies was obtained, and shows some species with non-monophyletic sorting (Figure 3). The cladogram sorted _Aplodntia rufa_ monophyletically, with a node that shows a polytomy with Gliridae and Sciuridae, each forming expected clades. Sciuridae further sorted, as expected, into a clade formed the Marmotini tribe sister to genus _Xerus_. _Xerus_ formed a clade sister to the other sciurids in the dataset, _Sciurus carolinensis_ and _Sciurus vulgaris_. Marmotini was sorted into to two main clades, with the genus _Marmota_ forming a clade, and another clade formed by _Cynomys gunnisoni_, _Ictidomys tridecemlineatus_, and _Urocitellus parryii_. This clade shows _U. parryii_ as sister to a clade formed by _C. gunnisoni_, and _I. tridecemlineatus_, which conforms with the latter two’s position shown in a cladogram obtained through maximum parsimony analysis (Helgen _et al._ 2009), and the species tree obtained in Mills _et al._ 2023 (Figure 4). This cladogram shows the subgenus _Petromarmota_ resolving as expected, with a clade of _Marmota_ containing all candidates from _M. caligata_, _M. flaviventris_, _M. olympus_, and _M. vancouverensis_.

![Figure2_bootstrapvalues](https://github.com/mmorassutti/biol550_project/assets/160165592/0cfdadfc-5a22-4e7d-b47d-174c068549c5)
**FIgure 2.** A maximum-likelihood cladogram including bootstrap support values at nodes with tip labels showing candidate source obtained in IQ-TREE using the top 10% of loci from the 75% concatented supermatrix from authors of Mills _et al._ 2023. 

![Figure3_Cladogram](https://github.com/mmorassutti/biol550_project/assets/160165592/90e1bdc7-3b6c-4c4c-ae20-6fee7ee0634a)
**Figure 3.** A maximum-likelihood cladogram including bootstrap support values at nodes with tip labels showing candidate source obtained in IQ-TREE using the top 10% of loci from the 75% concatented supermatrix from authors of Mills _et al._ 2023.

Non-monophyletic sorting occurred for three species: _M. baibacina_, _M. caligata_, and _M. himalayana_, seen in Figure 3. Two candidates were labeled as _M. baibacina_, with one candidate, Marmota_baibacina_01, placed sister to the clade formed by the candidates representing _M. menzbieri_, and the other candidate, Marmota_baibacina_02, placed in a clade with the candidate representing _M. kastschenkoi_. Candidates representing _M. caligata_ were sorted into multiple clades within subgenus _Petromarmota_. The candidate Marmota_caligata_10 was placed sister to the clade formed by the candidates representing _M. olympus_, with these taxa comprising a clade sister to the candidate Marmota_caligata_09. The candidates Marmota_caligata_01 through _06 formed a clade sister to the candidates representing _M. vancouverensis_, with these taxa forming a clade sister to the candidates Marmota_caligata_07 and _08. The four candidates representing _M. himalayana_ were grouped into two separate clades of genus _Marmota_. The candidates Marmota_himalayana_02 through _04 were placed in a clade sister to the candidate representing _M. caudata_, while the candidate Marmota_himalayana_01 was placed sister to the clade formed by the candidates representing _M. bobak_.

![Figure4_MillsSpeciesTree](https://github.com/mmorassutti/biol550_project/assets/160165592/ddbe97c6-a998-4ffb-8829-cbff40b2df52)
**Figure 4.** A maximum likelihood species tree from Mills _et al._ 2023 estimated with coalescent-based methods using gene trees from each UCE loci present in 75% of taxa in their dataset and the mitogenomes from these taxa. 

The chronogram obtained through a calibration completed with four fossils and a penalized likelihood method may be seen in Figure 5. This chronogram will be compared to that obtained using 8 fossils and with Bayesian methods, which is labeled as Figure 6 in this report (Figure 7 in Mills _et al._ 2023). The chronogram obtained from penalized likelihood analysis for this project the divergence time of tribe Marmotini from tribe Xerini at 30.9 million years ago (Ma), while this divergence time from the chronogram obtained from Bayesian analysis estimated this divergence time at 35.0 Ma (95%confidence interval (C.I.) = 33.8–36.7). The penalized likelihood analysis estimated the divergence of _Marmota_ from other members of Marmotini at 18.4 Ma, while Bayesian analysis estimated this divergence at 16.3 Ma (95% C.I. = 13.7–18.8). Penalized likelihood analysis estimated the divergence of subgenus _Petromarmota_ from other members of _Marmota_ at 15.5 Ma, while Bayesian analysis estimated this divergence at 5.71 Ma (95% C.I. = 3.95–7.62). For the crown diversification within _Petromarmota_, this project’s analysis estimated this to occur 13.2 Ma, however the estimation by Bayesian analysis estimated this to have occurred 2.31 Ma (95% C.I. = 2.62–3.11). Finally, this project’s analysis estimated the crown diversification of other members of _Marmota_, in the subgenus _Marmota_, to have occurred 12.5 Ma, while Bayesian analysis estimated this radiation to have occurred 3.57 Ma (95% C.I. = 2.45–4.72). 

![Figure5_Chronogram.png
](https://github.com/mmorassutti/biol550_project/blob/ef8ae623a0b93843b90c246fc2ff551a83d6ed3b/Figure5_Chronogram.png)
**Figure 5.** A chronogram estimated using the cladogram seen in Figure 3. Time calibration was estimated using penalized likelihood and four fossils. Labeled points correspond with the following fossils: A - _Palaeosciurus goti_, B - _Miospermophilus_, C - _Marmota marmota_, D - _Marmota bobak_.

![Figure6_MillsChronogram](https://github.com/mmorassutti/biol550_project/assets/160165592/be1088f6-a744-4c26-821d-3f12e1bf9ddb)
**Figure 6.** A chronogram from Mills _et al._ 2023 estimated with Bayesian methods and eight fossils. 

The chronogram from Mills et al. 2023 (Figure 6) also placed the more basal nodes of the tree at much younger ages than that which were obtained with fewer fossils and with penalized likelihood. In the time-calibrated tree obtained through the analysis for this project estimated the divergence of _A. rufa_ from the other members of order Rodentia at 100.2 Ma, while the chronogram from Mills _et al._ 2023 estimated this divergence time at 51.1 Ma (95% C.I. = 58–42). The divergence time of subfamily Xerinae from other sciurids estimated by penalized likelihood was estimated at 65.5 Ma, while Bayesian methods estimated this divergence at 39.4 Ma (95% C.I. = 40.5–38).

**Discussion**

It is clear that methods have a considerable impact on the results of analysis. The dataset for this project included outgroups and ingroup taxa that were not included in the final results of Mills _et al._ 2023. Furthermore, for this analysis the original dataset was reduced to only 10% of the loci used by the authors from the reference paper.The trees used in the reference paper were obtained through coalescent methods of combining UCE loci and mitogenomes to generate a maximum-likelihood species tree, with maximum-likelihood gene trees estimated for each UCE loci that determined the most appropriate substitution model for each of these loci. The trees for this project were obtained through a concatenated alignment of only 10% of UCE loci from the reference paper’s supermatrix, using the GTR+Γ substitution model for the entire dataset. Also, only half of the fossils used for time calibration by the authors of the reference paper were included in the analysis for this project. Finally, the time calibration for this project was completed with penalized likelihood methods, while authors of the reference paper completed their time calibration with Bayesian methods. These decisions that led to these differences were made due to limitations on the time, programs, and computational power available for this project. Though the results summarized in this paper are considerably different from that of Mills _et al._ 2023, there are many consistencies, and information that may still be gleaned from the limited analysis from this project alone.

The topology of the cladogram shows unambiguous sorting of Palearctic (old world) and Nearctic species of _Marmota_. All members of the subgenus _Petromarmota_ are found in their own clade, and Nearctic species of subgenus _Marmota_, the American woodchuck (M. monax) and the Alaska marmot (M. broweri), are paraphyletic to the Palearctic species of this subgenus (Figure 3). The intermittent presence of the Bering Land Bridge beginning at the onset of the Miocene and again 5-10 Ma facilitated the migration of terrestrial species across the boundary of the Palearctic and Nearctic (Elias _et al._ 1996, Hopkins 1959, Sher 1999). Further analysis would be needed to discern directionality of this movement, however, the timing of potential dispersals and following isolation for the Nearctic species of genus _Marmota_ are consistent with the timing of the presence of this corridor.   

The non-monophyletic sorting of _M. caligata_ (Figure 3) is consistent with that seen in the species tree from Mills _et al._ 2023 (Figure 4). Two candidates from this species formed a clade with _M. olympus_, while the rest formed a clade with _M. vancouverensis_. This aligns with the hypothesis from Mills _et al._ 2023 that there may be a cryptic species within _M. caligata_ in the region of the Cascade Mountains near Vancouver Island.

The non-monophyly seen in _M. himalayana_ (Figure 3) was not seen in the species tree estimated in Mills _et al._ 2023. This species only had three candidates in the reference paper (Figure 4), and the candidate that did not sort monophylically with the rest of the candidates for this species (Figure 3) does not appear to be included in the reference paper’s analysis. 

The non-monophyly of _M. baibacina_ is consistent with that seen in the species tree from Mills _et al._ 2023 (Figure 4). The two candidates from this species were sister to _M. menzbieri_ and _M. kastschenkoi_, respectively. Looking at the present ranges of these species (Figure 1), the formation of a clade by _M. baibacina_ and _M. kastschenkoi_ appears to be supported by their ranges, as these species are geographically adjacent. However, the ranges _M. baibacina_ and _M. menzbieri_ are separated by the range of _M. caudata_ so their formation of a clade does not seem as likely as the clade formed by _M. baibacina_ and _M. kastschenkoi_.

In summary, there are some issues with attempting to make conclusions about divergence times and cryptic species with a limited dataset and analysis. It is interesting that in many ways, the limited analysis employed for this project yielded results that were in many ways similar to that of the more robust analysis by Mills _et al._ 2023. This project provided valuable experience to its author in the methods of phylogenetic systematics, and in preparing data for these analyses. Given more time and aptitude with bioinformatics, the author of this project would have attempted to replicate the coalescent-based method outlined in the reference paper to improve the time calibration with the inclusion of more fossils in that part of the analysis. 


**Works Cited**
Armitage, K.B., 1981. Sociality as a life-history tactic of ground squirrels. _Oecologia_ 48, 36–49.

Arnold, W., 1992. Adaptation to the cold. The physiology of marmot hibernation. Proceedings of the 1st international symposium on Alpine marmot and genera _Marmota_, Turin, 31-40.

Anisimova M., Gil M., Dufayard J. F., Dessimoz C., Gascuel O. 2011. Survey of branch support methods demonstrates accuracy, power, and robustness of fast likelihood-based approximation schemes. _Systematic Biology_, 60, 685–699.

Bai, L., Liu, B., Ji, C., Zhao, S., Liu, S., Wang, R., Wang, W., Yao, P., Li, X., Fu, X., Yu, H., 2019. Hypoxic and cold adaptation insights from the Himalayan marmot genome. _iScience_, 11, 519–530.

Barash, D.P., 1974. The evolution of marmot societies: a general theory. _Science_, 185, 415–420.

Black, C.C., 1963. A review of the North American Tertiary Sciuridae. Bull. _Mus. Comp. Zool._ 130, 159–166.

Elias, S.A., Short, S.K., Nelson, C.H., Birks, H.H., 1996. Life and times of the Bering land bridge. _Nature_ 382, 60–63.

Erbajeva, M.A., Alexeeva, N.V., 2009. Pliocene-Recent Holarctic marmots: an overview. _Ethol. Ecol. Evol._ 22, 339–348.

Faircloth B.C. 2016. PHYLUCE is a software package for the analysis of conserved genomic loci. _Bioinformatics_ 32:786-788.

Ferrusquia-Villafranca, I., Flynn, L.J., Ruiz-Gonzalez, J.E., Torres-Hernandez, J.R., Martinez-Hernandez, E., 2018. New Eocene rodents from northwestern Oaxaca, southeastern Mexico, and their paleobiological significance. _Vertebrate Paleontology_, 38, 1514615.

Gil, E., Sesé, C. 1991. Middle Pleistocene small mammals from Atapuerca (Burgos, Spain), Datation et Caractérisation des Milieux Pléistocenes. _Cahiers du Quaternaire_, 16, 337–347.

Gromov, I. M., Bibikov, D. I., Kalabuchov, N. I., Mejer, M. N. 1965. Fauna SSSR.: Mlekopitaiushchie. Nazemny‘e belich‘i (Marmotinae) [Mammals. Ground squirrels (Marmotinae)], Publishing house Nauka, Moscow-Leningrad.

Hafner, D.J., 1984. Evolutionary relationships of the Nearctic Sciuridae. In: Murie, J.O., Michener, G.R. (Eds.), The Biology of Ground-Dwelling Squirrels. University of Nebraska Press.

Helgen, K. M., Cole, F. R., Helgen, L. E., Wilson, D. E. 2009. Generic Revision in the Holarctic Ground Squirrel Genus _Spermophilus_. _Journal of Mammalogy_, 90, 270–305.

Herron, M. D., Castoe, T. A., Parkinson, C. L. 2004. Sciurid phylogeny and the paraphyly of Holarctic ground squirrels (_Spermophilus_). _Molecular Phylogenetics and Evolution_, 31, 1015–1030. 

Hoang, D. T., Chernomor, O., von Haeseler, A., Minh, B. Q., Vinh, L. S., 2017. UFBoot2: Improving the ultrafast bootstrap approximation. _BioRxiv_, 35, 518–522.

Hopkins, D.M., 1959. Cenozoic history of the Bering Land Bridge: The seaway between the Pacific and Arctic basins has often been a land route between Siberia and Alaska. _Science_, 129 , 1519–1528.

Ivy, L.D., 1990. Systematics of Late Paleocene and Early Eocene Rodentia (Mammalia) from the Clarks Fork Basin, Wyoming. Contributions from the Museum of Paleontology, University of Michigan 28, 21–70.

Kerhoulas, N. J., Arbogast, B. S. 2010. Molecular systematics and Pleistocene biogeography of Mesoamerican flying squirrels. _Journal of Mammalogy_, 91, 654–667.

Korth, W.W., 1994. The Tertiary record of rodents in North America. In: _Topics in Geobiology_, vol. 12. Springer Science & Business Media.

Krysťufek, B., Vohraliḱ , V. 2013. Taxonomic revision of the Palaearctic rodents (Rodentia). Part 2. Sciuridae: _Urocitellus_, _Marmota_ and _Sciurotamias_. _Lynx series nova_, 44, 27–138.

McKenna, M.C., Bell, S.K., 1997. Classification of Mammals: Above the Species Level. Columbia University Press.

Mills, K. K., Everson, K. M., Hildebrandt, K. P. B., Brandler, O. V., Steppan, S. J., Olson, L. E. 2023. Ultraconserved elements improve resolution of marmot phylogeny and offer insights into biogeographic history. _Molecular Phylogenetics and Evolution_, 107785.

Nguyen, L.T., Schmidt, H. A., Von Haeseler, A., Minh, B. Q. 2015. IQ-TREE: A Fast and Effective Stochastic Algorithm for Estimating Maximum-Likelihood Phylogenies. _Molecular Biology and Evolution_, 32, 1, 268–274.

Paradis E, Schliep K 2019. ape 5.0: an environment for modern phylogenetics and evolutionary analyses in R. _Bioinformatics_, 35, 526-528. 

Rabiee, M., Sayyari, E., Mirarab, S. 2019. Multi-allele species reconstruction using ASTRAL. _Molecular Phylogenetics and Evolution_, 130, 286–96.

Rambaut, A. 2018. Figtree ver 1.4.4. Institute of Evolutionary Biology, University of Edinburgh, Edinburgh. 

dos Reis M., Inoue J., Hasegawa M., Asher R.J., Donoghue P.C., Yang Z. Phylogenomic datasets provide both precision and accuracy in estimating the timescale of placental mammal phylogeny. Proc. Biol. Sci., 2012 Sep 7; 279(1742): 3491-500.

Sanderson, M. J. 2002. Estimating absolute rates of molecular evolution and divergence times: a penalized likelihood approach. _Molecular Biology and Evolution_, 19, 101–109.

Sher, A., 1999. Traffic lights at the Beringian crossroads. _Nature_, 397, 103–104.

Tagliacollo, V. A., Lanfear, R. 2018. Estimating improved partitioning schemes for ultraconserved elements. _Molecular Biology and Evolution_, 35, 1798–1811.

Yang Z. 1994. Estimating the Pattern of Nucleotide Substitution. _Journal of Molecular Evolution_, 39, 105–111.

Yang, Z., Rannala, B., 2006. Bayesian estimation of species divergence times under a molecular clock using multiple fossil calibrations with soft bounds. _Molecular Biology and Evolution_, 23, 212–226.

Yang, Z., 2007. PAML 4: phylogenetic analysis by maximum likelihood. _Molecular Biology and Evolution_, 24, 1586–1591.

Zhang, Y. M., Williams, J. L., Lucky, A. 2019. Understanding UCEs: A comprehensive primer on using ultraconserved elements for arthropod phylogenomics. _Insect Systematics and Diversity_, 3, 1–3.


**R Code**
#load package
library(ape)

#load tree
phylo <- read.tree(file="top10pconcat-1.nexus.contree")

##root tree
phy=root(phylo, outgroup = "Aplodontia_rufa", resolve.root = TRUE)

##get node labels for fossils
#Douglassciurus oaxacensis 	Oaxaca, Mexico 	40.4 	Sciuridae - Aplodontiidae 		Ferrusquia-Villafranca et al. 2018 NODE=62
getMRCA(phy, tip = c("Aplodontia_rufa", "sciurus_vulgaris")) 

#Plesiarctomys (Sciurus) spectabilis 	Egerkingen, Switzerland 	37.2 	Sciurus - other sciurids 		Costeur and Schneider, 2011 NODE=63
getMRCA(phy, tip = c("sciurus_vulgaris", "xerus_inaurus"))

#Palaeosciurus goti 		Quercy, France 	28.4 	Xerus - Marmotini 		McKenna and Bell 1997 NODE=64 
getMRCA(phy, tip = c("xerus_inaurus", "Cynomys_gunnisoni"))

#Miospermophilus 		Colorado, USA 	16.0 	Spermophilus - Marmota 		(Black, 1963) NODE=65
getMRCA(phy, tip = c("Cynomys_gunnisoni", "Marmota_flaviventris_04"))

#Marmota bobak 		Kantemirovka, Russia 	0.5 	M. bobak - M. baibacina 		Gromov et al. (1965); NODE=74 
getMRCA(phy, tip = c("Marmota_bobak_02", "Marmota_baibacina_01"))

#Marmota marmota 		Castile, Spain 	1.2 	M. marmota - sister clade 		Gil and Ses´e (1991) NODE=72
getMRCA(phy, tip = c("Marmota_marmota_01", "Marmota_baibacina_01"))

#Marmota himalayana 		Shanxi, China 	1.0 	M. himalayana - M. sibirica 	Gromov et al. 1965 NODE=80
getMRCA(phy, tip = c("Marmota_himalayana_02", "Marmota_sibirica_05"))

#Marmota monax 		Maryland, USA 	0.8 	M. monax - sister clade 		Kurten and Anderson (1980) NODE=69
getMRCA(phy, tip = c("Marmota_monax_02", "Marmota_broweri_02"))

##Run chronopl for each fossil
#Douglassciurus oaxacensis 	Oaxaca, Mexico 	40.4 	Sciuridae - Aplodontiidae 		Ferrusquia-Villafranca et al. 2018 NODE=62
chronopl(phy, lambda=1, age.min = c(40.4), age.max = c(45.4),node = c(62), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

#Plesiarctomys (Sciurus) spectabilis 	Egerkingen, Switzerland 	37.2 	Sciurus - other sciurids 		Costeur and Schneider, 2011 NODE=63
chronopl(phy, lambda=1, age.min = c(37.2), age.max = c(42.2),node = c(63), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

#Palaeosciurus goti 		Quercy, France 	28.4 	Xerus - Marmotini 		McKenna and Bell 1997 NODE=64 
chronopl(phy, lambda=1, age.min = c(28.4), age.max = c(33.4),node = c(64), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

#Miospermophilus 		Colorado, USA 	16.0 	Spermophilus - Marmota 		(Black, 1963) NODE=65
chronopl(phy, lambda=1, age.min = c(16), age.max = c(21),node = c(65), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

#Marmota bobak 		Kantemirovka, Russia 	0.5 	M. bobak - M. baibacina 		Gromov et al. (1965); NODE=74 
chronopl(phy, lambda=1, age.min = c(.5), age.max = c(5.5),node = c(74), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

#Marmota marmota 		Castile, Spain 	1.2 	M. marmota - sister clade 		Gil and Ses´e (1991) NODE=72
chronopl(phy, lambda=1, age.min = c(1.2), age.max = c(6.2),node = c(72), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

#Marmota himalayana 		Shanxi, China 	1.0 	M. himalayana - M. sibirica 	Gromov et al. 1965 NODE=80
chronopl(phy, lambda=1, age.min = c(1), age.max = c(6),node = c(80), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

#Marmota monax 		Maryland, USA 	0.8 	M. monax - sister clade 		Kurten and Anderson (1980) NODE=69
chronopl(phy, lambda=1, age.min = c(0.8), age.max = c(5.8),node = c(69), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

##Run chronopl for all fossils
chronopl(phy, lambda=1, age.min = c(40.4,37.2,28.4,16,0.5,1.2,1,0.8), age.max = c(45.4,42.2,33.4,21,5.5,6.2,6,5.8),node = c(63,64,65,74,72,80,69), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

chronopl(phy, lambda=1, age.min = c(37.2, 28.4, 16, .5, 1.2, 1, 0.8), age.max = 45.4,node = c(62, 63, 64, 65, 74, 72, 80, 69), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

?chronopl

#try again without rooting#####
phy1 <- read.tree(file="top10pconcat-1.nexus.contree")
##get node labels for fossils
####these didn't work####
#Douglassciurus oaxacensis 	Oaxaca, Mexico 	40.4 	Sciuridae - Aplodontiidae 		Ferrusquia-Villafranca et al. 2018 NODE=62
getMRCA(phy1, tip = c("Aplodontia_rufa", "sciurus_vulgaris")) 

#Plesiarctomys (Sciurus) spectabilis 	Egerkingen, Switzerland 	37.2 	Sciurus - other sciurids 		Costeur and Schneider, 2011 NODE=63
getMRCA(phy1, tip = c("sciurus_vulgaris", "xerus_inaurus"))

#Palaeosciurus goti 		Quercy, France 	28.4 	Xerus - Marmotini 		McKenna and Bell 1997 NODE=64 
getMRCA(phy1, tip = c("xerus_inaurus", "Cynomys_gunnisoni"))

####these did work####
#Miospermophilus 		Colorado, USA 	16.0 	Spermophilus - Marmota 		(Black, 1963) NODE=65
getMRCA(phy1, tip = c("Cynomys_gunnisoni", "Marmota_flaviventris_04"))

#Marmota bobak 		Kantemirovka, Russia 	0.5 	M. bobak - M. baibacina 		Gromov et al. (1965); NODE=74 
getMRCA(phy1, tip = c("Marmota_bobak_02", "Marmota_baibacina_01"))

#Marmota marmota 		Castile, Spain 	1.2 	M. marmota - sister clade 		Gil and Ses´e (1991) NODE=72
getMRCA(phy1, tip = c("Marmota_marmota_01", "Marmota_baibacina_01"))

#Marmota himalayana 		Shanxi, China 	1.0 	M. himalayana - M. sibirica 	Gromov et al. 1965 NODE=80
getMRCA(phy1, tip = c("Marmota_himalayana_02", "Marmota_sibirica_05"))

#Marmota monax 		Maryland, USA 	0.8 	M. monax - sister clade 		Kurten and Anderson (1980) NODE=69
getMRCA(phy1, tip = c("Marmota_monax_02", "Marmota_broweri_02"))

##Run chronopl for each fossil

#Miospermophilus 		Colorado, USA 	16.0 	Spermophilus - Marmota 		(Black, 1963) NODE=65
chronopl(phy1, lambda=1, age.min = c(16), age.max = c(21),node = c(65), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

#Marmota bobak 		Kantemirovka, Russia 	0.5 	M. bobak - M. baibacina 		Gromov et al. (1965); NODE=74 
chronopl(phy1, lambda=1, age.min = c(.5), age.max = c(5.5),node = c(74), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

#Marmota marmota 		Castile, Spain 	1.2 	M. marmota - sister clade 		Gil and Ses´e (1991) NODE=72
chronopl(phy1, lambda=1, age.min = c(1.2), age.max = c(6.2),node = c(72), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

#Marmota himalayana 		Shanxi, China 	1.0 	M. himalayana - M. sibirica 	Gromov et al. 1965 NODE=80
chronopl(phy1, lambda=1, age.min = c(1), age.max = c(6),node = c(80), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

#Marmota monax 		Maryland, USA 	0.8 	M. monax - sister clade 		Kurten and Anderson (1980) NODE=69
chronopl(phy1, lambda=1, age.min = c(0.8), age.max = c(5.8),node = c(69), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

chrono <- c(chronopl(phy1, lambda=1, age.min = c(16), age.max = c(21),node = c(65), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500),chronopl(phy1, lambda=1, age.min = c(.5), age.max = c(5.5),node = c(74), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500),chronopl(phy1, lambda=1, age.min = c(1.2), age.max = c(6.2),node = c(72), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)
            ,chronopl(phy1, lambda=1, age.min = c(1), age.max = c(6),node = c(80), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500),
            chronopl(phy1, lambda=1, age.min = c(0.8), age.max = c(5.8),node = c(69), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)
)

plot(chrono)

#concatenating the individual chronopl functions worked, but created individual plots, didn't combine results into one tree
#running this as above with the fossils that worked for the unrooted tree didn't work
chronopl(phy1, lambda=1, age.min = c(37.2, 28.4, 16, .5, 1.2, 1, 0.8), age.max = 45.4,node = c(62, 63, 64, 65, 74, 72, 80, 69), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)


#try running chrnpl with the xerus and marmotini, save calibrated tree in figtree and exprt in image in ppt and label clades
#Palaeosciurus goti 		Quercy, France 	28.4 	Xerus - Marmotini 		McKenna and Bell 1997 NODE=64 
Marmotini <- chronopl(phy, lambda=1, age.min = c(28.4), age.max = c(33.4),node = c(64), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

#Miospermophilus 		Colorado, USA 	16.0 	Spermophilus - Marmota 		(Black, 1963) NODE=65
Marmota <- chronopl(phy, lambda=1, age.min = c(16), age.max = c(21),node = c(65), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

#Xerus-Marmotini & Spermophilus-Marmota
Combo <- chronopl(phy, lambda=1, age.min = c(16,28.4), age.max = c(21,33.4),node = c(65,64), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)

#plot the final chronograms
pMarmotini <- plot(Marmotini)
pMarmta <- plot(Marmota)
pCombo <- plot(Combo)

pCombo <- plot.phylo(Combo,use.edge.length = TRUE, show.tip.label = TRUE, show.node.label = FALSE)
add.scale.bar(pCombo)

write.nexus(Combo,file = "pCombo_chronogram.nexus")
write.tree(Combo, file = "pCombo_chronogram.treefile")

#unrooted tree for scaled plot in figtree since figtree can't open the rooted tree
#Xerus-Marmotini & Spermophilus-Marmota
Combo1 <- chronopl(phy1, lambda=1, age.min = c(16,28.4), age.max = c(21,33.4),node = c(65,64), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)
write.tree(Combo1, file = "pCombo1_chronogram.treefile")


#unrooted tree with Marmota fossils, this is the script for the chronogram used in in the report 
Combo2 <- chronopl(phy1, lambda=1, age.min = c(0.5,1.2,16,28.4), age.max = c(5.5,6.2,21,33.4),node = c(74,72,65,64), S = 1, tol = 1e-8,CV = FALSE, eval.max = 500, iter.max = 500)
write.tree(Combo2, file = "pCombo2_chronogram.treefile")



