# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** Rahul Krishna
- **Register Number:** 212223040162

  ### Ex. No. 01

```
import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('me.jpg', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```

<img width="431" height="410" alt="bccba0ca-14cd-4fa5-919a-ac76fd1a945e" src="https://github.com/user-attachments/assets/6f4c1df6-ca3f-4b12-9bf3-7d80c96888d5" />


```
# Load the image
image = cv2.imread('me.jpg')
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (0, 255, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  

plt.show()
```

<img width="431" height="410" alt="0ca8b7f9-7de8-4016-bbbd-ca9d61d4a95b" src="https://github.com/user-attachments/assets/d4c3d770-035a-45cc-b50b-cad4485d0867" />

```
# Load the image
image = cv2.imread('me.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(400,300),150,(0,255,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

<img width="431" height="410" alt="37163651-1cea-4015-85b0-9670a5fc0c55" src="https://github.com/user-attachments/assets/00ac98d3-d506-493b-8082-8685981fb4f6" />

```
# Load the image
image = cv2.imread('me.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

<img width="431" height="410" alt="41b14465-030b-48a8-98c9-7ccccd0ca30d" src="https://github.com/user-attachments/assets/751e4019-2700-4f1a-aba0-ff0bff75dc82" />

```
# Load the image
image = cv2.imread('me.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Add text to the image
text_img = cv2.putText(img_rgb, "KANAGAVEL R", (30, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (0, 0, 255), 800)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```

<img width="431" height="410" alt="54b10fff-d526-4cf8-bf6d-45bf1e9a9b6e" src="https://github.com/user-attachments/assets/1dd81155-52e2-48d4-add2-05d1342f3178" />

```
# Load the image
image = cv2.imread('me.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```

<img width="431" height="410" alt="13d6f268-88df-479b-aac9-20fbde113c77" src="https://github.com/user-attachments/assets/542232e9-6d08-4318-9758-e7572ff9539b" />

```
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```

<img width="431" height="410" alt="13d6f268-88df-479b-aac9-20fbde113c77" src="https://github.com/user-attachments/assets/05d80278-6200-453e-a359-108bc9278a4c" />

```
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```

<img width="431" height="410" alt="e311a4b8-739a-4718-ad8d-8d419fa5242a" src="https://github.com/user-attachments/assets/e9e85511-db37-4356-b700-58a3beef18ce" />

```
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```

<img width="431" height="410" alt="532cd364-8c8f-42cd-8731-91b4bf175eab" src="https://github.com/user-attachments/assets/1dd38c5b-d08d-4457-a0a3-9d59958856ae" />

```
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```

<img width="431" height="410" alt="532cd364-8c8f-42cd-8731-91b4bf175eab" src="https://github.com/user-attachments/assets/303a8e7b-d0a3-442e-8ca7-a8e192371aab" />

```
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```

<img width="431" height="410" alt="1e4408d1-ac2c-4e8f-918c-e15fbcf6cbd4" src="https://github.com/user-attachments/assets/311f7e25-293a-4505-9311-b2aee5330e1b" />

```
# Load the image
image = cv2.imread('me.jpg')
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
```

<img width="431" height="410" alt="c04411b3-1b4f-487b-930b-c06494344f70" src="https://github.com/user-attachments/assets/23603b38-4a40-4386-843f-0cf40ca53eb2" />

```
# Load the image
image = cv2.imread('me.jpg')
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
```

<img width="431" height="410" alt="70ac64a6-5a87-4c22-979c-51f57f494252" src="https://github.com/user-attachments/assets/8f3f5881-d9c8-446e-b22a-35ca36186303" />

```
# Load the image
image = cv2.imread('me.jpg') 
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```

<img width="493" height="410" alt="6ec392dc-19ff-4366-8bcc-c582baae555d" src="https://github.com/user-attachments/assets/9b83e205-58df-4355-af61-40c6162a16b0" />

```
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```

<img width="389" height="410" alt="62c7159d-e56f-4fb8-be44-798c2bcb114b" src="https://github.com/user-attachments/assets/fb72ce31-d473-4bca-8d68-d4d59b926f3f" />


## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
