# Screenrecorder with Python
This application is a simple and easy first project to learn python and expand my knowledge. Basics were acquired (still on it) from the Book [How to automate the boring stuff](https://automatetheboringstuff.com/#toc).

If possible I will containerize this and use this app for other projects -> All leading to be a competent Cloud Engineer in the future.

## What does thhe app do?
This application will record your screen activities and output into a re-playable video file. No GUI is planned - maybe an add-on to this project in the future.

## Libraries Used

In this project we need three libraries, these are as followed:
- numpy
- pyautogui
- opencv-python

## Code Explanation
1. We import the needed Libraires with
```python
import numpy as np, cv2, pyautogui
```

2. We prepare our variables such as
- resolution (in this example 1920 x 1080)
- Video Codec to use (XVID)
- filename of the saved videofile at the end
- fps (can be higher)

3. This function allows you to write video frames to a file efficiently
```python
out = cv2.VideoWriter(filename, codec, fps, resolution)
```

4. We create a smaller Live-feed Window to show the user what's being recorded. This part is optional, but looks cool.
```python
cv2.namedWindow('Live', cv2.WINDOW_NORMAL)
cv2.resizeWindow('Live', 480, 270)
```

5. This is the Programm loop and does the followng from top to bottom:
- takes screenshot with pyautoGUI
- convert the screenshot to a numpy array
- BGR (default) has to be converter to RGB
- Write to output file
- "OPTIONAL" show the small live feed window
- stop recording when we press 'q'