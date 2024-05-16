# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
#### Step1:Load the necessary packages.
#### Step2:Read the Image and convert to grayscale.
#### Step3:Use Global thresholding to segment the image.
#### Step4:Use Adaptive thresholding to segment the image.
#### Step5:Use Otsu's method to segment the image and display the results.

## Program
### Developed By : VIGNESH KUMARAN N S
### Register Number : 212222230171
```python
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2
```
```python
# Read the Image and convert to grayscale

image = cv2.imread('kobe.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('kobe.jpg',0)
```
```python
# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
```python
# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
```python
# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
```python
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

![ex8](https://github.com/VigneshkumaranNS/Thresholdingg/assets/119484483/26de3a9f-87a5-4c39-8c58-a829fe5de0a9)

### Global Thresholding

![Ex8-1](https://github.com/VigneshkumaranNS/Thresholdingg/assets/119484483/3744c668-212f-48de-8379-fc3b467c15d0)
![EX8-2](https://github.com/VigneshkumaranNS/Thresholdingg/assets/119484483/fe92e17c-ec10-4aec-87b4-90d38600c065)
![EX8-3](https://github.com/VigneshkumaranNS/Thresholdingg/assets/119484483/4b4db062-90ed-4511-a97c-6be39a656139)
![EX8-4](https://github.com/VigneshkumaranNS/Thresholdingg/assets/119484483/a3f4ba97-adf5-4427-9422-b83cf5dc1f69)
![EX8-5](https://github.com/VigneshkumaranNS/Thresholdingg/assets/119484483/7189ea7f-aec0-49e6-b725-4863be611048)

### Adaptive Thresholding

![image](https://github.com/VigneshkumaranNS/Thresholdingg/assets/119484483/966e25b1-38d3-4ea8-a2a1-1eeb372722af)
![image](https://github.com/VigneshkumaranNS/Thresholdingg/assets/119484483/8de8cb31-44a4-4755-96e8-1b3b0dc3f8a7)

### Optimum Global Thesholding using Otsu's Method

![image](https://github.com/VigneshkumaranNS/Thresholdingg/assets/119484483/4e3fde6d-eb0f-4a47-9044-7fd4b4e0b057)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
