# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

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

## 💻 Program

### Developed By: Mukeshkumar V 

### Register No: 212225230193

---
1. Import the required libraries.
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```
2.Capture a frame from the webcam and save it as a JPG image.
```
cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_frame.jpg", frame)

cap.release()
```

3.Read the captured image.
```
captured_image = cv2.imread("captured_frame.jpg")
```
4.Display the captured image.
```
plt.imshow(captured_image[:, :, ::-1])
plt.title("Captured Frame")
plt.axis("off")
plt.show()
```
5.Display the live webcam video.
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```
6.Display the video after resizing.
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))

    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```
7.Rotate the video by 90° clockwise and display it.
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)

    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

## Output

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`


<img width="640" height="511" alt="Screenshot 2026-08-18 105812" src="https://github.com/user-attachments/assets/736f71c0-f484-43b7-bc76-adb00516ec71" />

### ii) Display the video
Live webcam video is displayed


<img width="649" height="478" alt="Screenshot 2026-08-18 105825" src="https://github.com/user-attachments/assets/93f842d6-dcbd-4263-9358-9aeece6bbefc" />

### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)


<img width="338" height="482" alt="Screenshot 2026-08-18 105834" src="https://github.com/user-attachments/assets/a0a7c3cf-7ff8-44a3-8c96-4c321753ce95" />

### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)


<img width="378" height="481" alt="Screenshot 2026-08-18 105843" src="https://github.com/user-attachments/assets/882f2bc7-22e4-4cfa-a570-162173e53985" />

---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
