# Exp-8  THRESHOLDING
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


```python
#Name:  HAREESH R
#Reg No: 212223230068
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale

image = cv2.imread('cheetah.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('cheetah.jpeg',0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)jujupitr
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

## Original Image
![Screenshot 2025-05-03 112118](https://github.com/user-attachments/assets/2e991b3c-e001-4543-81f7-de178f255e39)


## Global Thresholding

![Screenshot 2025-05-03 112138](https://github.com/user-attachments/assets/00386fb5-eeea-48dc-b9a0-a2a0b388b0ac)

![Screenshot 2025-05-03 112150](https://github.com/user-attachments/assets/aba19cf9-1141-499a-8e6e-722318ce72e0)

![Screenshot 2025-05-03 112201](https://github.com/user-attachments/assets/342d4dcc-15f2-4348-9678-815815116ff8)

![Screenshot 2025-05-03 112221](https://github.com/user-attachments/assets/c6ebd3d0-172f-4633-b794-1694e673936d)

![Screenshot 2025-05-03 112235](https://github.com/user-attachments/assets/df684a88-5b8b-4d8a-95be-9c0fee623fc1)



## Adaptive Thresholding
![Screenshot 2025-05-03 111933](https://github.com/user-attachments/assets/104723d3-e6e7-4f4a-9aa2-9e2ac2b968cf)

![Screenshot 2025-05-03 111947](https://github.com/user-attachments/assets/f4f959c9-20ce-45c9-b8f2-8d11117bea44)

## Optimum Global Thesholding using Otsu's Method

![Screenshot 2025-05-03 111834](https://github.com/user-attachments/assets/58d336e2-e5ed-46fa-bbaf-becd8eb2168d)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
