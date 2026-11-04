# Image Smoothing and Sharpening Using OpenCV

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---

##  Developed By

## Name: Rishab P Doshi
### Register No: 212224240134

### Smoothing Filters

## Averaging filter 
```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("birds.jpeg")
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
### Weighted averaging
```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
### Gaussian filter
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
### Median filter
```
median=cv2.medianBlur(image2,13)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
###  Sharpening Filters
### Laplacian kernel
```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
### Laplacian operator
```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```


###  Output

### Smoothing Filters

- Averaging filter produces blurred image  
<img width="923" height="731" alt="image" src="https://github.com/user-attachments/assets/9d29e4db-4e9d-4792-8ad2-53063636bb82" />

- Weighted averaging provides smoother result with less distortion
<img width="376" height="508" alt="image" src="https://github.com/user-attachments/assets/fd2e5117-2334-4d37-bb09-d6ae93fb4db7" />

- Gaussian filter preserves edges better while reducing noise  
<img width="291" height="500" alt="image" src="https://github.com/user-attachments/assets/e0aa7ea9-1d60-4c1b-928c-674b1bd3a9f2" />

- Median filter removes salt-and-pepper noise effectively  
<img width="367" height="502" alt="image" src="https://github.com/user-attachments/assets/0e6e8436-69aa-4893-b8f1-e759ad489585" />

###  Sharpening Filters

- Laplacian kernel enhances edges and fine details  
<img width="300" height="502" alt="image" src="https://github.com/user-attachments/assets/f43a7ef9-f84e-41d0-9aa7-f267f233783c" />

- Laplacian operator detects edges clearly in grayscale  
<img width="310" height="503" alt="image" src="https://github.com/user-attachments/assets/faef26a8-6ef3-4b08-a72b-a58eb33aff95" />

---

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
