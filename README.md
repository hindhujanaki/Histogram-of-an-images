## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Developed By: G.HINDHU
# Register Number: 212223230079

import cv2
import numpy as np
import matplotlib.pyplot as plt
gray_image = cv2.imread('panda.jpeg', cv2.IMREAD_GRAYSCALE)
plt.title("Grayscale Image")
plt.imshow(gray_image, cmap='gray')
plt.axis('off')
# Step 3: Plot the histogram of the grayscale image
plt.title("Histogram of Grayscale Image")
plt.hist(gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
plt.tight_layout()
plt.show()
# Step 4: Apply histogram equalization using OpenCV
equalized_gray_image = cv2.equalizeHist(gray_image)
# Step 5: Display the histogram of the equalized image
plt.title("Histogram of Equalized Grayscale Image")
plt.hist(equalized_gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
# Step 6: Display the enhanced grayscale image
plt.title("Enhanced Grayscale Image")
plt.imshow(equalized_gray_image, cmap='gray')
plt.axis('off')
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 1: Get the input color image
color_image = cv2.imread('bird.jpg')
# Step 2: Display the input color image
plt.title("Input Color Image")
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.axis('off')
# Step 3: Plot the histogram of the input color image (combined channels)
# Calculate the histogram for all channels separately
hist_b = cv2.calcHist([color_image], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_image], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_image], [2], None, [256], [0, 256])
# Plot the histograms
plt.title("Histogram of Input Color Image")
plt.plot(hist_b, color='blue', label='Blue channel')
plt.plot(hist_g, color='green', label='Green channel')
plt.plot(hist_r, color='red', label='Red channel')
plt.show()
plt.title("Histogram Equalized Image")
plt.imshow(equalized_color_image[:,:,::-1])
plt.axis('off')
# Step 4: Apply histogram equalization to each channel of the color image
blue_channel_eq = cv2.equalizeHist(color_image[:, :, 0])
green_channel_eq = cv2.equalizeHist(color_image[:, :, 1])
red_channel_eq = cv2.equalizeHist(color_image[:, :, 2])
# Step 5: Merge the equalized channels back into a color image
equalized_color_image = cv2.merge([blue_channel_eq, green_channel_eq, red_channel_eq])

```
## Output:
### Input Grayscale Image and Color Image

![image](https://github.com/user-attachments/assets/c42390bf-7326-42b8-90ae-27f1a5a9eac4)

### Histogram of Grayscale Image and any channel of Color Image

![image](https://github.com/user-attachments/assets/b5f297c5-1f34-4098-9261-8d95a4501ca2)

### Histogram Equalization of Grayscale Image.

![image](https://github.com/user-attachments/assets/ba5d4bcc-1acd-45e5-8af2-f03c4d602d14)

![image](https://github.com/user-attachments/assets/b746f535-deb3-42f7-b2df-a7fc408c8c5c)

![image](https://github.com/user-attachments/assets/b3ed9135-f9ec-4fb0-b7f8-623e31573099)

![image](https://github.com/user-attachments/assets/c0ebd3a2-391c-470b-98d1-b28bc51fef2c)

![image](https://github.com/user-attachments/assets/74f49dc6-3d39-4e08-bebc-e63e86d2785f)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
