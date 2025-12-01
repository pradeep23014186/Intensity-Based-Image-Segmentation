<h1 align=center>Thresholding using OpenCV</h1>

## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
Anaconda - Python 3.7
OpenCV
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
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread("owl.jpg")

image_gray = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

#CONVERT THE COLOR FROM BGR TO RGB
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
#plt.imshow(image)
plt.title("Original Image")
plt.axis("off")

ret,thresh_dipt1=cv2.threshold(image_gray,100,255,cv2.THRESH_BINARY)
plt.imshow(thresh_dipt1)
plt.axis("off")

adaptive_threshold=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 1)
plt.imshow(adaptive_threshold,cmap="gray")
plt.axis("off")

ret, otsu_threshold = cv2.threshold(image_gray, 25, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
plt.imshow(otsu_threshold)
plt.axis("off")
```

# Output
### 1. Original Image
<img width="496" height="468" alt="image" src="https://github.com/user-attachments/assets/03e4bd12-a7b3-4569-9094-10f35216183d" />

### 2. Global Theresholding
<img width="605" height="443" alt="image" src="https://github.com/user-attachments/assets/359b5f06-6771-42c9-8d85-98ff625cc83c" />

### 3. Adaptive Thresholding
<img width="493" height="442" alt="image" src="https://github.com/user-attachments/assets/6c801ed4-dc18-4e59-948f-5ecaeb9f4d0c" />

### 4. Optimum Global Thesholding using Otsu's Method
<img width="501" height="435" alt="image" src="https://github.com/user-attachments/assets/14d22115-f07f-4a5d-986d-644641356b3f" />

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
