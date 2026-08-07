# Edge-detection-opencv
## Aim:
To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib

## Algorithm:
### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using cv2.imread().

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply Sobel operator using OpenCV to detect edges.

### Step 5:
Apply Prewitt operator using custom kernels.

### Step 6:
Apply Roberts operator using custom kernels.

### Step 7:
Apply Laplacian operator using OpenCV.

### Step 8:
Apply Canny edge detector using OpenCV.

### Step 9:
Display all edge-detected images for comparison.

## Developed By:
Name: DEVADHAARINI.R
Register No: 212225040061.
## Program:
**Original Image**
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('cat.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```
**Sobel Edge Detector**
```
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```
**Laplacian Edge Detector**
```
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
```
**Canny Edge Detector**
```
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```

## Output:
** Original Image**
<img width="666" height="409" alt="Screenshot 2026-08-07 225956" src="https://github.com/user-attachments/assets/7e63c91d-1357-41d1-8120-5f776139a4da" />

**Sobel Edge Detector**
- Detects edges in horizontal and vertical directions
- Produces gradient-based edge map
<img width="689" height="423" alt="Screenshot 2026-08-07 230026" src="https://github.com/user-attachments/assets/356c233e-e1df-485d-8230-a1acaf7b5069" />

  
**Laplacian Edge Detector**
- Detects edges using second-order derivatives
- Highlights rapid intensity changes
<img width="643" height="413" alt="Screenshot 2026-08-07 230242" src="https://github.com/user-attachments/assets/226470bb-bf1c-4785-813c-11e7f32ce198" />

**Canny Edge Detector**
- Multi-stage edge detection
- Produces clean and thin edges
<img width="674" height="411" alt="Screenshot 2026-08-07 230327" src="https://github.com/user-attachments/assets/7fc0a86e-1f47-4659-8ec5-75aed7eeda28" />
 
## Result:
Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
