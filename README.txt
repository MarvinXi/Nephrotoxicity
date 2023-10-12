Unveiling the mechanisms of nephrotoxic compounds-induced nephrotoxicity through toxicological network analysis

*PIPLINE FOR THE  TOXICOLOGICAL NETWORK ANALYSIS*

#PREPARATION#
localization.py
separation.py
interactome.tsv
Compound targets.txt (eg: Matrine.txt)
Disease genes.txt (eg: Tubular Necrosis.txt)

#REQUIREMENT# 
The packages should operate on Python versions no less than 2.4.
The NetworkX and NumPy are indispensable for the packages' working.
The number of  Compound targets or Disease genes should be a minimum of 25.
The Compound targets or Disease genes must be arranged in one column in the form of Gene ID.

#COMMAND#
(1) python localization.py -g Compound targets.txt
(2) python localization.py -g Disease genes.txt 
(3) python separation.py --g1 Compound targets.txt --g2 Disease genes.txt 
(4) python localization.py -g Compound targets and Disease genes.txt

#USAGE#
(1) The collected disease genes or composite targets are organized into two files: Compound targets.txt and Disease genes.txt.
(2) Python localization.py is employed [see #COMMAND(1)(2)#] to test whether modules constructed by Disease genes or Compound targets are significantly distributed in the human interactome.
(3) Only when the p-value and the lcc size S of the modules are less than 0.05 and significantly greater than the random expected LCC [rand], respectively, will the modules be retained.
(4) Python separation.py [see #COMMAND(3)#] is utilized to calculate the shortest path length (dis ab) between compound targets and disease genes for each significantly distributed compound module and disease module.
(5) Compound targets and disease genes belonging to significantly distributed modules are organized into Compound targets and Disease genes.txt (eg: Matrine-Tubular Necrosis.txt).
(6) Python localization.py is employed [see #COMMAND(4)#] to project compound targets and disease genes belonging to significantly distributed modules into the human interactome to construct compound targets-disease genes networks. 
(7) Only when the p-value and the lcc size S of the networks are less than 0.05 and significantly greater than the random expected LCC [rand], respectively, will the networks be retained.
(8) For the significantly distributed networks, nodes in the core gene set with dis ab ¡Ü 1 are subject to further GO annotations and KEGG functional enrichment analysis.

#REFERENCE#
(1) Menche, J, Sharma, A, Kitsak, M, Ghiassian, SD, Vidal, M, Loscalzo, J, et al. (2015). Disease networks. Uncovering disease-disease relationships through the incomplete interactome. Science 347: 1257601.
(2) Dai, W, Tang, T, Dai, Z, Shi, D, Mo, L, and Zhang, Y (2020). Probing the Mechanism of Hepatotoxicity of Hexabromocyclododecanes through Toxicological Network Analysis. Environ Sci Technol 54: 15235-15245.