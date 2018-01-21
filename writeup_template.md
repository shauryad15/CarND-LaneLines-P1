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

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by first calculating the approx values of min slope and max slope for the left lines and right lines.
According to the slopes i bifocated the points that belongs to left and right side of the image. Then i defined the region for which my lines should be drawn lowY,highY.
After that i checked whether there are sufficient points to draw the line or not,then by using Y, slope M and intercept B i calculated the X coordinates and plotted the line using polyfit.

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One shortcoming is the color selection that might fail in some cases which i'll be doing later.

Another shortcoming is the curved lanes where my pipeline fails to determine the lanes correctly,which can be solved by increasing the degree of polynomial which i'll be doing later.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to select colors yellow and white.

Another potential improvement could be to use these functions properly for the curved lanes.
