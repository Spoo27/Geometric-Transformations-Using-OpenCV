# Geometric Transformations Using OpenCV

## Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation  
- Image Scaling (Resizing)  
- Image Shearing  
- Image Reflection (Flipping)  
- Image Rotation  

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in color mode.

### Step 3: Image Translation
- Create a translation matrix to shift the image  
- Move the image 50 pixels to the right and 80 pixels down  
- Apply transformation using `cv2.warpAffine()`  
- Display original and translated images  

### Step 4: Image Scaling
- Resize the image to 0.5× (downscale)  
- Resize the image to 2× (upscale)  
- Use `cv2.resize()`  
- Display original, downscaled, and upscaled images  

### Step 5: Image Shearing
- Create transformation matrices for:
  - Horizontal shearing  
  - Vertical shearing  
- Apply transformations using `cv2.warpAffine()`  
- Display original and sheared images  

### Step 6: Image Reflection
- Perform flipping using `cv2.flip()`:
  - Horizontal reflection  
  - Vertical reflection  
  - Both axes  
- Display all reflected images  

### Step 7: Image Rotation
- Create rotation matrices for:
  - 45° rotation  
  - 90° rotation  
- Use `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`  
- Display original and rotated images  

---

##  Program

### Developed By:
## Name: Spoorthi V 
### Register No: 212224230271
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Qno. 1.jpeg')
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('off')

tx, ty = 100, 50 
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  # Translation matrix: 
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0])) 
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  
plt.title("Translated Image")  
plt.axis('off')

fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB)) 
plt.title("Scaled Image")  
plt.axis('off')

shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  # Display the sheared image
plt.title("Sheared Image")  
plt.axis('off')
reflected_image = cv2.flip(image, 2)
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  
plt.title("Reflected Image")  
plt.axis('off')
(height, width) = image.shape[:2]  
angle = 45 
center = (width // 2, height // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  
plt.title("Rotated Image")  
plt.axis('off')
x, y, w, h = 100, 100, 200, 150 
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image")  
plt.axis('off')
```
## Output
<img width="592" height="461" alt="image" src="https://github.com/user-attachments/assets/80036e74-0b43-42d7-917b-4d022f092a1d" />
<img width="586" height="475" alt="image" src="https://github.com/user-attachments/assets/75b380f1-066c-4be0-90ee-b37f6330e0e6" />
<img width="610" height="217" alt="image" src="https://github.com/user-attachments/assets/b6716f9e-31c8-45c4-9ed2-8d733f5581d2" />
<img width="590" height="466" alt="image" src="https://github.com/user-attachments/assets/0f4e9cb5-56ca-46e2-80ef-634d7b924aa8" />
<img width="586" height="472" alt="image" src="https://github.com/user-attachments/assets/db8bcead-6e2f-4c8d-95c5-fb00c4a607d3" />
<img width="578" height="460" alt="image" src="https://github.com/user-attachments/assets/c82ac68d-6590-4ef8-a818-b5c75b959eb0" />
<img width="581" height="458" alt="image" src="https://github.com/user-attachments/assets/985121d3-7440-4ab8-b50f-ebf2553aa975" />


##  Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
