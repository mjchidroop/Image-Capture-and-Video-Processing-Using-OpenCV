# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## Program

### Developed By:
**Name:** Chidroop M J  

### Register No:
212225240029  

---

### 1. Import the required libraries.
```python
import cv2
```

### 2. Initialize the webcam using cv2.VideoCapture().
```python
cap = cv2.VideoCapture(0)
```

### 3. Capture a frame and write it as a JPG file using cv2.imwrite().
```python
ret, frame = cap.read()

if ret:
    cv2.imwrite('captured_image.jpg', frame)
    print("Image saved as captured_image.jpg")
else:
    print("Failed to capture image")
```

### 4. Display the live video stream using cv2.imshow().
```python
while True:
    ret, frame = cap.read()
    if not ret:
        break

    cv2.imshow('Live Video', frame)

    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

### 5. Display the video by resizing the window.
```python
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    if not ret:
        break

    resized_frame = cv2.resize(frame, (640, 480))
    cv2.imshow('Resized Video', resized_frame)

    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

### 6. Rotate and display the video.
```python
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    if not ret:
        break

    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    cv2.imshow('Rotated Video', rotated_frame)

    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

---

## Output

### i) Write the frame as JPG image
<img width="512" height="411" alt="download" src="https://github.com/user-attachments/assets/d19f45c9-cf9e-4822-8525-326902ccd12e" />

### ii) Display the video
<img width="512" height="389" alt="download" src="https://github.com/user-attachments/assets/e0398583-6285-4cb5-86dd-59dd4d16ce5e" />

### iii) Display the video by resizing the window
<img width="266" height="389" alt="download" src="https://github.com/user-attachments/assets/d9780ea7-c7c3-40dd-ab08-cd094715bfa3" />

### iv) Rotate and display the video
<img width="297" height="389" alt="download" src="https://github.com/user-attachments/assets/db595ed9-e7a4-41d7-942d-bf8e53562360" />

---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
