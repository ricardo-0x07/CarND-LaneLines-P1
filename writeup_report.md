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

My pipeline consisted of 6 steps. First, I converted the images to grayscale, then I performed gaussian smoothing, then I performed canny edge detection, then I defined the region of interest, the I performed the hough transform, and finally merged the line onto the original image. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by using the np.polyfit() function to determine the Hough Parameters of each line then I used the Hough parameters for the lines to filter the lines and compute the end points of the extrapolated lines, then I used the end points of the extrapolated line to draw the markers for the lane onto the image.

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when dealing with sharpe turns it may not completely identify the lane lines accurately. 

Another shortcoming could be if it detects unexpected lines in the region of interest it may cause issues with the markers drawn.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to draw markers for the curves in the the lane lines

Another potential improvement could be to remove the intermittent glitches that may occur.
