# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0)
### Step 2:
Write the captured image using cv2.imwrite("NewPicture.jpg",frame)
### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
### Step 4:
Display the image until the loop gets over
### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
## Program:

## i) Write the frame as JPG file:
``` Python
### Developed By: YUVARAJ.S
### Register No: 22008589



import cv2

videoCaptureObject = cv2.VideoCapture(0)


while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("Yuvaraj",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```python
### Developed By: YUVARAJ.S
### Register No: 22008589
import numpy as np
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    cv2.imshow('YUVARAJ', frame)q
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```python


### Developed By: YUVARAJ.S
### Register No: 22008589


import numpy as np
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = smaller_frame

    cv2.imshow('YUVARAJ', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```python
### Developed By: YUVARAJ.S
### Register No: 22008589

import numpy as np
import cv2
im = cv2.VideoCapture(0)
while True:
    ret,frame = im.read()
    width = int(im.get(3))
    height = int(im.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smallerFrame = cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)
    image[:height//2,:width//2] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    image[height//2:, :width // 2] = smallerFrame
    image[:height//2, width//2:] = smallerFrame
    image[height//2:, width//2:] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    cv2.imshow('frame',image)
    if cv2.waitKey(1) == ord('b'):
        break
im.release()
cv2.destroyAllWindows()


```

## Output

### i) Write the frame as JPG image
![output](./frame.jpeg)


### ii) Display the video
![output](./display%20img.jpeg)


### iii) Display the video by resizing the window
![output](./resize.jpeg)



### iv) Rotate and display the video
![output](./rotate.jpeg)




## Result:
Thus the image is accessed from webcamera and displayed using openCV.
