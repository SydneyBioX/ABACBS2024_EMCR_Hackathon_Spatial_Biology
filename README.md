# ABACBS EMCR Hackathon: Spatial Biology

4 November 2024

## 1. Overarching task

### What is given: 
* Reference scRNA-seq dataset with cell-type annotation 

* MoleculeExperiment object containing: 
	* molecules 
	* boundaries of cells according to scheme 1 
	* boundaries of cells according to scheme 2 

* Cell type annotation for spatial data according to scheme 1

### Questions - Method: 
* How can we best extract an annotation for spatial data according to scheme 2? 
* How can we obtain a tissue-level characterisation independent of segmentation schemes? 
* How do our approaches change if we do not have a reference dataset?

### Questions - Evaluation: 
* What metrics can be used to assess consistency, accuracy, stability? 
* Can we identify cells that are most and least consistent, according to each scheme?
Open for participants to use data & scenario as inspiration!

## 2. Installation required software

Please install the following R packages:

```
library(MoleculeExperiment) # for data structure
library(SingleCellExperiment) # for data structure
library(SpatialExperiment) # for data structure
library(scater) # for visualisation
library(patchwork) # for plotting
```

For reproducing the processed data please install the following R packages and 
scripts:

```
library(MoleculeExperiment) # for data structure
source(url("https://raw.githubusercontent.com/SydneyBioX/SpatialUtils/refs/heads/main/R/tileBoundaries.R"))
library(SingleCellExperiment) # for data structure
library(zellkonverter) # for reading scRNAseq h5ad data
library(scran) # for normalisation
library(scater) # for visualisation
library(randomForest) # for predictive model
library(SpatialExperiment) # for data structure
library(patchwork) # for plotting
```

## 3. Data and assumed folder structure

We assume that this repository is located inside the `scripts` folder of the 
hackathon project directory. We assume there are the following additional folders
with relative paths:

* `../processedData/`
  * `xenium_pancreas_me.Rds` - MoleculeExperiment of Xenium pancreas
  * `xenium_pancreas_features.Rds` - character vector of features
  * `sc_pancreas_sce.Rds` - SingleCellExperiment of Tabula Sapiens scRNA-seq reference
  * `xenium_pancreas_spe_cells.Rds` - SpatialExperiment of cell-summarised Xenium data
  * `xenium_pancreas_spe_tiles.Rds` - SpatialExperiment of tile-summarised Xenium data

* `../analysisOutput/`
  * `pancreas_colours.Rds` - character vector of cell type colours
  * `sc_cell_type_RF_fit.Rds` - Fitted Random Forest model object used for predicting cell types

* (for reproducing data processing) `../rawData/`
  * `9af4585d-a1aa-4109-913f-6fe73772af70.h5ad` - H5AD file of reference single cell data
  * `Xenium_V1_human_Pancreas_FFPE_outs/` - folder containing raw Xenium data bundle

## Contact

Please contact the Hackathon leads Dr Shila Ghazanfar and EMCR guide Dr Yue Cao
first via the ABACBS Slack channel. Further questions can be sent to 
<shila.ghazanfar@sydney.edu.au>.
