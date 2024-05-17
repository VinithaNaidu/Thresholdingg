# EX08-THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

- **Step1:** Load the necessary packages.

- **Step2:** Read the Image and convert to grayscale.

- **Step3:** Use Global thresholding to segment the image.

- **Step4:** Use Adaptive thresholding to segment the image.

- **Step5:** Use Otsu's method to segment the image and display the results.

## PROGRAM
```
Developed By : D.Vinitha
Register Number : 212222230175
```

### Load the necessary packages

```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

### Read the Image and convert to grayscale

```python
image = cv2.imread('rain.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('rain.jpg',0)
```

### Use Global thresholding to segment the image

```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

### Use Adaptive thresholding to segment the image

```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

### Use Otsu's method to segment the image 

```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

### Display the results

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

## OUTPUT

### Original Image
<img src="https://github.com/Janarthanan2/DIP_EX08_Thresholding/assets/119393515/f35cdd69-7db6-43ae-8aa8-3c977a98c920" width=65%>

### Global Thresholding

<img src="https://github.com/Janarthanan2/DIP_EX08_Thresholding/assets/119393515/186a14ec-4a22-45c6-8cf5-655bda466caf" width=65%>
<img src="https://github.com/Janarthanan2/DIP_EX08_Thresholding/assets/119393515/ab9e27fe-ba35-4fce-9891-a047015a8fb4" width=65%>
<img src="https://github.com/Janarthanan2/DIP_EX08_Thresholding/assets/119393515/531e8f12-8dca-4120-8490-8b03df0d855e" width=65%>
<img src="https://github.com/Janarthanan2/DIP_EX08_Thresholding/assets/119393515/e1b826e0-f03f-4be1-8e25-0642997e7a68" width=65%>
<img src="https://github.com/Janarthanan2/DIP_EX08_Thresholding/assets/119393515/97d684a0-d794-415c-a19d-f66b36e21e01" width=65%>


### Adaptive Thresholding
<img src="https://github.com/Janarthanan2/DIP_EX08_Thresholding/assets/119393515/4a20ed99-c787-4014-a635-fec563535259" width=65%>
<img src="https://github.com/Janarthanan2/DIP_EX08_Thresholding/assets/119393515/5ee982c3-6251-458e-b172-2a20d62583a8" width=65%>


### Optimum Global Thesholding using Otsu's Method
<img src="https://github.com/Janarthanan2/DIP_EX08_Thresholding/assets/119393515/8bd75d77-7202-471c-a3e4-ce0fdfe0e31e" width=65%>


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
