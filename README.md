# Experiment 03 -- Histogram of Images

### Name : SURYA D
### Reg No: 212224220115

## Aim

To perform histogram equalization on grayscale and color images using
OpenCV and visualize the original and equalized images along with their
histograms.

## Procedure

1.  Import the required Python libraries: OpenCV (`cv2`), NumPy, and
    Matplotlib.
2.  Read the input image `MyI.jpeg` in grayscale mode using
    `cv2.imread()`.
3.  Display the original grayscale image and plot its histogram.
4.  Apply histogram equalization to the grayscale image using
    `cv2.equalizeHist()`.
5.  Display the equalized grayscale image and its histogram.
6.  Read the input image again in color mode.
7.  Convert the color image from BGR to HSV color space using
    `cv2.cvtColor()`.
8.  Apply histogram equalization to the Value (V) channel of the HSV
    image.
9.  Convert the equalized HSV image back to BGR color space.
10. Display the equalized color image, compare it with the original
    image, and plot their histograms.

## Program

``` python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Histogram Equalization for Grayscale Images
img = cv2.imread('MyI.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')
plt.show()

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

# Histogram Equalization for Color Images
img = cv2.imread('MyI.jpeg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.show()

plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()

plt.figure(figsize=(20, 10))
plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.show()

plt.figure(figsize=[15, 4])
plt.subplot(121)
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image')

plt.subplot(122)
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()
```

## Output

 **Original Grayscale Image:** 
 
<img width="249" height="434" alt="download" src="https://github.com/user-attachments/assets/25811846-914d-4b82-8195-7bfa670fcfd7" />


**Original Grayscale Histogram:** 

<img width="570" height="434" alt="download" src="https://github.com/user-attachments/assets/8873120d-112a-48fb-acd9-629271162831" />

**Equalized Grayscale Histogram:**

<img width="570" height="434" alt="download" src="https://github.com/user-attachments/assets/7b046629-c45e-4474-b069-a7ea6bd6ce76" />

  
**Equalized Grayscale Image:** 

<img width="249" height="434" alt="download" src="https://github.com/user-attachments/assets/93d8184f-a9d8-45cc-9e17-4d2339d69860" />


**Equalized Color Image:**

<img width="249" height="434" alt="download" src="https://github.com/user-attachments/assets/f06a4c47-c534-41b4-92c9-0b8daa9033a6" />


**Color Image Comparison:**

<img width="1084" height="414" alt="download" src="https://github.com/user-attachments/assets/e1f2276c-7ce6-495d-9115-3d4e5adbf03a" />


**Histogram Comparison:** T

<img width="1237" height="372" alt="download" src="https://github.com/user-attachments/assets/0ea80d07-845a-4a75-b66b-d978d061e61c" />


## Result

Thus, histogram equalization was successfully performed on grayscale and
color images using OpenCV. The original and equalized images and their
histograms were displayed and compared.
