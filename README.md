# IMPLEMENTATION-OF-FILTERSS
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
**Step1**:Import libraries and read the saved images using cv2.imread().

**Step2** : Convert the saved BGR image to RGB using cvtColor().

**Step3**: By using the following filters for image smoothing:<br>
filter2D(src, ddepth, kernel), <br>
Box filter,<br>
Weighted Average filter,<br>
GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]),<br> 
medianBlur(src, ksize),and <br>
for image sharpening:Laplacian Kernel, Laplacian Operator.
<br>

**Step4**: Apply the filters using cv2.filter2D() for each respective filters.

**Step5**: Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().

## Program:
### Developed By   : Gownori Jayanth
### Register Number: 212221230030

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import numpy as np
image = cv2.imread("cat.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
cv2.imshow('original',original_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
kernel1 = np.ones((11,11),np.float32)/121
box_filter = cv2.filter2D(original_image,-1,kernel1)
cv2.imshow('box_filter',box_filter)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
ii) Using Weighted Averaging Filter
```Python

#ii) Using Weighted Averaging Filter
import cv2
import numpy as np
image = cv2.imread("cat.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
cv2.imshow('original',original_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
cv2.imshow('weighted_filter',weighted_filter)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
iii) Using Gaussian Filter
```Python
#iii) Using Gaussian Filter
import cv2
import numpy as np
image = cv2.imread("cat.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
cv2.imshow('original',original_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0,
sigmaY=0)
cv2.imshow('gaussian_filter',gaussian_blur)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

iv) Using Median Filter
```Python

#iv) Using Median Filter
import cv2
import numpy as np
image = cv2.imread("cat.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
cv2.imshow('original',original_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
median = cv2.medianBlur(src=original_image,ksize = 11)
cv2.imshow('median_filter',median)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
import cv2
import numpy as np
image = cv2.imread("cat.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
cv2.imshow('original',original_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
cv2.imshow('laplacian_kernel',laplacian_kernel)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
ii) Using Laplacian Operator
```Python
import cv2
import numpy as np
image = cv2.imread("cat.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
cv2.imshow('original',original_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
cv2.imshow('laplacian_operator',laplacian_operator)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## OUTPUT:
### 1. Smoothing Filters

<img width="600" alt="DIP1" src="https://github.com/JayanthYadav123/IMPLEMENTATION-OF-FILTERSS/assets/94836154/04a2ea3a-80c0-4d6c-a7cf-02acd348e553">

**i) Using Averaging Filter**

<img width="599" alt="DIP2" src="https://github.com/JayanthYadav123/IMPLEMENTATION-OF-FILTERSS/assets/94836154/35dae2b2-eca0-49c3-8091-9fd8fa1f76da">

**ii) Using Weighted Averaging Filter**
<img width="598" alt="DIP3" src="https://github.com/JayanthYadav123/IMPLEMENTATION-OF-FILTERSS/assets/94836154/50622b22-137c-4012-9117-178c9d7499c7">


**iii) Using Gaussian Filter**

<img width="599" alt="DIP4" src="https://github.com/JayanthYadav123/IMPLEMENTATION-OF-FILTERSS/assets/94836154/4405f384-d0c2-40f5-acb7-8bca182fd561">

**iv) Using Median Filter**

<img width="600" alt="DIP5" src="https://github.com/JayanthYadav123/IMPLEMENTATION-OF-FILTERSS/assets/94836154/3ed06ebe-028c-4cd3-8801-316e1d72338e">


### 2. Sharpening Filters

**i) Using Laplacian Kernal**

<img width="599" alt="DIP6" src="https://github.com/JayanthYadav123/IMPLEMENTATION-OF-FILTERSS/assets/94836154/aa9a8b9d-7cb9-488b-baed-42425935bfb6">


**ii) Using Laplacian Operator**

<img width="598" alt="DIP7" src="https://github.com/JayanthYadav123/IMPLEMENTATION-OF-FILTERSS/assets/94836154/fdc6ed6a-f513-41a1-b1db-ea09e00d9adb">


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
