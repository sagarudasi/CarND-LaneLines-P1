#**Finding Lane Lines on the Road**
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

This project uses opencv to detect lane lines.

Pipeline
---

1. Convert image to grayscale
2. Apply gaussian blur
3. Use canny edge detection to detect edges
4. Apply a ROI (Region of interest mask)
5. Use Hough's Line Transform to convert pixels into lines
6. Add the image of lines to actual image to see combined output
