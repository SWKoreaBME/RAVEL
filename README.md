# RAVEL
[![Build Status](https://travis-ci.org/Jfortin1/RAVEL.svg?branch=master)](https://travis-ci.org/Jfortin1/RAVEL)

### Imaging suite for the statistical analysis of structural MRIs. 

RAVEL stands for Removal of Artificial Voxel Effect by Linear regression, the main preprocessing function of the package. 

#### Installation

```{r}
library(devtools)
install_github("jfortin1/RAVEL")
```


#### preprocessRAVEL

The function `preprocessRAVEL` applies the RAVEL correction described in XX


#### preprocessWS

The function `preprocessWS` applies the White Stripe intensity normalization described in XX

#### Tissue Segmentation

There are different tissue segmentation algorithms available in R. My favorite is the FSL FAST segmentation via the [`fslr`](https://cran.r-project.org/web/packages/fslr/index.html) package. Note that the `fslr` package requires FSL to be installed on your machine; see the [FSL website](http://fsl.fmrib.ox.ac.uk/fsl/fslwiki/). Here is an example how to perform segmentation on the JHU-MNI-ss template included in the `RAVELData` package. First, let's make sure we have `fslr` correctly installed:

```{r}
library(fslr)
library(RAVELData)
have.fsl() # Should be TRUE if fsl is correctly installed
```
Then we perform a 3-class tissue segmentation on the T1-w image with the FAST segmentation algorithm:

```{r}
img_path <- system.file(package="RAVELData", "data/JHU_MNI_SS_T1_Brain.nii.gz")
img <- readNIfTI(img_path)
seg <- fast(img, verbose=FALSE) 
 
```
The object `seg` is an image that contains the segmentation labels `0,1,2` and `3` referring to Background, CSF, GM and WM voxels respectively. 

- Add image of the template
- Add image of the segmentation

#### Registration to template

#### Coregistration (for more than one modality)

#### RAVEL for longitudinal data

#### RAVEL for multimodal data




