# Histogram Equalization Using OpenCV (Grayscale & Color Images)

### Developed By:

**Name:** Roshan V

### Register No:

**212225240124**

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

* Read and display a grayscale image
* Apply histogram equalization on the grayscale image
* Display the equalized grayscale image
* Read and display a color image
* Convert the color image to HSV color space
* Apply histogram equalization on the Value (V) channel
* Convert the enhanced image back to BGR format
* Display the original and equalized color images
* Display the histograms of the original and equalized images

---

## Software Used

* Anaconda – Python 3.x
* Jupyter Notebook
* OpenCV (`cv2`)
* NumPy
* Matplotlib

---

## Algorithm

```text
1) Import Required Libraries
-> Import OpenCV, NumPy, and Matplotlib for image processing and visualization.

2) Read the Grayscale Image
-> Load the input image in grayscale mode using cv2.imread().

3) Display the Original Grayscale Image
-> Display the grayscale image using Matplotlib.

4) Apply Histogram Equalization
-> Enhance the contrast of the grayscale image using cv2.equalizeHist().

5) Display the Equalized Grayscale Histogram
-> Plot the histogram of the equalized grayscale image.

6) Display the Equalized Grayscale Image
-> Display the histogram-equalized grayscale image.

7) Read the Color Image
-> Load the input image in color mode using cv2.imread().

8) Convert to HSV Color Space
-> Convert the BGR image to HSV color space using cv2.cvtColor().

9) Equalize the Value Channel
-> Apply histogram equalization only to the V (Value) channel.

10) Convert Back to BGR
-> Convert the enhanced HSV image back to BGR format.

11) Display the Color Results
-> Display the original and equalized color images.

12) Display Histograms
-> Plot the histograms of the original and equalized color images.
```

---

# Program

### Developed By:

**Name:** Roshan V

### Register No:

**212225240124**

---

## STEP-1

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

---

## STEP-2

```python
img = cv2.imread('Tokyo.jpg', cv2.IMREAD_GRAYSCALE)
```

---

## STEP-3

```python
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```

### Output – Original Grayscale Image

<img width="173" height="308" alt="Screenshot 2026-08-08 144253" src="https://github.com/user-attachments/assets/f34ba0e7-e6ad-4e11-9a51-3e11caa4f70f" />

> **Image location:** `images/original.jpg`

---

## STEP-4

```python
img_eq = cv2.equalizeHist(img)
```

---

## STEP-5

```python
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')
```

### Output – Equalized Histogram

<img width="485" height="349" alt="Screenshot 2026-08-08 144318" src="https://github.com/user-attachments/assets/7612d422-4995-4100-af0b-861d250bfba5" />

> **Image location:** `images/equalized_histogram.jpg`

---

## STEP-6

```python
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```

### Output – Equalized Image

<img width="150" height="320" alt="Screenshot 2026-08-08 144337" src="https://github.com/user-attachments/assets/bc23a2bd-b7d1-4208-a1ca-80b302264c48" />

> **Image location:** `images/equalized.jpg`

---

## STEP-7

```python
img = cv2.imread('Tokyo.jpg', cv2.IMREAD_COLOR)
```

---

## STEP-8

```python
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```

---

## STEP-9

```python
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
```

---

## STEP-10

```python
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```

---

## STEP-11

```python
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.show()
```

---

## STEP-12

```python
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()
```

---

## STEP-13

```python
plt.figure(figsize=(20,10))

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.show()
```

---

## STEP-14

```python
plt.figure(figsize=[15,4])

plt.subplot(121)
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image')

plt.subplot(122)
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
```

### Output – Original Histogram

<img width="434" height="344" alt="Screenshot 2026-08-08 144409" src="https://github.com/user-attachments/assets/3c8347e4-fd15-4285-b0f3-002e417709e8" />

> **Image location:** `images/original_histogram.jpg`

---

# Output

## Grayscale Histogram Equalization

* Original grayscale image is displayed.
* Histogram equalization is applied to the grayscale image.
* Equalized grayscale image is displayed.
* Equalized histogram is plotted.

## Color Histogram Equalization

* Original color image is loaded.
* The image is converted from BGR to HSV color space.
* Histogram equalization is applied to the Value (V) channel.
* The enhanced image is converted back to BGR format.
* Original and equalized color images are displayed.
* Original and equalized histograms are displayed.

---

# Output Images

### 1. Original Image

<img width="173" height="308" alt="Screenshot 2026-08-08 144253" src="https://github.com/user-attachments/assets/c57358a3-13df-4542-b485-963a04018d0d" />

### 2. Equalized Image

<img width="485" height="349" alt="Screenshot 2026-08-08 144318" src="https://github.com/user-attachments/assets/fea9b827-c140-4576-bee6-ca1472c9057b" />

### 3. Original Histogram

<img width="150" height="320" alt="Screenshot 2026-08-08 144337" src="https://github.com/user-attachments/assets/ecf4da12-ecd5-49d6-95c5-4446f9c66ee9" />

### 4. Equalized Histogram

<img width="434" height="344" alt="Screenshot 2026-08-08 144409" src="https://github.com/user-attachments/assets/89b3b8ec-7adf-4aef-8611-009045ec2ff0" />

---

## Folder Structure

```text
Histogram-Equalization/
│
├── Ex-3.ipynb
├── Tokyo.jpg
├── README.md
│
└── images/
    ├── original.jpg
    ├── equalized.jpg
    ├── original_histogram.jpg
    └── equalized_histogram.jpg
```

---

# Result

Thus, histogram equalization was successfully implemented using OpenCV for both grayscale and color images. The contrast and brightness of the images were enhanced by redistributing the intensity values, and the corresponding histograms were obtained successfully.
