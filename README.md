# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.

## Program:
```
#name- RICHARDSON A
#RegNO -212222233005
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('HappyFish.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Apply Sobel edge detector
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions

# Apply Laplacian edge detector
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)

# Apply Canny edge detector
canny_edges = cv2.Canny(gray_image, 50, 150)

# Display results using Matplotlib
plt.figure(figsize=(12, 12))

# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

# Sobel Edge Detection
plt.subplot(2, 2, 2)
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

# Laplacian Edge Detection
plt.subplot(2, 2, 3)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

# Canny Edge Detection
plt.subplot(2, 2, 4)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')

# Show all results
plt.tight_layout()
plt.show()

```
## Orignal image:
<img width="509" alt="Screenshot 2024-10-16 at 4 50 48 PM" src="https://github.com/user-attachments/assets/60a3e927-30d2-464a-babc-b16f634b381f">


## Output:
### SOBEL EDGE DETECTOR
<img width="511" alt="Screenshot 2024-10-16 at 4 51 28 PM" src="https://github.com/user-attachments/assets/f02437a3-9679-4246-9cdd-b2ee5de3be4f">


### LAPLACIAN EDGE DETECTOR
<img width="516" alt="Screenshot 2024-10-16 at 4 51 49 PM" src="https://github.com/user-attachments/assets/bb6b3df7-6e0c-4199-aed2-695b0f7c2000">



### CANNY EDGE DETECTOR

<img width="509" alt="Screenshot 2024-10-16 at 4 52 00 PM" src="https://github.com/user-attachments/assets/ebffd300-dea6-4274-9353-e17c6b825ce7">

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
