---
title: "Metabolomics workshop"
teaching: 15 min
exercises: 75 min
questions:
- "How can I evaluate the similarity between MS spectra?"
objectives:
- "Understand how GNPS molecular networks work."
- "Use raw mzML metabolomic data for annotation."
- "Visualize and explore molecular networks"
keypoints:
- "Data is generated using Liquid Chromatography coupled to a tandem mass spectrometer (LC-MS/MS or MS2)."
- "Dereplication is the process of identifying previously known compounds."
- "Molecular networking is a computational method that organizes MS2 data based on spectral similarity, allowing us to infer relationships between chemical structures"
- "Feature-Based Molecular Networking (FBMN) enhances classical molecular networking by integrating relative quantitative data, enabling more robust metabolomics statistical analysis."
---

## Introduction

In the previous sections, we explored the biosynthetic potential of various strains by analyzing the BGCs within their genomes. We utilized BiG-SCAPE to create BGC networks, which compare all the BGCs detected by antiSMASH to determine their relatedness. 
Similarly, using metabolomics we can investigate the metabolites produced by selected strains in the laboratory. While crude extracts can be made to analyze the metabolites of specific strains, it is also possible to study the metabolites present in complex samples, such as soil, marine environments, host organisms, or stool samples.
There are two approaches to annotating metabolomics data. The first comprises using the information obtained by LC-MS, comparing the exact mass and UV spectra of each detected metabolite through natural product databases.
The introduction of the global natural products social molecular networking [GNPS](https://gnps.ucsd.edu/ProteoSAFe/static/gnps-splash.jsp) platform for molecular networking (M. Wang et al., 2016), significantly influenced dereplication techniques. Molecular networking groups metabolites into molecular families (MFs), thereby improving the annotation process of unknown metabolites.

<a href="/Figs/Molecular-network.png">
  <img src="/Figs/Molecular-network.png" alt="GNPS output can be directly visualized in the GNPS webpage, or using other visualization tools such as [Cytoscape](https://cytoscape.org/) " />
</a>

## Creating a GNPS account

Before starting this tutorial, it will be useful to have a GNPS account. For that go to the 
[GNPS](https://gnps.ucsd.edu/ProteoSAFe/static/gnps-splash.jsp) webpage 
and select Create a new account.
<a href="/Figs/create_GNPSaccount.jpg">
  <img src="/Figs/create_GNPSaccount.jpg" alt="Create an account in GNPS" />
</a>

Then fill in the following information: 
  -Username	
  -Name	
  -Organization	
  -Email	
  -Password
Wait for a confirmation email, and you now have a GNPS account.

Reference: Wang, M., Carver, J., Phelan, V. et al. Sharing and community curation of mass spectrometry data with Global Natural Products Social Molecular Networking. Nat Biotechnol 34, 828–837 (2016). https://doi.org/10.1038/nbt.3597

## Download MZMine v3.9
First, go to the MZMine 3.9 release
[MZMine 3.9](https://github.com/mzmine/mzmine/releases/tag/v3.9.0)

Select the installable file depending on your computer

<a href="/Figs/Download_MZMine.jpg">
  <img src="/Figs/Download_MZMine.jpg" alt="MZmine 3, an MS data analysis platform " />
</a>

Double-click on the file, and install the software

Reference: Schmid, R., Heuckeroth, S., Korf, A. et al. Integrative analysis of multimodal mass spectrometry data in MZmine 3. Nat Biotechnol 41, 447–449 (2023). https://doi.org/10.1038/s41587-023-01690-2

## Download the metabolomics dataset

First, we need to go to Zenodo and download all the mzML raw data collected from the described strains. 

https://zenodo.org/api/records/13352458/files-archive

After downloading the compressed file, we need to decompress it and store the files in a folder on our computer. 

## The dataset

This data was collected from crude extracts from two marine *Streptomyces*: *Streptomyces* sp. H-KF8, and *Streptomyces* sp. Vc74B-19. 
Two media were used, ISP2 and ISP2 prepared with artificial seawater (ASW), to evaluate the effect of replicating the natural environment from which these strains were isolated. 

<a href="/Figs/Datasets.png">
  <img src="/Figs/Datasets.png" alt="Data collection from *Streptomyces* sp. H-KF8, and *Streptomyces* sp. Vc74B-19." />
</a>

We downloaded 18 LC-MS/MS-derived files in mzML format. This data was collected by Dr. Mauricio Caraballo-Rodriguez in the Dorrestein Lab, at the University of California San Diego.
There are files from each strain, in ISP2 and ISP2-ASW, besides the crude extracts from the culture media. The data is in triplicates.

Besides mzML files, there is a file metadata_table.tsv, that contains all the relevant information from this dataset. 
Includes the names of the samples, relevant data collection, and taxonomic information. 

In addition, there is information relevant to the analysis, such as the names of the strains, the media used for culturing, and the antimicrobial activity. All this information is included in the format ATTRIBUTE_*

<a href="/Figs/Metadata.jpg">
  <img src="/Figs/Metadata.jpg" alt="Data collection from *Streptomyces* sp. H-KF8, and *Streptomyces* sp. Vc74B-19." />
</a>

At last, there is a file named MZMine_FBMN_batch.xml that collects all the information necessary for the analysis using MZMine

** Analysis using MZMine

1. Load batch file

Open MZMine3, and click on "Open", and then in "Batch Mode
<a href="/Figs/batch_01.jpg">
  <img src="/Figs/batch_01.jpg" alt="Load batch file" />
</a>

Here you should select load, and search for your downloaded files on your computer. Then select the MZMine_FBMN_batch.xml file
In confirmation, you should select Replace the batch steps.

<a href="/Figs/batch_02.jpg">
  <img src="/Figs/batch_02.jpg" alt="Load batch file" />
</a>

Then double-click on import MS data

<a href="/Figs/batch_03.jpg">
  <img src="/Figs/batch_03.jpg" alt="Load batch file" />
</a>

Select from your computer the 18 mzML files from this dataset

<a href="/Figs/batch_04.jpg">
  <img src="/Figs/batch_04.jpg" alt="Load batch file" />
</a>

After this, every file should be included in the batch-processing mode. Select OK afterwards so the files begin to process in the meantime.

<a href="/Figs/batch_05.jpg">
  <img src="/Figs/batch_05.jpg" alt="Load batch file" />
</a>







In the future it will include:
https://www.tfleao.com/general-8, 
[Paired omics](https://pairedomicsdata.bioinformatics.nl/)
[GNPS](https://gnps.ucsd.edu/ProteoSAFe/static/gnps-splash.jsp)

{% include links.md %}
