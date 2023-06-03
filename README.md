# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the image and convert the image to Grayscale.

### Step2:
Smoothen the image using Gaussian Method.

### Step3:
Apply the reqiured algorithms for Global thresholding.

### Step4:
Apply the reqiured algorithms for Adaptive thresholding.

### Step5:
Apply the required algorithms for otus's thresholding

## Program
```
Lathika Sunder
212221230054
```
```
# Load the necessary packages
import cv2
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale

BGR_image=cv2.imread('peacock.jpg')
gray=cv2.cvtColor(BGR_image,cv2.COLOR_BGR2GRAY)
plt.imshow(gray)


# Use Global thresholding to segment the image

ret,thresh1=cv2.threshold(gray,100,255,cv2.THRESH_BINARY )
ret,thresh2=cv2.threshold(gray,100,255,cv2.THRESH_BINARY_INV)
ret,thresh3=cv2.threshold(gray,100,255,cv2.THRESH_TRUNC)
ret,thresh4=cv2.threshold(gray,100,255,cv2.THRESH_TOZERO)
ret,thresh5=cv2.threshold(gray,100,255,cv2.THRESH_TOZERO_INV)


# Use Adaptive thresholding to segment the image
img= cv2.GaussianBlur(gray,(3,3),0)
th1 = cv2.adaptiveThreshold(gray, 255, cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY, 11,2) 
th2= cv2.adaptiveThreshold(gray, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY, 11,2)
plt.imshow(img,cmap='gray')
plt.title('Input Image'), plt.xticks([]), plt.yticks([])
plt.show()
plt.imshow(th1,cmap='gray')
plt.title('Adaptive Mean Thresholding'), plt.xticks([]), plt.yticks([])
plt.show()
plt.imshow(th2,cmap='gray')
plt.title('Adaptive Gaussian Thresholding'), plt.xticks([]), plt.yticks([])
plt.show()


# Use Otsu's method to segment the image 
ret2,th2 = cv2.threshold(gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)



# Display the results
plt.imshow(thresh1,cmap='gray')
plt.imshow(thresh2,cmap='gray')
plt.imshow(thresh3,cmap='gray')
plt.imshow(thresh4,cmap='gray')
plt.imshow(thresh5,cmap='gray')
plt.imshow(th2,cmap='gray')
```

## Output

### Original Image
![image](https://github.com/lathika-sunder/Thresholding/assets/95066409/d686cec1-cf83-4166-a6cb-8d6a8958b78c)

### Global Thresholding
![image](https://github.com/lathika-sunder/Thresholding/assets/95066409/ec880512-3583-40e5-8dc1-e42a3921cc20)

### Adaptive Thresholding:
![image](https://github.com/lathika-sunder/Thresholding/assets/95066409/3fbce1ce-3946-422f-a096-c37a24374317)
![image](https://github.com/lathika-sunder/Thresholding/assets/95066409/334e52bf-cdfd-4850-bcb2-731f0753b6b7)

### Optimal global Thesholding using Otsu's Method
![image](https://github.com/lathika-sunder/Thresholding/assets/95066409/3d65cf1c-5113-40b3-8c23-c4c5c016736f)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
