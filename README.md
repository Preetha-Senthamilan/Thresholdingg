# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program
```
NAME : PREETHA.S
REG : 212222230110

```
```
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2
# Read the Image and convert to grayscale

image = cv2.imread('flight.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('flight.jpg',0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

```

## Output

### Original Image

![image](https://github.com/Preetha-Senthamilan/Thresholdingg/assets/119390282/7cb743b0-5c14-4b3b-b41c-4502b8f045ed)


### Global Thresholding

![image](https://github.com/Preetha-Senthamilan/Thresholdingg/assets/119390282/2ed7399e-e701-4028-8973-260b330a70d3)

![image](https://github.com/Preetha-Senthamilan/Thresholdingg/assets/119390282/a173f2b8-8cd5-4e07-a997-781972902d92)


![image](https://github.com/Preetha-Senthamilan/Thresholdingg/assets/119390282/5a5a299e-1731-49f2-bb06-f824d217c693)


![image](https://github.com/Preetha-Senthamilan/Thresholdingg/assets/119390282/908f8e33-3bc2-47b6-802f-8d53a03c6568)



![image](https://github.com/Preetha-Senthamilan/Thresholdingg/assets/119390282/91688252-0e3a-41ee-9d15-f337443406d6)




### Adaptive Thresholding

![image](https://github.com/Preetha-Senthamilan/Thresholdingg/assets/119390282/f3aa7adf-5bb1-4b50-9dcc-915692062e00)


![image](https://github.com/Preetha-Senthamilan/Thresholdingg/assets/119390282/79f6cda6-b8d4-424b-83d4-dbb1176966e9)


### Optimum Global Thesholding using Otsu's Method


![image](https://github.com/Preetha-Senthamilan/Thresholdingg/assets/119390282/842e10e5-6c59-4db4-bb6a-c7101ee5b914)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
