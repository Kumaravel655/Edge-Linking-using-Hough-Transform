# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read image and convert it to grayscale image
<br>

### Step2:
Find the edges in the image using canny detector and display
<br>

### Step3:
Detect points that form a line using HoughLinesP
<br>

### Step4:
Draw lines on the image
<br>

### Step5:
Display the result
<br>


## Program:
```Python


# Read image and convert it to grayscale image
import cv2 
import numpy as np
import matplotlib.pyplot as plt
img=cv2.imread("br.jpg",0)
img_c=cv2.imread("br.jpg",1)
img=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
plt.figure(figsize=(20,20))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img_c)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Gray Image')
plt.imshow(img)
plt.show()
# Find the edges in the image using canny detector and display
canny=cv2.Canny(img,120,150)
plt.figure(figsize=(20,20))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img_c)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Canny')
plt.imshow(canny)
plt.show()

# Detect points that form a line using HoughLinesP
lines=cv2.HoughLinesP(canny,1,np.pi/180,50,20,2)

# Draw lines on the image
blank_image = np.ones(img.shape, dtype=np.uint8)
for lin in lines:
    x1,y1,x2,y2=lin[0]
    cv2.line(blank_image,(x1,y1),(x2,y2),(255,0,0),2)
    
# Display the result
plt.figure(figsize=(20,20))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img_c)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Hough Transform')
plt.imshow(blank_image)
plt.show()

```
</br>
</br>
</br>

## Output

### Input image and grayscale image
![Screenshot (169)](https://user-images.githubusercontent.com/75234946/169675944-721625ec-67bb-45de-a2e4-767376845e1f.png)


### Canny Edge detector output
![Screenshot (171)](https://user-images.githubusercontent.com/75234946/169676008-81509b33-e58b-442f-bebc-12e99d85c6ad.png)


### Display the result of Hough transform

![Screenshot (173)](https://user-images.githubusercontent.com/75234946/169676032-b1dcdef6-0f99-4f5c-8a78-9eedfc086b87.png)



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
