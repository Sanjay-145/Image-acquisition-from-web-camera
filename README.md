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
Use VideoCapture(0) to access web camera.

### Step 2:
Use imread to read the video or image.

### Step 3:
Use imwrite to save the image.

### Step 4:
Use imshow to save the image.

### Step 5:
End the program and close the output video windows by pressing 'q'.

## Program:
### Developed By:Sanjay p
### Register No:212220230042

## i) Write the frame as JPG file
```
import cv2
videoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=videoCaptureObject.read()
    cv2.imwrite("New Picture.jpg",frame)
    result=False
videoCaptureObject.release()
cv2.destroyAllWindows()

```

## ii) Display the video
```
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
   ret,frame=cap.read()
   cv2.imshow('frame',frame)
   if cv2.waitKey(1)==ord('q'):
       break
cap.release()
cap.destroyAllWindows()

```

## iii) Display the video by resizing the window

```
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```


## iv) Rotate and display the video
```
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```






## Output

### i) Write the frame as JPG image
![image](https://user-images.githubusercontent.com/75235426/162229113-e59e4044-ff22-4590-8938-6b821e4c0faa.png)

### ii) Display the video
![1](https://user-images.githubusercontent.com/75235426/162224808-4d179b92-ae36-4781-9111-5ce207d7ebc6.png)

### iii) Display the video by resizing the window
![2](https://user-images.githubusercontent.com/75235426/162224749-f37d7fc6-59f8-47b9-96d7-64954d1d16af.png)



### iv) Rotate and display the video
![image](https://user-images.githubusercontent.com/75235426/162224700-5187a421-a374-40a0-b44f-3454757dce7c.png)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
