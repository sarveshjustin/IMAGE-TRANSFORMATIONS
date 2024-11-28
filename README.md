```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Qn4.jpg')
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")  
plt.axis('off') 
(-0.5, 635.5, 437.5, -0.5)
tx, ty = 100, 50  
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))  
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB)) 
plt.title("Translated Image")  
plt.axis('off')
(-0.5, 635.5, 437.5, -0.5)
fx, fy = 5.0, 2.0 
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))
plt.title("Scaled Image")
plt.axis('off')
(-0.5, 3179.5, 875.5, -0.5)
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))
plt.title("Sheared Image")
plt.axis('off')
(-0.5, 635.5, 437.5, -0.5)
reflected_image = cv2.flip(image, 2) 
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB)) 
plt.title("Reflected Image") 
plt.axis('off')
(-0.5, 635.5, 437.5, -0.5)
(height, width) = image.shape[:2] 
angle = 45
center = (width // 2, height // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))
plt.title("Rotated Image")
plt.axis('off')
(-0.5, 499.5, 499.5, -0.5)
x, y, w, h = 100, 100, 200, 150  
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image")
plt.axis('off')

```
