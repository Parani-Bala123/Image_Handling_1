# Experiment 1: Image Handling and Pixel Transformation using OpenCV

### Name: Parani Bala M
### Reg.no: 212224230192

## Aim

To perform basic image handling and processing operations using Python, OpenCV, and Matplotlib, including image loading, displaying, drawing shapes, color space conversion, pixel manipulation, resizing, cropping, and flipping.

## Objectives

- To read and display an image using OpenCV and Matplotlib.
- To identify image dimensions and color channels.
- To draw lines, circles, and rectangles on an image.
- To add text to an image.
- To convert images into different color spaces, such as RGB, HSV, Grayscale, and YCrCb.
- To modify selected pixels in an image.
- To resize and crop an image.
- To perform horizontal and vertical flipping operations.

## Software Requirements

- Python 3.x
- OpenCV
- Matplotlib
- Jupyter Notebook

Install the required libraries:

```bash
pip install opencv-python matplotlib notebook
```

## Algorithm

1. Start the program.
2. Import the OpenCV and Matplotlib libraries.
3. Read the input image using `cv2.imread()`.
4. Convert the image from BGR to RGB format for proper display using Matplotlib.
5. Display the original image.
6. Obtain the image dimensions using the `shape` attribute.
7. Draw a line, circle, and rectangle on the image using OpenCV functions.
8. Add text to the image using `cv2.putText()`.
9. Convert the image into HSV, Grayscale, and YCrCb color spaces.
10. Modify a selected region of pixels in the image.
11. Resize the image using `cv2.resize()`.
12. Crop a region of interest using array slicing.
13. Flip the image horizontally and vertically using `cv2.flip()`.
14. Display the processed images using Matplotlib.
15. Stop the program.

## Program

### 1. Import Libraries and Read the Image

```python
import cv2
import matplotlib.pyplot as plt

img = cv2.imread("My_Image.png", cv2.IMREAD_COLOR)

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.imshow(img_rgb)
plt.title("Original Image")
plt.axis("off")
plt.show()

print("Image Shape:", img_rgb.shape)
```

## Output:
<img width="1512" height="560" alt="image" src="https://github.com/user-attachments/assets/9e806b1c-3cff-4d08-b19d-cfb5a0bf1915" />


### 2. Draw Shapes and Add Text

```python
# Draw a line
line_img = cv2.line(
    img_rgb.copy(), (0, 0), (768, 600), (255, 0, 0), 2
)

# Draw a circle
circle_img = cv2.circle(
    img_rgb.copy(), (250, 350), 200, (255, 0, 0), 10
)

# Draw a rectangle
rectangle_img = cv2.rectangle(
    img_rgb.copy(), (0, 0), (490, 610), (0, 0, 255), 10
)

# Add text
text_img = cv2.putText(
    img_rgb.copy(),
    "OpenCV Drawing",
    (10, 30),
    cv2.FONT_HERSHEY_SIMPLEX,
    1,
    (200, 200, 200),
    10
)

# Display the image with text
plt.imshow(text_img)
plt.title("Image with Text")
plt.axis("off")
plt.show()
```
## Output:

<img width="1515" height="557" alt="image" src="https://github.com/user-attachments/assets/b96e3d31-5be2-431f-a040-acd59b2a8f7a" />
<img width="1502" height="577" alt="image" src="https://github.com/user-attachments/assets/91786540-3671-4e02-9889-0dfb9a333a22" />
<img width="1508" height="567" alt="image" src="https://github.com/user-attachments/assets/13c3d6f8-e3dc-4663-99ce-2d0d6a8f2ccc" />
<img width="1508" height="565" alt="image" src="https://github.com/user-attachments/assets/65b5dee1-ab37-479d-8794-1387fa06aa5c" />

### 3. Color Space Conversion

```python
# Convert RGB to HSV
image_hsv = cv2.cvtColor(img_rgb, cv2.COLOR_RGB2HSV)

# Convert RGB to Grayscale
image_gray = cv2.cvtColor(img_rgb, cv2.COLOR_RGB2GRAY)

# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(img_rgb, cv2.COLOR_RGB2YCrCb)

# Display grayscale image
plt.imshow(image_gray, cmap="gray")
plt.title("Grayscale Image")
plt.axis("off")
plt.show()
```
## Output:

<img width="1512" height="600" alt="image" src="https://github.com/user-attachments/assets/9a3c5584-9255-4539-9e04-15d7ffb497ac" />
<img width="1503" height="610" alt="image" src="https://github.com/user-attachments/assets/c68eda21-89bc-4dfe-87f2-543e0eb6a8d8" />
<img width="1510" height="600" alt="image" src="https://github.com/user-attachments/assets/b528a66d-2bba-4994-93b5-d6363e54b79b" />
<img width="1522" height="612" alt="image" src="https://github.com/user-attachments/assets/c6649d1c-1a24-4766-85aa-85804ac2520b" />


### 4. Pixel Manipulation

```python
image = cv2.imread("My_Image.png", cv2.IMREAD_COLOR)

# Modify a selected region to white
image[40:400, 40:400] = [255, 255, 255]

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

plt.imshow(image_rgb)
plt.title("Image with White Block")
plt.axis("off")
plt.show()
```
## Output:

<img width="1500" height="567" alt="image" src="https://github.com/user-attachments/assets/ee36814d-99cd-4b1e-8d46-5b81777c4529" />

### 5. Image Resizing

```python
image = cv2.imread("My_Image.png", cv2.IMREAD_COLOR)

resized_image = cv2.resize(image, (384, 300))

resized_image_rgb = cv2.cvtColor(
    resized_image, cv2.COLOR_BGR2RGB
)

plt.imshow(resized_image_rgb)
plt.title("Resized Image")
plt.axis("off")
plt.show()

print("Resized Image Shape:", resized_image_rgb.shape)
```

## Output:

<img width="1508" height="580" alt="image" src="https://github.com/user-attachments/assets/cc757544-1e7b-4b2f-b955-6189f8e52594" />

### 6. Image Cropping

```python
image = cv2.imread("My_Image.png", cv2.IMREAD_COLOR)

roi = image[40:390, 40:390]

roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest")
plt.axis("off")
plt.show()
```
## Output:

<img width="1512" height="576" alt="image" src="https://github.com/user-attachments/assets/59c92280-3def-4151-9714-78ff55eaab56" />

### 7. Image Flipping

```python
image = cv2.imread("My_Image.png", cv2.IMREAD_COLOR)

# Horizontal flip
flipped_horizontally = cv2.flip(image, 1)

# Vertical flip
flipped_vertically = cv2.flip(image, 0)

# Display horizontally flipped image
plt.imshow(cv2.cvtColor(
    flipped_horizontally, cv2.COLOR_BGR2RGB
))
plt.title("Horizontal Flip")
plt.axis("off")
plt.show()

# Display vertically flipped image
plt.imshow(cv2.cvtColor(
    flipped_vertically, cv2.COLOR_BGR2RGB
))
plt.title("Vertical Flip")
plt.axis("off")
plt.show()
```

## Output:

<img width="1517" height="611" alt="image" src="https://github.com/user-attachments/assets/d6339d8d-3d9d-446d-ac7e-93527eee4d39" />

<img width="1503" height="631" alt="image" src="https://github.com/user-attachments/assets/c4d31c38-49a9-40aa-83e1-1c111f758030" />

## Result

Thus, basic image handling and processing operations were performed successfully using Python, OpenCV, and Matplotlib. The image was loaded, displayed, analyzed, annotated, converted into different color spaces, modified, resized, cropped, and flipped.

