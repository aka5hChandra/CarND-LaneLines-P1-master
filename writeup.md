#**Finding Lane Lines on the Road** 

---

[//]: # (Image References)

[image1]: ./lane_images/solidWhiteCurve.jpg 
[image2]: ./lane_images/solidYellowCurve2.jpg 

---

### Reflection

###1. Detailed description of pipeline and draw_lines() function modification.

####My pipeline consisted of 5 steps. 

1. Convert the images to grayscale
2. Apply Gaussian blur on grayscale image
3. Find canny edges of blured image
4. Mask edges by area of interest
5. Apply Hough trasform

####In order to draw a single line on the left and right lanes, I modified the draw_lines() function as below

1.Distinguish between left or right lane by checking the sign of slope
2.Find the extreme points of lane by comparsion
3.Extraplot lane by using slop and current extreme point

Below are couple of outputs

![alt text][image1]
![alt text][image2]


###2.Potential shortcomings with current pipeline

1.This pipeline fails when lane are not stright but sharp curve. 
2.Another shortcoming is the hardcoded mask for area of interset. Which is problem when car is not 
moving in between lanes, in which case lanes are not allinged anymore as expected.

###3.Possible improvements 

1.We could implement better contour detection rather then just stright line detections for lane.
2.Insted of hardcoding mask to find area of interset, we could use tracking and machine learning to
detect lane efficiently.