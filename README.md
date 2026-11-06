# Experiment 6: Record-Edge Detection

### Name: Parani Bala M
### Reg.no: 212224230192

## Aim
To implement different edge detection techniques using Python and OpenCV to identify the edges and boundaries of objects in an image.

## Objectives
- To read and display an input image.
- To convert a color image into a grayscale image.
- To implement Sobel Edge Detection.
- To detect horizontal and vertical edges using Sobel operators.
- To implement Laplacian Edge Detection.
- To implement Canny Edge Detection.
- To compare the results obtained using different edge detection techniques.

## Software Requirements
- Python 3.x
- Jupyter Notebook
- OpenCV (`cv2`)
- NumPy
- Matplotlib
- Input image: `My_Image.png`

## Algorithm
1. Start the program.
2. Import OpenCV, NumPy, and Matplotlib libraries.
3. Read the input image using `cv2.imread()`.
4. Convert the input image into grayscale using `cv2.cvtColor()`.
5. Display the original image.
6. Apply the Sobel operator in the X direction using `cv2.Sobel()`.
7. Apply the Sobel operator in the Y direction using `cv2.Sobel()`.
8. Combine both Sobel outputs using `cv2.magnitude()`.
9. Display the Sobel edge detection result.
10. Apply Laplacian Edge Detection using `cv2.Laplacian()`.
11. Display the Laplacian edge detection result.
12. Apply Canny Edge Detection using `cv2.Canny()` with threshold values 50 and 150.
13. Display the Canny edge detection result.
14. Stop the program.

## Program

### 1. Import Libraries and Display Original Image

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('My_Image.png')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```

### Output:
<img width="1492" height="592" alt="image" src="https://github.com/user-attachments/assets/e01b2b58-ff34-46c6-8f2c-fca8a0930cf2" />

### 2. Sobel Edge Detection

```python
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction

sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions

plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```

### Output:
<img width="1510" height="605" alt="image" src="https://github.com/user-attachments/assets/ebc082fd-f0b3-41d8-871d-49c935e807e4" />

### 3. Laplacian Edge Detection

```python
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)

plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
```

### Output:
<img width="1497" height="600" alt="image" src="https://github.com/user-attachments/assets/3466db7c-a183-4975-a7ab-a3e5914399fd" />

### 4. Canny Edge Detection

```python
canny_edges = cv2.Canny(gray_image, 50, 150)

plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```

### Output:
<img width="1508" height="610" alt="image" src="https://github.com/user-attachments/assets/b7dbbef5-9759-4158-834e-2bab46c7c592" />


## Result
Different edge detection techniques were implemented successfully using OpenCV. Sobel Edge Detection, Laplacian Edge Detection, and Canny Edge Detection were applied to the input image. The detected edges were displayed using Matplotlib for comparison.
