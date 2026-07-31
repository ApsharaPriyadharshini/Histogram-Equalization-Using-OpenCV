# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program

### Developed By:
**Name:** Apshara Priyadharshini M
### Register No: 212225040026
____________________________  
```
1. Import the required libraries and read the grayscale image.
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
```
2. Plot the histogram of the grayscale image.
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Image Histogram')
plt.show()
```
```
3. Apply histogram equalization.
img_eq = cv2.equalizeHist(img)
```
```
4. Display the histogram of the equalized image.
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Equalized Histogram')
plt.show()
```
```
5. Display the equalized grayscale image.
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()
```
```

6. Read the image in color mode and convert to HSV.
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```
```
7. Apply histogram equalization to the V channel.
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
```
```
8. Convert the enhanced HSV image back to BGR.
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```
```
9. Display the original and equalized color images.
plt.subplot(121)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(122)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.show()
```
```
10. Display the original and equalized images along with their histograms.
plt.figure(figsize=[12,10])

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Histogram Equalized')

plt.show()
```
---

##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed
- <img width="1042" height="632" alt="image" src="https://github.com/user-attachments/assets/2a111d11-a6f2-42e9-a8fc-9baa3ccd9363" />
 
- Histogram of original grayscale image is plotted
- <img width="1002" height="636" alt="image" src="https://github.com/user-attachments/assets/cda6e68d-2117-4617-ba4b-e547e3ac2d29" />

- Enhanced image after histogram equalization is displayed
- <img width="1037" height="690" alt="image" src="https://github.com/user-attachments/assets/17a06c8d-53b9-4953-aefa-447d92f15d2d" />

- Histogram of enhanced grayscale image shows improved contrast
- <img width="1001" height="612" alt="image" src="https://github.com/user-attachments/assets/ad9b4c85-2d63-49d0-a284-fe87b21fe646" />


### Color Image Histogram Equalization

<img width="950" height="345" alt="image" src="https://github.com/user-attachments/assets/c7c87dfa-028a-4c0d-92ba-6bfa0be96db5" />
<img width="1038" height="351" alt="image" src="https://github.com/user-attachments/assets/a52a6f92-45b6-4f17-9b04-9aedb3e601bb" />
<img width="1043" height="432" alt="image" src="https://github.com/user-attachments/assets/57b76690-5ed4-4d71-b66c-720fc0a6cc46" />

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
