# Remote Sensing of Car and Truck Parking Lots at German Highway Rest Areas using Semantic Segmentation

This repository contains the code of my Master Thesis ["Remote Sensing of Car and Truck Parking Lots at German Highway Rest Areas using Semantic Segmentation"](korbach_benedikt_master_thesis.pdf) in partial fulfillment of the requirements for the M.Sc. in Data Science for Public Policy, supervised by Prof. Lynn Kaack, PhD (Hertie School). It does, however, not include any image data or model files due to their large file sizes. The pipeline to download the images of rest areas used in this research can be found in [Download Images](https://github.com/benedikt-korbach/remote-sensing-of-parking-areas/blob/main/scripts/01_data_acquisition/01c_download_images.ipynb). If you want to get access to the dataset of rest area images or have question about this project, feel free to contact me.

## Script Description

**Data Acquisition**:
- [OSM Data Import & Cleaning](https://github.com/benedikt-korbach/remote-sensing-of-parking-areas/blob/main/scripts/01_data_acquisition/01a_import_clean_OSM_export.ipynb): Filter rest areas with associated car and truck parking, create identifiers and merge into one dataframe.
- [Rest Area Selection](https://github.com/benedikt-korbach/remote-sensing-of-parking-areas/blob/main/scripts/01_data_acquisition/01b_select_service_stations.ipynb): Visually inspect rest areas with associated parking, adjust parking labels to the correct type (car, truck, pull-off) and select correctly annotated rest areas to be included in the dataset.
- [Image Download](https://github.com/benedikt-korbach/remote-sensing-of-parking-areas/blob/main/scripts/01_data_acquisition/01c_download_images.ipynb): Create image bounding boxes and download rest areas images (2560x2560 pixels) via Digital Orthophoto (DOP) Web Map Services (WMS).

**Mask Creation & Data Split**
- [Mask Creation & Tiling](https://github.com/benedikt-korbach/remote-sensing-of-parking-areas/blob/main/scripts/02_mask_creation_and_split/02a_create_tiling_masks.ipynb): Generate grey-scale masks denoting parking areas (car, truck, pull-off), split the dataset into training cases and a dataset for training/validation and create tiles from the training/validation dataset.
- [Data Split](https://github.com/benedikt-korbach/remote-sensing-of-parking-areas/blob/main/scripts/02_mask_creation_and_split/02b_create_train_val.ipynb): Reduce background-only tiles and split remaining tiles into training and validation set.

**Image Segmentation**
- [Parking Segmentation](https://github.com/benedikt-korbach/remote-sensing-of-parking-areas/blob/main/scripts/03_image_segmentation/03_segment_parking.ipynb): Run semantic segmentation models (U-Net, LinkNet, FPN), perform hyper-parameter tuning and evaluate model performance.

