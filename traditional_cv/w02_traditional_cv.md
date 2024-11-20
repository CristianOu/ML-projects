# Exercise week 2

This is your 2nd mandatory exercise for the track "Advanced Machine Learning in Computer Vision".
The tasks will be published on 5th September, and must be completed until a week later, i.e. Thursday 12.09.2024, 08:15. 
By that time you must fill out the checklist on the learnit page to indicate which tasks you volunteer to present. 
You are very welcome to present incomplete solutions and describe what challenges you faced.

 
## Task 1: Programming - Image Segmentation
Note: You are welcome to use frameworks.

Building on the segmentation exercise from last week. 
You have explored the task of image segmentation in RGB color space.
Equipped with the knowledge from the lecture, choose at least one other color space, and repeat the task.
Display and describe your observations and experience.
Feel free to use other images. 

## Task 2: Programming - Edge Detection

In the lecture you were introduced to the concept of edge detection, in this exercise you should apply this new knowledge.

a. Choose which approach you want to use. You can choose to use filters as Sobel or Prewitt (as illustrated in the lecture), or more sophisticated canny edge.

b. Choose one python function to execute image filtering. Which one did you choose and which edge handling do you choose?

c. Explore and document different variants of you approach. Guiding questions (omit the ones which do not apply to your approach):

   1. Which filter type and size?
   2. Which edge handling?
   3. Which values, e.g. which threshold did you use? 
   4. How did you choose to visualize your results?

Note: When visualising be mindful that the operations might yield to values which are outside of the scope of $[0, 255]$. 

## Task 3: Theory - Convolution
You can now apply image filters via coding. In this exercise you should practise to use the concept on (digital) paper.
Compute the 1D convolution $f\star w$, for the following signals each with and without zero padding:

a.  $f=[1,5,2,1,1,6,2]$, $w=\frac{1}{2}[1, 1]$ 

b.  $f=[1,5,2,1,1,6,2]$, $w=[1, 0, -1]$ 

c.  $f=[1,5,2,1,1,6,2]$, $w=[1, -1]$ 

Moving on to one 2D example. 

d.  Compute the 2D convolution of $I$ and $K$, ie. $I\star K$, where 
$$I=\begin{pmatrix} 1 & 5 & 1\\\ 1 & 7 & 1\\\ 1 & 5 & 1 \end{pmatrix}, ~K=\frac{1}{4}\begin{pmatrix}1 & 1\\\ 1 & 1 \end{pmatrix}$$

Choose the edge handling such that the resulting image is cropped, ie. smaller than the original image $I$. 
Then describe one solution to retain the original image size, such that the output image matches. 


e. Map the following keywords to each subtask: edge filter, smoothing, low pass filter, high pass filter. 
Note: This is not a one-to-one mapping. Some might not be mapped at all or mapped to multiple. 
