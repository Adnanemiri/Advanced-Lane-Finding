
### Writeup / README

Here are the steps I took to build the pipeline

## 1. Camera Calibration

The goal of camera calibration is to find disstortion coefficients and the camera's parameters that will enable us to project 3D to points in real world to 2D points in the image plan. The calibration was done using 20 chessboard images taken from diffent angles.

[image1]: ./examples/undistort.png

![alt text][image1]

## 2. Apply a distortion correction to test images.

Now that I have the camera matrix and the coefficients of disstortion, I can undistort test images.

[image2]: ./examples/undistort_test.png

![alt text][image2]

## 3. Use color transforms, gradients, etc., to create a thresholded binary image.

In this part I applied color transforms and gradients in order to create a binary thresholded image containing likely lane pixels 

[image3]: ./examples/binary.png "Thresholded"

![alt text][image3]

## 4. Apply a perspective transform to rectify binary image ("birds-eye view").

In this part I rectified the binary image to have a birds-eye view :

[image4]: ./examples/warped.png
![alt text][image4]

## 5. Detect lane pixels and fit to find the lane boundary.

After rectifying our test images, I detected lane pixels and fitted the lanes.

[image5]: ./examples/poly.png
![alt text][image5]

## 7. Warp the detected lane boundaries back onto the original image.

I warped back the detected lanes by inversing the perspective transform of the detected lanes and road.

[image6]: ./examples/reverse.png
![alt text][image6]
