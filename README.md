# Exp -1.Image Handling and Pixel Transformations Using OpenCV
## Name : Kishor Kumar B
## Reg No : 212223240072

## AIM
Implement fundamental image processing operations using OpenCV in Python, including image loading, drawing, color space conversion, pixel manipulation, resizing, cropping, flipping, and saving images.

## Software Required
- Python 3.x
- OpenCV (cv2)
- NumPy
- Matplotlib
- Jupyter Notebook / Anaconda

## Algorithm
1. Load an image using OpenCV.
2. Display the image using Matplotlib.
3. Draw basic shapes (line, circle, rectangle) and add text.
4. Convert the image into HSV, Grayscale, and YCrCb color spaces.
5. Access and modify pixel values.
6. Resize the image.
7. Crop a Region of Interest (ROI).
8. Flip the image horizontally and vertically.
9. Save the processed image.


## Code

```python
import cv2
import matplotlib.pyplot as plt

# Read the image using OpenCV
img = cv2.imread('1ex.jpg', cv2.IMREAD_COLOR)

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()

# Load the image
image = cv2.imread('1ex.jpg')

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_rgb.shape

# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (0, 255, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)

plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('1ex.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_rgb.shape

circle_img = cv2.circle(img_rgb,(400,300),150,(0,255,0),10) # cv2.circle(image, center, radius, color, thickness)

plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('1ex.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img.shape

# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 255, 0), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)

plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('1ex.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Add text to the image
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)

plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('1ex.jpg')

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")

# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")

# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")

# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")

# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)

plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")

# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499

# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg')

image.shape

# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)

# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)

resized_image_rgb.shape

# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg')

image.shape

# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349

# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg')

# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)

# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)

# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")

# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)

# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)

# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```
## Output Images

### cell_4_0.png
![](ex1_imgs/cell_4_0.png)

### cell_11_1.png
![](ex1_imgs/cell_11_1.png)

### cell_16_2.png
![](ex1_imgs/cell_16_2.png)

### cell_21_3.png
![](ex1_imgs/cell_21_3.png)

### cell_25_4.png
![](ex1_imgs/cell_25_4.png)

### cell_29_5.png
![](ex1_imgs/cell_29_5.png)

### cell_31_6.png
<img width="512" height="313" alt="Screenshot 2026-07-24 155102" src="https://github.com/user-attachments/assets/b43105fe-00e4-40e3-9346-52aa8577c699" />



### cell_33_7.png
<img width="524" height="310" alt="Screenshot 2026-07-24 155214" src="https://github.com/user-attachments/assets/e43be6c0-c74e-4a6b-bb52-9aa5881cb9ba" /></br>
<img width="391" height="396" alt="Screenshot 2026-07-24 155209" src="https://github.com/user-attachments/assets/3ec612df-c8fb-4bb2-b1af-800e2320b1ea" /></br>
<img width="496" height="395" alt="Screenshot 2026-07-24 155203" src="https://github.com/user-attachments/assets/838e6e83-9962-4c5c-b7ef-ece27908ea63" /></br>
<img width="548" height="307" alt="Screenshot 2026-07-24 155218" src="https://github.com/user-attachments/assets/fedaf40b-5cf2-4fff-9945-03a575f29b90" /></br>
<img width="518" height="311" alt="Screenshot 2026-07-24 155157" src="https://github.com/user-attachments/assets/491cc52f-bf51-4146-aa8b-e9c67547216f" /></br>
<img width="509" height="314" alt="Screenshot 2026-07-24 155151" src="https://github.com/user-attachments/assets/0ff86300-a39d-4627-8afc-9b7e119a6d0a" /></br>
<img width="527" height="315" alt="Screenshot 2026-07-24 155145" src="https://github.com/user-attachments/assets/5caf0e94-6deb-4781-9b08-87ee3d039f34" /></br>





## Result
Successfully performed image handling and pixel transformation operations using OpenCV, including drawing, color space conversion, pixel editing, resizing, cropping, flipping, displaying, and saving images.
