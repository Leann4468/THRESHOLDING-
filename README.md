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
DEVELOPED BY: LEANN JOBY MATHEW
REGISTER NO: 212222230074
```
#### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
![image](https://github.com/Leann4468/THRESHOLDING-/assets/121165979/ade885de-1971-4946-b85c-4b3b746b1bc7)


#### Read the Image and convert to grayscale
```python
image = cv2.imread("fly.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("fly.jpg",0)
```
![image](https://github.com/Leann4468/THRESHOLDING-/assets/121165979/bfea381a-2b43-4ada-9fdc-78072e1e01f1)

#### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
![image](https://github.com/Leann4468/THRESHOLDING-/assets/121165979/64aca85b-a708-43a4-b98c-2035cd00ddfb)

#### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
![image](https://github.com/Leann4468/THRESHOLDING-/assets/121165979/a0324aee-94e5-4a29-bb06-ab7e8ae8ca8b)

#### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
![image](https://github.com/Leann4468/THRESHOLDING-/assets/121165979/204d0c97-dabb-465b-82c5-83e7e07dd82d)

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
![image](https://github.com/Leann4468/THRESHOLDING-/assets/121165979/c1372400-20d9-4765-8947-b56f75d98f91)
![image](https://github.com/Leann4468/THRESHOLDING-/assets/121165979/2c2a4f8c-8e10-4781-b665-ea9f9f859e0c)
![image](https://github.com/Leann4468/THRESHOLDING-/assets/121165979/0dd7fa59-0850-412e-a215-7abaf9b5f316)
![image](https://github.com/Leann4468/THRESHOLDING-/assets/121165979/dfcc7e31-32b0-43ee-af80-24813dbb77f2)
![image](https://github.com/Leann4468/THRESHOLDING-/assets/121165979/1e7067cb-946f-4f1f-97ad-c95d74718402)
![image](https://github.com/Leann4468/THRESHOLDING-/assets/121165979/5293a1bb-83b7-4bbe-9049-bdef4f66ba83)
![image](https://github.com/Leann4468/THRESHOLDING-/assets/121165979/7f5b7b49-5b0c-4a29-bd99-47c971021c41)
![image](https://github.com/Leann4468/THRESHOLDING-/assets/121165979/8d9de148-28f4-4a03-afe6-319e72452629)
![image](https://github.com/Leann4468/THRESHOLDING-/assets/121165979/f0b4bef9-1c5d-4da4-bf61-6a9f9c4904d1)


### Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
