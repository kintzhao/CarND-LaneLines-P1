# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/gray_solidYellowCurve2.jpg "Grayscale"
[image2]: ./test_images_output/canny_solidYellowCurve2.jpg "Canny"
[image3]: ./test_images_output/mask_solidYellowCurve2.jpg "mask"
[image4]: ./test_images_output/hough_solidYellowCurve2.jpg "hough"
[image5]: ./test_images_output/weighted_solidYellowCurve2.jpg "wighted"
[image6]: ./test_images_output/guass_solidYellowCurve2.jpg "guass"
[image7]: ./test_images_output/hough_raw_solidYellowCurve2.jpg "hough_raw"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps.
-- Convert the images to grayscale. such as: ![alt text][image1]

-- Filter the guassis white noise by gaussian_blur. ![alt text][image6]

-- Detect the edge of image by canny. And Select the interest region. ![alt text][image2]![alt text][image3]

-- Extract the lines from canny_image by hough_lines using the function of draw_lines. ![alt text][image7]

-- Extract the lane lines from lines using the function of improve_draw_lines. 

--- there are many lines from the process of houghLineP,I should extract the two line as the lane line. Because of 
the rule that car running in the midddle of two lane lines, It is notice that separating line segments by their  slope ((y2-y1)/(x2-x1)) to decide which segments are part of the left line vs. the right line.  

![alt text][image4]

The raw road image with extracted lane lines drawn on it. ![alt text][image5]


### 2. Identify potential shortcomings with your current pipeline

To some extent the process may be not robust by the calculation of average gradient. the two lane lines may cross  at front against the real road in the video.

Another shortcoming could be the light effects.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to try to get the best params for the process of houghLineP 

Another potential improvement could be to change the process of image filter to extend the robustness of the light effects.

