# Experiment 1: Image Handling

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

## Result

Thus, basic image handling and processing operations were performed successfully using Python, OpenCV, and Matplotlib. The image was loaded, displayed, analyzed, annotated, converted into different color spaces, modified, resized, cropped, and flipped.

