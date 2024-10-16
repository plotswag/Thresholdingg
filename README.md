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
Developed by:Giftson Rajarathinam N
Register number:212222233002

```
```python
# Load the necessary packages

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale

image = cv2.imread('HappyFish.jpg')

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()



# Use Global thresholding to segment the image

ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()



# Use Adaptive thresholding to segment the image

th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY, 11, 2)

# Display the adaptive thresholding result
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()




# Use Otsu's method to segment the image 
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)



# Display the results
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()




```
## Output:

### Original Image:
![images](https://github.com/user-attachments/assets/895aef0d-223c-4cff-bb7a-6c86a48e6412)
### Greyscale Image:
![image](https://github.com/user-attachments/assets/88368a0e-577b-4f88-86ab-8fe3554000d2)

### Global Thresholding:
![image](https://github.com/user-attachments/assets/43ba3db9-eb2c-4aff-87ec-762a337bfd1b)


### Adaptive Thresholding:
![image](https://github.com/user-attachments/assets/50033e1b-0261-4399-9867-290403aa91f3)


### Optimum Global Thesholding using Otsu's Method:
![image](https://github.com/user-attachments/assets/ea9c3b64-d6db-4bcc-8e48-29781f6919ca)



## Result:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
