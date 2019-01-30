# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

Python and OpenCV are used in this project.


Pipeline description
--- 

The pipeline consits of 7 steps:

* Step 1: Converting the original image into a grayscale
* Step 2: Blurring the grayscale image using cv2.GaussianBlur
* Step 3: Detecting edges by applying Canny Edge detection
* Step 4: Masking the edge image to obtain an image only with lines in the region of interest
* Step 5: Detecting which edges are part of a lane line by applying a Hough transformation
* Step 6: Connecting the single lines out of the Hough transformation and extrapolating the lines within the function `draw_lines()`
* * Step 6.1: Dividing the single lines into lines that are part of the left and right lane line 
* * Step 6.2: Calculating the average position and slope of the left and right lines.  
* Step 7: Insert the detected lane lines into the original image

For a more illustrated description of the pipeline please check the file `writeup.md`.

Usage
--- 
In order to test the code run every Phyton cell within the file `P1.ipynb`. The program will load the test videos out of the `test_videos` folder and then save the annonated test videos in the folder `test_videos_output`.

