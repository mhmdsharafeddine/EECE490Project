# Solar Flares Classification Project
## Overview
This project aims to predict solar flare intensity using machine learning models trained on features extracted from magnetogram images of solar active regions.
Solar flares are categorized into four main classes based on their intensity: C, M, X, and 0 (no flare).
Our objective is to identify patterns in solar magnetic data that help forecast flare strength accurately.

##Dataset
The dataset used is found on this [link](https://datadryad.org/dataset/doi:10.5061/dryad.dv41ns23n). 

For our work, we will focus on the Validation_data_by_AR.csv file, which contains pre-processed features extracted from solar active regions (ARs). Each row represents a single active region, while columns describe numerical measurements derived from magnetogram images captured by the SDO/HMI instrument.

This file includes a total of 31 features grouped into several categories:

| Gradient features  | Neutral line features         | Wavelet features          | Flux features            | Flare class         | Image path                |
|--------------------|------------------------------|---------------------------|---------------------------|---------------------|---------------------------|
| Gradient mean      | NL length                    | Wavelet energy level 1    | Total unsigned flux       | Binary flare class  | Path to image in dataset  |
| Gradient std       | NL no. fragments             | Wavelet energy level 2    | Total signed flux         |                     |                           |
| Gradient median    | NL gradient-weighted length  | Wavelet energy level 3    | Total negative flux       |                     |                           |
| Gradient min       | NL curvature mean            | Wavelet energy level 4    | Total positive flux       |                     |                           |
| Gradient max       | NL curvature std             | Wavelet energy level 5    |                           |                     |                           |
| Gradient skewness  | NL curvature median          |                           |                           |                     |                           |
| Gradient kurtosis  | NL curvature min             |                           |                           |                     |                           |
|                    | NL curvature max             |                           |                           |                     |                           |
|                    | NL bending energy std        |                           |                           |                     |                           |
|                    | NL bending energy median     |                           |                           |                     |                           |
|                    | NL bending energy min        |                           |                           |                     |                           |
|                    | NL bending energy max        |                           |                           |                     |                           |

