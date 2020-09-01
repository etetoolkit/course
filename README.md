# Reconstruction, analysis, and visualization of phylogenomic data with the ETE Toolkit


# Course Presentation
Welcome to the hands-on ETE Toolkit Phylogenomics practical course!

This document and the attached repository are intended to provide a practical guided tour covering most important features in the ETE Toolkit. For this, we use a fake biological dataset, so all examples and exercises are motivated by biological questions. You can see this course as a support material to the already available technical ETE documentation: 

- [ETE tutorial](http://etetoolkit.org/docs/latest/tutorial/index.html)
- [ETE reference guide](http://etetoolkit.org/docs/latest/reference/index.html)
- [ETE Tools documentation](http://etetoolkit.org/documentation/tools/)
- [ETE Tool cookbooks](http://etetoolkit.org/cookbook)


The course is divided into several sections organized by notebooks under the `nb/` folder. Each section represents a common phylogenomic question and covers different aspects of the ETE toolkit. 

All necessary data to run the exercise is in `data.tar.gz`. You should decompress the file in the root directory of this repository. 

IMPORTANT: Note that data used in this course is manually manipulated to ensure the expected results **Do not use it for real work!**

To start practicing you just need to: 
- [Setup the environment](Environment setup)


# Full Exercise

After many years of work, your lab has just isolated and sequenced a very interesting strain of the Aquifex aeolicus bacterium. This strain possesses a remarkable resistance to sulfur-rich environment. 

To investigate it further, you decide to address an in depth phylogenomic study where your strain is analyzed in the context of other known sulfur-related organisms and reference species.

Start a black notebook and try to work on the tasks proposed in the following notebooks: 

| Topic  | Tasks  | ETE features  | 
|---|---|---|
| [Preparing Genomic data ](nb/00-preparing_genomic_data)  |  General advides  |   None |
| [Building gene families](nb/01-building_gene_families)  |  clustering homologous sequences  |  Tree basics, ete-build, ete-view |
| [Building gene phylogenies](nb/02-building_gene_phylogenies)  |  building and handling phylogenetic gene tree |  Tree basics, ete-build, ete-view |
| [Building Concatenated species trees](nb/03-building_concat_species_trees)  |  building contatenated species trees   |  ete-build supermatrix, PhyloTree collections |
| [Comparing trees](nb/04-comparing_trees)  |  Comparing tree topologies  |  ete-compare, Tree.compare |
| [Linking trees to alignments](nb/05-linking_trees_and_alignments)  |  binding MSAs and  PhyloTrees  |  SeqGroup, PhyloTree |
| [Testing selection](nb/06-testing_selection)  |  Testing evolutionary hypothesis  |  ete-evol, codeml, visualization |
| [Predicting evolutionary events](nb/07-predicting_evol_events)  | Duplication and Speciation event detection  |  Rooting, Standardizing, evol events |
| [Linking to NCBI taxonomy](nb/08-linking_to_NCBI_taxonomy)  |  Querying NCBI taxonomy  |  ete-ncbiquery, NCBITaxa, Tree.annotate_ncbi_taxa |
| [Annotation trees](nb/09-annotating_trees)  |  NA  |  NA |
| [Programmatic visualization](nb/10-programmatic_visualization)  | Custom visualization  |  tree.render, TreeStyle, NodeStyle, Faces |



# Environment setup

this tutorial requires the following: 
- git (to clone and update this repository)
- Python 3.6 (for full compatibility, avoid 3.7 and 3.8)
- ete3 3.1.2 (Install lastest from etetookit conda channel, other channels might not be updated.
- ete_toolchain (install from etetoolkit conda channel)
- jupyter notebook and nbextensions


- The recipe to obtain a clean environment to follow all steps bellow:


## Clone this repository (git required)
```
# makes a separate dir for this course and enter it
mkdir etecourse/
cd etecourse/

# clone this repository
git clone https://github.com/etetoolkit/course
```

## Install and initialize miniconda 

- You can skip this step if you already have a conda env and know how to use it
- Rembember to initialize your conda env. i.e. the Miniconda installation script will ask you about this. 
```
Do you wish the installer to initialize Miniconda3
by running conda init? [yes|no]
[no] >>> yes
```

### Linux
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh -p ~/eteconda/
```

### OSX
```
curl https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh > Miniconda3-latest-MaxOSX-x86_64.sh
bash Miniconda3-latest-MaxOSX-x86_64.sh -p ~/eteconda/
```


## Create a conda environment for this course with all dependencies

1. open a new shell (IMPORTANT!), so you have your new conda env initialized.
2. Then create an enviroment to run this tutorial.

```
conda env create -f course/REQUIREMENTS_conda.yml
conda activate etecourse
```

## Install latest ete3
```
pip install ete3
```


## uncompress necessary data and start jupyter
```
# Enter data directory and uncompress data
cd course/data/
tar zxf fasta.tar.gz
tar zxf phylo.tar.gz

# Start jupyter in the root directory of this repo
cd ../
jupyter notebook
```

