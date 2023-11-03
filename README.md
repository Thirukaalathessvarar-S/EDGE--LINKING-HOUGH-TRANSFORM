# EDGE--LINKING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale.

### Step4:
Using Canny operator from cv2,detect the edges of the image.

### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.

### Step6:
Display the image and end the program.

## Program:
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("cat.jpg",0)
img_s=cv2.imread("cat.jpg",1)
img_s=cv2.cvtColor(img_s,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_s)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()

# Find the edges in the image using canny detector and display

canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()

# Detect points that form a line using HoughLinesP

lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)

# Draw lines on the image

for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_s,(x1,y1),(x2,y2),(255,0,0),3)

# Display the result

plt.imshow(img_s)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output
### Input image and grayscale image
![dip1_exp9](https://github.com/Thirukaalathessvarar-S/EDGE--LINKING-HOUGH-TRANSFORM/assets/121166390/9ac404c4-bcbc-43ae-bae2-e1182cef6b02)


### Canny Edge detector output
![dip2_exp9](https://github.com/Thirukaalathessvarar-S/EDGE--LINKING-HOUGH-TRANSFORM/assets/121166390/8c020814-153a-49d9-9a8f-d3eaad089fd6)

### Display the result of Hough transform
![dip3_exp9](https://github.com/Thirukaalathessvarar-S/EDGE--LINKING-HOUGH-TRANSFORM/assets/121166390/1f713f2b-d686-4ad8-afb5-3bb92d15b036)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
