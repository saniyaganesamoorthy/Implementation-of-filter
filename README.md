# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the required libraries.
### Step2
Convert the image from BGR to RGB.
### Step3
Apply the required filters for the image separately.
### Step4
Plot the original and filtered image by using matplotlib.pyplot.
### Step5
End the program.

## Program:
### Developed By   : SANIYA G
### Register Number: 212223240147

## Smoothing Filters
### Using Averaging Filter
```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("Tiger.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
![Screenshot 2024-10-03 113929](https://github.com/user-attachments/assets/8e71cd07-e604-41ae-b7ef-5bc49ad5debe)

### Using Weighted Averaging Filter
```Python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
![Screenshot 2024-10-03 114011](https://github.com/user-attachments/assets/384a505d-6432-45d6-a0bc-7f646af5994b)

### Using Gaussian Filter
```Python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
![Screenshot 2024-10-03 114024](https://github.com/user-attachments/assets/24f4afad-543b-498f-96d2-3cb1f3b3a50a)

### Using Median Filter
```Python
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
![Screenshot 2024-10-03 114044](https://github.com/user-attachments/assets/e243cc5a-8cce-4f33-80fb-91b3a07bee9a)

### Sharpening Filters
## Using Laplacian Linear Kernal
```Python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
![Screenshot 2024-10-03 114119](https://github.com/user-attachments/assets/6fa88c41-c84b-4e2a-9a8e-8be8dac94600)

### Using Laplacian Operator
```Python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
![Screenshot 2024-10-03 114146](https://github.com/user-attachments/assets/ffd16457-7a6b-4925-83ed-c3d01dd07e72)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
