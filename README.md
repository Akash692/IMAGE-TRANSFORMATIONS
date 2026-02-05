
## Ex.No:04
## IMAGE TRANSFORMATION
## NAME : S.T.DHANAAAKHAASH
## REG NO : 212224240032


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:

Read the input image using cv2.imread() and store it in a variable for further processing.


### Step3:

Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.

### Step4:

Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:

Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:

## i) Original Image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

```
image=cv2.imread("Chennai.png")
image.shape
```

```
#Display the images.
plt.imshow(image[:,:,::-1])
plt.title("Original Image")
plt.show()
```

## ii)Image Translation
```
# i) Image Translation
tx,ty=100,200
M_translation=np.float32([[1,0,tx],[0,1,ty]])
translated_image=cv2.warpAffine(image,M_translation, (673,419))
```

```
plt.imshow(translated_image[:,:,::-1])
plt.title("Translated Image")
plt.axis("on")
plt.show()
```

## iii) Image Scaling
```
# Image Scaling
fx,fy=2.0,1.0
scaled_image=cv2.resize(image,None,fx=fx,fy=fy, interpolation=cv2.INTER_LINEAR)
```

## iv)Image shearing
```
# Image Shearing
shear_matrix=np.float32([[1,0.5,0],[0.5,1,0]])
sheared_image = cv2.warpAffine(image, shear_matrix, (673, 419))
```

```
plt.imshow(sheared_image[:,:,::-1])
plt.title("Sheared Image")
plt.axis('on')
plt.show()
```

## v)Image Reflection
```
# Image Reflection
reflected_image = cv2.flip(image, 2)
```

```
# Show original image 
plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(image[:, :, ::-1])
plt.title("Original Image")
plt.axis('off')

# Show reflected image 
plt.subplot(1, 2, 2)
plt.imshow(reflected_image[:,:,::-1])
plt.title("Reflected Image")
plt.axis('off')

plt.tight_layout()
plt.show()
```

## vi)Image Rotation
```
# Image Rotation
(height,width) = image.shape[:2]
angle = 45
center = (width // 2, height // 2)
M_rotation=cv2.getRotationMatrix2D(center,angle,1)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))
```

```
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))
plt.title("Rotated Image")
plt.axis("off")
```

## vii)Image Cropping
```
angle = 145
center = (673 // 2, 419 // 2)
M_rotation=cv2.getRotationMatrix2D(center, angle, 1)  
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))
```

```
plt.imshow(rotated_image[:,:,::-1])
plt.title("Rotated Image")
plt.axis("off")
plt.show()
```

## Output:
### i) Original Image

<img width="561" height="642" alt="image" src="https://github.com/user-attachments/assets/f9464d96-e4dd-41e5-82ab-b7e3343c077b" />

### ii)Image Translation

<img width="842" height="559" alt="image" src="https://github.com/user-attachments/assets/64032811-3996-4a27-8ec8-da082eb4323b" />


### iv)Image shearing

<img width="804" height="543" alt="image" src="https://github.com/user-attachments/assets/7677b48f-b153-4ce4-8194-89c73fbed286" />


### v)Image Reflection

<img width="412" height="707" alt="image" src="https://github.com/user-attachments/assets/740ed224-5695-41c0-9882-76f069796a24" />


### vi)Image Rotation
<img width="508" height="618" alt="image" src="https://github.com/user-attachments/assets/ddcb87d9-4040-44a6-8b46-4b37f24d25d4" />



## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
