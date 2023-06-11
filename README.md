Exp.No : 05 
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
Date : 05.04.2023 
<br>
# Image Transformation
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
- **Step1:** Import the necessary libraries and read the original image and save it a image variable.
- **Step2:** Translate the image using 32-bit floating matrix to populate the pixel data. change the values to preference in the 3rd element of the 1st and 2nd row of the identity matrix to translate. implement the matrix on the image using cv2.warpPerspective(). 
- **Step3:** Scale the image using 32-bit floating matrix to populate the pixel data. change the values to preference in the 1st element of the 1st row and 2nd element of the 2nd row of the identity matrix to scale. implement the matrix on the image using cv2.warpPerspective().
- **Step4:** Shear the image using 32-bit floating matrix to populate the pixel data. Change the values to preference 
  - in the 2nd element of the 1st row of the identity matrix to shear on the x axis
  - in 1st element of the 2nd row of the identity matrix to shear on the y axis. <br> Implement the matrix on the image using cv2.warpPerspective().
- **Step5:** Reflect the image using 32-bit floating matrix to populate the pixel data. Change the values to  
  - row value of the original image in the 3rd element of the 2nd row with 2nd element as -1 of the identity matrix to reflect along the x axis
  - column value of the original image in 3rd element of the 1st row with the 1st element as -1 of the identity matrix to reflect along the y axis. <br> Implement the matrix on the image using cv2.warpPerspective().
- **Step 6:** Rotate the image by implementing the preferred angle value using np.radians(). Implement the matrix values as follows using 32-bit floating matrix to populate the pixel data. Implement the matrix on the image using cv2.warpPerspective().
    ```
    [[np.cos(angle),-(np.sin(angle)),0],
    [np.sin(angle),np.cos(angle),0],
    [0,0,1]]
    ```
- **Step 7:** Crop the image by taking a specific range of rows and columns from the input image.
- **Step 8:** Display all the Transformed images.

## Program:
> Developed By: Kaushika A <br>
> Register Number: 212221230048

**Image Translation**
```python
import numpy as np
import cv2

in_img=cv2.imread("mikasa.jpg",1)

#getting rows,columns,hues(if any)
rows,cols,dim=in_img.shape

#image translation
m=np.float32([[1,0,150],[0,1,100],[0,0,1]])
trans_img=cv2.warpPerspective(in_img,m,(cols,rows))

cv2.imshow("original image",in_img)
cv2.imshow("translated image",trans_img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

**Image Scaling**
```python
m=np.float32([[1.5,0,0],[0,1.8,0],[0,0,1]])
scale_img=cv2.warpPerspective(in_img,m,(cols,rows))

cv2.imshow("original image",in_img)
cv2.imshow("scaled image",scale_img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

**Image shearing**
```python
m_x=np.float32([[1,0.2,0],[0,1,0],[0,0,1]])
m_y=np.float32([[1,0,0],[0.4,1,0],[0,0,1]])

sheared_img_x=cv2.warpPerspective(in_img,m_x,(cols,rows))
sheared_img_y=cv2.warpPerspective(in_img,m_y,(cols,rows))

cv2.imshow("original image",in_img)
cv2.imshow("sheared img x-axis",sheared_img_x)
cv2.imshow("sheared img y-axis",sheared_img_y)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

**Image Reflection**
```python
in2_img=cv2.imread("maki.jpg",1)
rows2,cols2,dim2=in2_img.shape

m_x=np.float32([[1,0,0],[0,-1,rows2],[0,0,1]])
m_y=np.float32([[-1,0,cols2],[0,1,0],[0,0,1]])
reflected_img_x=cv2.warpPerspective(in2_img,m_x,(cols2,rows2))
reflected_img_y=cv2.warpPerspective(in2_img,m_y,(cols2,rows2))

cv2.imshow("original image",in2_img)
cv2.imshow("reflected img x-axis",reflected_img_x)
cv2.imshow("reflected img y-axis",reflected_img_y)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

**Image Rotation**
```python
angle=np.radians(45)
m=np.float32([[np.cos(angle),-(np.sin(angle)),0],
              [np.sin(angle),np.cos(angle),0],
              [0,0,1]])
rotated_img=cv2.warpPerspective(in2_img,m,(cols,rows))

cv2.imshow("original image",in2_img)
cv2.imshow("rotated image",rotated_img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

**Image Cropping**
```python
crop_img=in2_img[100:400,100:300]

cv2.imshow("original image",in2_img)
cv2.imshow("cropped image",crop_img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## Output:
**i)Image Translation**

<img src="https://github.com/Kaushika-Anandh/Image-Transformation/blob/main/1.PNG" width="370" height="300">

**ii) Image Scaling**

<img src="https://github.com/Kaushika-Anandh/Image-Transformation/blob/main/2.PNG" width="370" height="300">

**iii)Image shearing**

<img src="https://github.com/Kaushika-Anandh/Image-Transformation/blob/main/3.PNG" width="670" height="320">

**iv)Image Reflection**

<img src="https://github.com/Kaushika-Anandh/Image-Transformation/blob/main/4.PNG" width="670" height="410">

**v)Image Rotation**

<img src="https://github.com/Kaushika-Anandh/Image-Transformation/blob/main/5.PNG" width="390" height="390">

**vi)Image Cropping**

<img src="https://github.com/Kaushika-Anandh/Image-Transformation/blob/main/6.PNG" width="390" height="410">

## Result: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
