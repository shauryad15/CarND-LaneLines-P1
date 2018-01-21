# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied gaussian blur with kernel size 5 to remove the noise from the image.

Then i used canny edge detection technique to detect the edges from the image.

Then i applied mask to select the region of interest of my image.

Then i used hough transform to draw the lines on the image.
Finally i combined the orginal image with hough transformed image to get the required output.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by wasn't able to figure out the technique. Tried a few but the lines weren't overlapping with the lanes. So left as of now.

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One shortcoming is the to average and extrapolate image to show the single line overlapping with the lanes rather than multiple lines.

Another shortcoming is the curved lanes where my pipeline fails to determine the lanes correctly.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to average and extrapolate lines.

Another potential improvement could be to use these funtions properly for the curved lanes.
