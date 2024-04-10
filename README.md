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
![Screenshot 2024-04-10 110334](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/ddd32c6c-aeeb-4fb2-84b3-20d3f8f264ee)

### Global Thresholding
![Screenshot 2024-04-10 110418](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/89b15271-c04c-4ad5-ac52-0629b9218cc8)
![Screenshot 2024-04-10 110354](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/bae19a8b-b0e9-4e88-ae7d-b326fae4957e)
![Screenshot 2024-04-10 110343](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/83625a51-b40d-4a7c-9201-fd6683d84d72)
![Screenshot 2024-04-10 110427](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/80b8dd99-ce5b-4102-abd4-7)
![Screenshot 2024-04-10 110436](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/fcb64e6e-ea69-40f7-8dbd-8f6f442cf611)
ab9ee55d4de)


### Adaptive Thresholding

![Screenshot 2024-04-04 115142](https://github.com/vasundrasriravi/THRESHOLDING-/assets/119393983/f0f2cef9-52fa-49a5-b031-688016938a04)
![Screenshot 2024-04-10 110513](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/83b7ac8c-80a0-46c1-8519-ffb38dfeadf1)

### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-04-10 110447](https://github.com/KameshLeVI/THRESHOLDING-/assets/120780633/47aa2352-ac60-4466-ab91-e9aaa165e3cc)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
