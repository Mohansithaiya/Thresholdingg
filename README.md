# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Import required libraries.
<br>

### Step2:
Read the image and convert it to grayscale then display it.
<br>

### Step3:
Use Global thresholding to segment the image
<br>

### Step4:
Use Adaptive thresholding to segment the image
<br>

### Step5:
Use Otsu's method to segment the image
<br>

## Program

```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt


# Read the Image and convert to grayscale

image = cv2.imread('EAGLE.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)


# Use Global thresholding to segment the image
ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)


# Use Adaptive thresholding to segment the image
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY, 11, 2)

# Use Otsu's method to segment the image 
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()

plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()

plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()

```
## Output

### Global Thresholding
![Screenshot 2025-04-29 184444](https://github.com/user-attachments/assets/cd1247b5-83dd-4142-b878-93378c1c2902)


### Adaptive Thresholding
![Screenshot 2025-04-29 184451](https://github.com/user-attachments/assets/ec47f2e1-ebed-40c6-a814-8c23da1b6ad1)


### Optimum Global Thesholding using Otsu's Method
![Screenshot 2025-04-29 184457](https://github.com/user-attachments/assets/d0a45142-7df7-4e66-bbda-26f38a55cefb)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
