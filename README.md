## EX-08 THRESHOLDING
### Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.


### Software Required
1. Anaconda - Python 3.7
2. OpenCV
 
### Algorithm
#### Step1:
Load the necessary packages.
#### Step2:
Read the Image and convert to grayscale.
#### Step3:
Use Global thresholding to segment the image.
#### Step4:
Use Adaptive thresholding to segment the image.
#### Step5:
Use Otsu's method to segment the image and display the results.
### Program
```python
DEVELOPED BY: Yuvasakthi N.C
REGISTER NO: 212222240120
```
#### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
#### Read the Image and convert to grayscale
```python
image = cv2.imread("seal.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("seal.jpg",0)
```
#### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
#### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
#### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
#### Display the results
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

### Output
#### Original Image

![image](https://github.com/IamShakthi/THRESHOLDING-/assets/117913445/fb7aa2fc-0b5e-4ec9-956b-956f08a00d0a)

#### Global Thresholding

![image](https://github.com/IamShakthi/THRESHOLDING-/assets/117913445/9a4cbf0d-ee6c-4b85-8ca2-828b9f70e9c6)

![image](https://github.com/IamShakthi/THRESHOLDING-/assets/117913445/0fe62309-30c1-4b9c-ab38-a03462fc00ab)

![image](https://github.com/IamShakthi/THRESHOLDING-/assets/117913445/3acdaa23-59e4-4452-a642-37b07466046c)
![image](https://github.com/IamShakthi/THRESHOLDING-/assets/117913445/7a7326a5-895b-410f-9a07-808e91cf70dc)
![image](https://github.com/IamShakthi/THRESHOLDING-/assets/117913445/68e0ffaf-e1d2-41ec-b6fc-eaebe8491a42)


#### Adaptive Thresholding

![image](https://github.com/IamShakthi/THRESHOLDING-/assets/117913445/3fffa686-fd1c-423f-acd5-4f6f818e967b)

![image](https://github.com/IamShakthi/THRESHOLDING-/assets/117913445/eb4ce1b9-4294-4051-ad23-870a3d5b7116)

#### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/IamShakthi/THRESHOLDING-/assets/117913445/3261f1a9-5d47-45cb-86d9-66ef963eed09)

### Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.


