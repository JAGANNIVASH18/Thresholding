# THRESHOLDING

## Aim
To perform image segmentation using Global Thresholding, Adaptive Thresholding, and Otsu’s Thresholding techniques with Python and OpenCV.

---

## Software Required
- Anaconda – Python 3.7
- OpenCV

---

## Algorithm

### Step 1
Import the required libraries such as OpenCV, NumPy, and Matplotlib.

### Step 2
Read the input image and convert it into grayscale format.

### Step 3
Apply Global Thresholding techniques to segment the image.

### Step 4
Apply Adaptive Thresholding methods for image segmentation.

### Step 5
Apply Otsu’s Thresholding method and display all the segmented outputs.

---

## Program

### Import Required Packages

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Read the Image and Convert to Grayscale

```python
image = cv2.imread("DUCK.jpg")
image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

image_gray = cv2.imread("DUCK.jpg",0)
```

### Apply Global Thresholding

```python
ret,thresh_dipt1 = cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)

ret,thresh_dipt2 = cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)

ret,thresh_dipt3 = cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)

ret,thresh_dipt4 = cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)

ret,thresh_dipt5 = cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

### Apply Otsu’s Thresholding

```python
ret,thresh_dipt6 = cv2.threshold(
    image_gray,
    0,
    255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)
```

### Apply Adaptive Thresholding

```python
thresh_dipt7 = cv2.adaptiveThreshold(
    image_gray,
    255,
    cv2.ADAPTIVE_THRESH_MEAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)

thresh_dipt8 = cv2.adaptiveThreshold(
    image_gray,
    255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)
```

### Display the Results

```python
titles = [
    "Gray Image",
    "Threshold Image (Binary)",
    "Threshold Image (Binary Inverse)",
    "Threshold Image (To Zero)",
    "Threshold Image (To Zero-Inverse)",
    "Threshold Image (Truncate)",
    "Otsu",
    "Adaptive Threshold (Mean)",
    "Adaptive Threshold (Gaussian)"
]

images = [
    image_gray,
    thresh_dipt1,
    thresh_dipt2,
    thresh_dipt3,
    thresh_dipt4,
    thresh_dipt5,
    thresh_dipt6,
    thresh_dipt7,
    thresh_dipt8
]

for i in range(0,9):

    plt.figure(figsize=(10,10))

    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")

    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(images[i], cmap='gray')
    plt.axis("off")

    plt.show()
```

---

## Output

### Original Image

<img width="360" height="226" alt="image" src="https://github.com/user-attachments/assets/6e709e20-05fe-47dd-bab5-ecd1aed1511b" />


### Global Thresholding

<img width="858" height="447" alt="image" src="https://github.com/user-attachments/assets/4250e373-2eba-4976-b402-aa1f0ddc7342" />
<img width="938" height="448" alt="image" src="https://github.com/user-attachments/assets/e07452b9-47a9-48d2-8030-b0468cedb650" />
<img width="844" height="236" alt="image" src="https://github.com/user-attachments/assets/7a26dd45-08c6-413a-823f-54b395bd4dae" />


### Adaptive Thresholding

<img width="889" height="453" alt="image" src="https://github.com/user-attachments/assets/4eac158a-c481-472b-aa65-86258f366db2" />


### Otsu’s Thresholding

<img width="892" height="228" alt="image" src="https://github.com/user-attachments/assets/ef139b51-4e20-4dd2-b0c9-5a51e6ef9ca7" />


---

## Result
Thus, the image segmentation process using Global Thresholding, Adaptive Thresholding, and Otsu’s Thresholding was successfully implemented using Python and OpenCV.

---

## About
This project demonstrates different thresholding techniques used in image processing for segmenting grayscale images using OpenCV.

---

## Topics
- Python
- OpenCV
- Image Processing
- Thresholding
- Computer Vision
