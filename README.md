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
Developed by: Kamesh D
Register no: 212222240043
```
# Load the necessary packages
```py
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
# Read the Image and convert to grayscale
```py
image = cv2.imread("joker.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("joker.jpg",0)
```
# Use Global thresholding to segment the image
```py
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
# Use Adaptive thresholding to segment the image
```py
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
# Use Otsu's method to segment the image 
```py
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
# Display the results
```py
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
![Screenshot 2024-04-10 110334](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/26bee555-3daf-4d29-923e-ee5a91cecf05)

### Global Thresholding
![Screenshot 2024-04-10 110343](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/0a9ed891-14a2-446c-84e7-bf9661f30a23)
![Screenshot 2024-04-10 110354](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/2a8ad0b1-08d2-4eb6-8480-5985d85bc571)
![Screenshot 2024-04-10 110418](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/cc97d073-02f3-4172-9bb3-83ae6bcd0c9b)
![Screenshot 2024-04-10 110427](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/9e7f4f38-e2e3-4274-9fac-c74cb805b0c7)
![Screenshot 2024-04-10 110436](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/5b39cfcc-6e85-42cc-b53e-830219a62dd5)

### Adaptive Thresholding
![Screenshot 2024-04-10 110502](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/6ad7edd4-6d0b-476f-b62f-d1dec93a5341)
![Screenshot 2024-04-10 110513](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/ae1abd94-bec8-4177-8999-ffcec85f732d)

### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-04-10 110447](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/6df5c626-28b1-460b-b86a-e55b74b1ac28)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
