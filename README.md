# Experiment 2: Image Acquisition Using Web Camera
### Developed By : LOKESH S
### Register Number : 212224240079

### Aim :
To acquire an image using a web camera, save the captured frame as a JPG file, display the video stream, and display the video by resizing the frames using Python and OpenCV.

### Requirements :
- Computer or laptop
- Web camera (built-in or external)
Software requirements
- Python
- Jupyter Notebook / Anaconda

### Procedure :
1. Import the required libraries: OpenCV, Matplotlib, IPython display, and time.
2. Open the web camera using cv2.VideoCapture(0).
3. Capture and save an image: Read a frame from the camera and save it as ex.jpg using cv2.imwrite().
4. Display the captured image: Read the saved JPG file and display it using Matplotlib.
5. Display the video: Capture and display 50 consecutive frames from the web camera. Convert each frame from BGR to RGB format before displaying it.
6. Resize the video: Resize each captured frame to 100 × 150 pixels using cv2.resize() and display it.
7. Rotate the video: Rotate each captured frame by 90 degrees clockwise using cv2.rotate() and display the rotated frame.
8. Release the web camera after completing the image and video acquisition operations.

### Program :

### Step1 : Write the frame as JPG file

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("ex.jpg", frame)
cap.release()

captured_image = cv2.imread('ex.jpg')

plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('on')
plt.show()
```

### Step2 : Display the video

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

### Step3 : Display the video by resizing the window

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

### Step4 : Rotate and display the video

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

### Output : 

### Step1 : Write the frame as JPG file
<img width="567" height="422" alt="image" src="https://github.com/user-attachments/assets/4c0283e1-d019-4363-be2c-48316e249f77" />



### Step2 : Display the video

<img width="504" height="375" alt="image" src="https://github.com/user-attachments/assets/8822c998-ca12-4a9b-9a45-1f9bbb2e71b8" />


### Step3 : Display the video by resizing the window

<img width="251" height="375" alt="image" src="https://github.com/user-attachments/assets/170659b9-6092-46e2-b395-fbc46cd1ede2" />

### Step4 : Rotate and display the video

<img width="280" height="378" alt="image" src="https://github.com/user-attachments/assets/a9457a5c-ba98-4030-b7e1-cab6d188ed1a" />

### Result: 

Thus, the image was successfully captured, saved, displayed, resized, and rotated using Python and OpenCV.
