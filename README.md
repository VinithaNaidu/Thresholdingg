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

# Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

# Read the Image and convert to grayscale
```python
image = cv2.imread("nature.png",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("nature.png",0)
```

# Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```



# Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```



# Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```



# Display the results

```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()


```
## Output

### Original Image
<img width="334" alt="image" src="https://github.com/TejaswiniGugananthan/Thresholdingg/assets/121222763/4c51ada8-8fc2-428c-92b7-f4cfaae0e6ee">


### Global Thresholding
<img width="335" alt="image" src="https://github.com/TejaswiniGugananthan/Thresholdingg/assets/121222763/fb7955b8-f171-4af1-999a-a97253d4d839">

<img width="339" alt="image" src="https://github.com/TejaswiniGugananthan/Thresholdingg/assets/121222763/3c7081b9-c30e-4a8d-8388-b5c7ef1819e5">

<img width="335" alt="image" src="https://github.com/TejaswiniGugananthan/Thresholdingg/assets/121222763/623a6eaf-6d21-44d4-8b99-d81cbacae581">

### Adaptive Thresholding

<img width="338" alt="image" src="https://github.com/TejaswiniGugananthan/Thresholdingg/assets/121222763/ef26f0b4-23a9-4751-82f3-7367e04fd826">


### Optimum Global Thesholding using Otsu's Method

<img width="331" alt="image" src="https://github.com/TejaswiniGugananthan/Thresholdingg/assets/121222763/6b1b4c22-ea5f-42b7-a3f5-c0b55a688677">


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
