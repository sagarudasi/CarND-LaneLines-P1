#**Finding Lane Lines on the Road**

##Writeup Template

###You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/result.jpg "Result"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

Pipeline I used is that first convert the image to grayscale. Then apply Gaussian blur.
After that use Canny Edge Detection to detect edges and apply ROI mask to this image.
Then use Hough's Line Transform algorithm to get line co-ordinates from point data.

For draw_lines function, first I categorized lines detected based on the slope value into left and right lane lines.
Then calculated average of all the x and y co-ordinates for left and right lane lines.
After that I used slope point formula to extrapolate lines and colored them red and green.

![alt text][image1]


###2. Identify potential shortcomings with your current pipeline

Following are the shortcomings as per my understanding -
1. Steep curves will result into incorrect average and thus lane lines will be drawn incorrectly
2. Faint lane lines won't get detected.
3. Lighting conditions like night and cloudy weather may result in incorrect results
4. If camera resolution changes then I will have to adjust the parameters of ROI to make it work


###3. Suggest possible improvements to your pipeline

I think calculating ROI in percent and then creating the ROI quad will help in using the same code for other image resolutions.
Also fitting curve instead of line will help on lanes which are steep.
