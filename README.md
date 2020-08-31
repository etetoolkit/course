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
| [Building gene families]()  | clustering homologous sequences   |   None |
| [Building gene phylogenies](/tree/nb/01-building_gene_families)  |    |  Tree basics, ete-build, ete-view |
|   |   |      |
|   |   |      |



# Environment setup

## Clone this repository (git required)
```
# makes a separate dir for this course and enter it
mkdir etecourse/
cd etecourse/

# clone this repository
git clone https://github.com/etetoolkit/course
```

## Install and initialize miniconda

(You can skip this if you know conda)

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
```
conda env create -f course/REQUIREMENTS_conda.yml
conda activate etecourse
```

## uncompress necessary data and start jupyter
```
cd course/ 
tar zxf data.tar.gz
jupyter notebook
```

