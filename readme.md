# WIPI-Dataset
The WIPI dataset is generated from the [Sen1Floods11](https://github.com/cloudtostreet/Sen1Floods11) dataset through water index extraction and cloud removal operations. The table below provides relevant information about the dataset.

| Dataset  |  Image size  | Train set | Val set | Test set |
| :------: | :----------: | :-------: | :-----: | :------: |
| Sen1-SAR | (512,512,2)  |    221    |   85    |   140    |
| Sen2-MS  | (512,512,13) |    221    |   85    |   140    |
|   WIPI   | (512,512,9)  |    221    |   85    |   140    |

The Sen1Floods11 dataset comprises raw Sentinel-1 SAR images (Sen1-SAR) and raw Sentinel-2 multispectral images (Sen2-MS), where Sen1-SAR includes VV and VH bands, and Sen2-MS includes 13 bands (1-8, 8A, 9-12) covering the entire spectrum. The dataset covers 120,406 square kilometers of surface water, spanning 6 continents globally and documenting 11 flood events. The selection criteria for events include having flood coverage on Sentinel-1 and coincident Sentinel-2 imagery on the same day or within 2 days of the Sentinel-1 image. In addition to images, Sen1-SAR provides automated labels using the Otsu threshold method, with two categories: water (label 1) and non-water (label 0). Sen2-MS provides manual labels, including three categories: water (label 1), non-water (label 0), and cloud and invalid regions (label -1). A set of sample images and masks from the Sen1Floods11 dataset are shown in
Figure 1.

![Figure1.jpg](https://s2.loli.net/2023/11/21/Tk4XdNlgbD6KHFJ.jpg)

<center>Figure 1. A set of sample images and masks from the Sen1Floods11 dataset.</center>

## Water Index Extraction

In this work, instead of directly superimposing the SAR and multispectral image, we first analyze the characteristics of the water index and extract seven different water indexes from 13 bands of raw MSI to enhance water information while reducing the channel dimension. The seven extracted water indexes are: 1) Normalized Difference Vegetation Index (NDVI); 2) Normalized Difference Moisture Index (NDMI); 3) Normalized Difference Water Index (NDWI); 4) Modified Normalized Difference Water Index (MNDWI); 5) Automated Water Extraction Index Non-Shadow (AWEINS); 6) Automated Water Extraction Index Shadow (AWEIS); and 7) Linear Discriminant Analysis Water Index (LDAWI).

## Obtaining cloud-free label

We propose a Multi-Model Decision Fusion (MMDF) method to automatically obtain cloud-free labels based on the fine manual labels of multispectral images. The framework of MMDF is shown in Figure 2.

![image.png](https://s2.loli.net/2023/11/21/LwBqrUYFieNngyR.png)

<center>Figure 2. The framework of MMDF to automatically obtain cloud-free labels.</center>
The WIPI can be used for academic research only, please do not use them for commercial purposes. If you have any problem with the use of WIPI dataset, please contact: [rfwang@xidian.edu.cn](mailto:rfwang@xidian.edu.cn) and [weibinli@xidian.edu.cn](mailto:weibinli@xidian.edu.cn).
