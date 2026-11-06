# Ex. No: 5 – Implementation of Filters
### Developed By : VIMALRAJ B
### Register Number : 212224230304
### Aim :
To implement various image filtering techniques using Python and OpenCV to smooth images, reduce noise, and enhance image details.
### Requirements :
Hardware Requirements:
- Computer or Laptop
- Minimum 4 GB RAM
Software Requirements:
- Python
- Jupyter Notebook
- OpenCV
- NumPy
- Matplotlib
### Procedure :
1. Import the required libraries such as OpenCV, NumPy, and Matplotlib.
2. Read the input image using cv2.imread().
3. Convert the image from BGR to RGB format.
4. Apply an Average Filter using a predefined kernel.
5. Apply a Weighted Average Filter to smooth the image.
6. Apply a Gaussian Filter to reduce image noise.
7. Apply a Median Filter to remove noise while preserving edges.
8. Apply a Laplacian Kernel to highlight image details.
9. Apply the Laplacian Operator to detect edges.
10. Display the original and filtered images using Matplotlib.

### Program : 
```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("ex.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("on")
plt.show()
```
```python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("on")
plt.show()
```
```python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("on")
plt.show()
```
```python
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("on")
plt.show()
```
```python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("on")
plt.show()
```
```python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("on")
plt.show()
```

### Output : 

<img width="518" height="311" alt="image" src="https://github.com/user-attachments/assets/0f64b05c-8bc9-484b-830c-f0cba5179a84" /></br>

<img width="397" height="227" alt="image" src="https://github.com/user-attachments/assets/71c589c8-cafe-47f6-8f2b-850bf3cf2928" /></br>

<img width="382" height="233" alt="image" src="https://github.com/user-attachments/assets/3bb6d324-ff7b-4ac0-9785-38f78ae79415" /></br>

<img width="527" height="310" alt="image" src="https://github.com/user-attachments/assets/7ca69b9c-254a-40af-8b6b-dac33b15d15e" /></br>

<img width="384" height="229" alt="image" src="https://github.com/user-attachments/assets/f210b643-d3e2-4c19-9161-53dae77092fe" /></br>

<img width="387" height="234" alt="image" src="https://github.com/user-attachments/assets/6c492367-0ba8-40d0-b75e-d5512c64e6ac" /></br>


### Result :
Thus, various image filtering techniques such as Average Filter, Weighted Average Filter, Gaussian Blur, Median Blur, and Laplacian Operator were successfully implemented using Python and OpenCV. The filtered images were displayed and their effects were observed.
