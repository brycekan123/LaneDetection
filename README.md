In this project, I use functions from OpenCV to create a Lane Detection script on a sample movie.

# EdgeDetectiononSingleImage.py
First, to get a grasp of OpenCV, I attempted to perform edge detection on a single image.
- Reads an image containing lanes
Image:
![Screenshot 2024-08-19 at 10 45 49 PM](https://github.com/user-attachments/assets/7920b138-72b5-4b30-93b2-dba86a437374)
- Crop Image
- Converts image to Gray Scale
- Applies Gaussian Blur to reduce image noise and smoothen image
- Uses Canny to apply edge detection on image
Result:
![Screenshot 2024-08-19 at 10 44 58 PM](https://github.com/user-attachments/assets/11d57670-edc6-4eaf-a670-4e2f5e1d057f)


# EdgeDetectOnVideo.py
Now, I attempt to use additional functions on top of the functions used in the Single Image script to create a Lane Detection Script on a video.
- To do this, I needed to select a region of interest for more accurate line detection. I placed ROI by applying a mask on where lanes are most common in videos.

```
def region_of_interest(img, vertices):
    #initializes image to be black. Starting withi a blank mask
    mask = np.zeros_like(img)
    #fills polygon within vertices with white color
    cv2.fillPoly(mask, vertices, 255)
    # Returning the image only where mask pixels are non-zero
    masked_image = cv2.bitwise_and(img, mask)
    return masked_image
```

![Screenshot 2024-08-19 at 11 00 51 PM](https://github.com/user-attachments/assets/5649d40b-1d8b-4bff-96ac-e6354bd1aea7)

- Using HoughLinesP, I was able to generate lines per frame of the image and adjust parameters(threshold, minLineLength and maxLineGap) needed for accurate lane detection

```
lines = cv2.HoughLinesP(roi_edges, rho=1, theta=np.pi/180,threshold= 150, minLineLength=100, maxLineGap=10)
```


Result:

![Screenshot 2024-08-19 at 10 52 10 PM](https://github.com/user-attachments/assets/2d8b5140-b31f-48fc-87ad-e763ccc52e27)
