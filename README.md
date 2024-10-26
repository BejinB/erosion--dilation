# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Apply the dilation operation on the image using cv2.dilate() with the same structuring element. Dilation will increase the size of the white regions (text) in the image, effectively reversing the effect of erosion

### Step2:
Initialize a blank image (100 pixels high and 400 pixels wide) using NumPy. The image should be a single-channel (grayscale) array filled with zeros (black).

### Step3:
Use OpenCV's cv2.putText() function to overlay the text "HYCINTH" on the blank image. Define the font style, position, font scale, color, and thickness for rendering the text.

### Step4:
Specify the size of the structuring element (e.g., 5x5 pixels) and create a rectangular structuring element using cv2.getStructuringElement(). This element will be used for the morphological operations.

### Step5:
Apply the erosion operation on the image using cv2.erode() with the defined structuring element. Erosion will reduce the size of the white regions (text) in the image.


## Program:
### Import the necessary packages
``` Python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create a blank image (100 pixels high and 400 pixels wide)
img = np.zeros((100, 400), dtype='uint8')
```
### Create the Text using cv2.putText
```python
# Put some text on the image for demonstration
cv2.putText(img, 'VINUSH CV', (60, 70), cv2.FONT_HERSHEY_SIMPLEX, 2, (255), 5)
```


### Create the structuring element
```python
# Create a rectangular structuring element
kernel_size = (5, 5)  # Width and height of the kernel
structuring_element = cv2.getStructuringElement(cv2.MORPH_RECT, kernel_size)

# Perform Erosion
eroded_image = cv2.erode(img, structuring_element, iterations=1)

# Perform Dilation
dilated_image = cv2.dilate(img, structuring_element, iterations=1)

# Display the original, eroded, and dilated images
plt.figure(figsize=(15, 5))
```
## Original Image
```python
# Original Image

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.axis('off')

plt.show()
```
![image](https://github.com/user-attachments/assets/f4633c35-6ca9-41c5-8ea2-782a7f332ad4)



## Erode the image
```python
plt.figure(figsize=(15, 5))
# Eroded Image
plt.imshow(eroded_image, cmap='gray')
plt.title('Eroded Image')
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/a519d1d9-5c80-4e83-b614-7d3b0d2aedca)



## Dilate the image
```python
plt.figure(figsize=(15, 5))
# Dilated Image
plt.imshow(dilated_image, cmap='gray')
plt.title('Dilated Image')
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/4e4be930-3333-4eec-85ca-3bf7769846eb)



## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
