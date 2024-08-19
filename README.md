In this project, I use functions from OpenCV to create a Lane Detection script.

EdgeDetectiononSingleImage.py
- Reads an image containing lanes
- Converts to Gray Scale
- Applies Gaussian Blur to reduce image noise and smoothen image
- Uses Canny to perform edge detection on image

EdgeDetectOnVideo.py
- Applying to functions and resources learned from EdgeDetectiononSingleImage.py, I attempt to create a lane detection script on a 40 second video
- Challenges:
-     Need to create an Region of Interest for more accurate line detection
-       In doing so, I needed to generate a mask.
-       Assuming height, and width is from middle to bottom of the image, I set the region of interest.
- Using HoughLinesP, I was able to generate lines per frame of the image and adjust parameters needed for accurate lane detection
  
