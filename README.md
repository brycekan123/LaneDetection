In this project, I use functions from OpenCV to create a Lane Detection script on a sample movie.

To get a grasp of OpenCV, I attempted to perform edge detection on a single image.
EdgeDetectiononSingleImage.py
- Reads an image containing lanes
Image:
![Screenshot 2024-08-19 at 10 45 49 PM](https://github.com/user-attachments/assets/7920b138-72b5-4b30-93b2-dba86a437374)
- Crop Image
- Converts image to Gray Scale
- Applies Gaussian Blur to reduce image noise and smoothen image
- Uses Canny to apply edge detection on image
Result:
![Screenshot 2024-08-19 at 10 44 58 PM](https://github.com/user-attachments/assets/11d57670-edc6-4eaf-a670-4e2f5e1d057f)



EdgeDetectOnVideo.py
- Applying to functions and resources learned from EdgeDetectiononSingleImage.py, I attempt to create a lane detection script on a 40 second video
- Challenges:
-     Need to create an Region of Interest for more accurate line detection
-       In doing so, I needed to generate a mask.
-       Assuming height, and width is from middle to bottom of the image, I set the region of interest.
- Using HoughLinesP, I was able to generate lines per frame of the image and adjust parameters needed for accurate lane detection
  
