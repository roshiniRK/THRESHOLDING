# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.
<br>

### Step2:
Read the Image and convert to grayscale.
<br>

### Step3:
Use Global thresholding to segment the image.
<br>

### Step4:
Use Adaptive thresholding to segment the image.
<br>

### Step5:
Use Otsu's method to segment the image.
<br>

### Step6:
Display the results.
<br>

## Program
```
Developed by: ROSHINI R K
Register number :212222230123
```
# Load the necessary packages
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```




# Read the Image and convert to grayscale
```python
image=cv2.imread("butterfly.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("butterfly.jpg",0)
```



# Use Global thresholding to segment the image
```python
ret,thresh_dipt1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_dipt2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_dipt3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_dipt4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_dipt5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```



# Use Adaptive thresholding to segment the image
```python
ret,thresh_dipt6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```



# Use Otsu's method to segment the image 
```python
thresh_dipt7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_dipt8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```



# Display the results
```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_dipt1,thresh_dipt2,thresh_dipt3,thresh_dipt4,thresh_dipt5,thresh_dipt6,thresh_dipt7,thresh_dipt8]
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
<br>

![image](https://github.com/roshiniRK/THRESHOLDING/assets/118956165/1e3a613a-3f98-4b9b-920d-0fd113e01d42)


<br>


### Global Thresholding
<br>

![image](https://github.com/roshiniRK/THRESHOLDING/assets/118956165/9aa0d99a-16b1-4ee4-b817-807f01abc5ef)
![image](https://github.com/roshiniRK/THRESHOLDING/assets/118956165/3a93458f-972d-4336-b7f1-eb42d972fe89)
![image](https://github.com/roshiniRK/THRESHOLDING/assets/118956165/453fad6b-f6ac-4411-984f-e3d7201d18c7)




<br>


### Adaptive Thresholding
<br>

![image](https://github.com/roshiniRK/THRESHOLDING/assets/118956165/0b5bcebc-9f8e-46cf-bcbd-8bc89cd2b492)



<br>


### Optimum Global Thesholding using Otsu's Method
<br>

![image](https://github.com/roshiniRK/THRESHOLDING/assets/118956165/f319a0ac-c702-4357-83ac-77d16da8443f)



<br>



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
