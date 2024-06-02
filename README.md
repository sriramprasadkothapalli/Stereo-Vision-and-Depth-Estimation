# Stereo-Vision-and-Depth-Estimation

The main objective of this pipeline is to compute depth images from 3 datasets given, each dataset consists of 2 images and information about calibration matrix, baseline, focal lengths.


## Libraries 
Install these libraries to run the code

```
import os
from google.colab import drive
from google.colab.patches import cv2_imshow
import cv2 as cv
import numpy as np
from matplotlib import pyplot as plt
import glob
```

## Pipeline 

- Identify matching features between the two images in each dataset using any feature matching algorithms.

- Estimate the Fundamental matrix using RANSAC method based on the matched features.

- Compute the Essential matrix from the Fundamental matrix considering calibration parameters.

- Decompose the Essential matrix into rotation and translation matrices.

- Apply perspective transformation to rectify images and ensure horizontal epipolar lines.

- Print the homography matrices (H1 and H2) for rectification.

- Visualize epipolar lines and feature points on both rectified images.

- Calculate the disparity map representing the pixel-wise differences between the two images.

- Rescale the disparity map and save it as grayscale and color images using heat map conversion.

- Utilize the disparity information to compute depth values for each pixel.

- Generate a depth image representing the spatial dimensions of the scene.

- Save the depth image as grayscale and color using heat map conversion for visualization.
## Visual Outputs 
### 1. Feature matching
![image](https://github.com/sriramprasadkothapalli/Stereo-Vision-and-Depth-Estimation/assets/143056659/2b257d06-521c-485a-b921-d494a9da9882)
### 2.1 Drawing Epipolar Lines 
 ![image](https://github.com/sriramprasadkothapalli/Stereo-Vision-and-Depth-Estimation/assets/143056659/a403edde-4507-476b-b799-bd214fe67bcf)
### 2.2 Epipolar lines after rectification on the images 
![image](https://github.com/sriramprasadkothapalli/Stereo-Vision-and-Depth-Estimation/assets/143056659/33ef9425-d198-4ac9-a69d-a9a1c0a2e967)
### 3.1 Disparity map 
![image](https://github.com/sriramprasadkothapalli/Stereo-Vision-and-Depth-Estimation/assets/143056659/b7ca0f25-9f49-4932-a249-b39e8431523e)
### 3.2 Depth map
![image](https://github.com/sriramprasadkothapalli/Stereo-Vision-and-Depth-Estimation/assets/143056659/cc2189cc-f7bc-4fde-b04a-188772bd1189)
### 3.3 Depth map greyscale 
![image](https://github.com/sriramprasadkothapalli/Stereo-Vision-and-Depth-Estimation/assets/143056659/16ee8cda-d29b-4b5b-939a-af3894b3f8b5)


