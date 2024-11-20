# Exercise week 9

This is your 9th mandatory exercise for the track "Advanced Machine Learning for Computer Vision".
The tasks will be published on 31st October, and must be completed until a week later, i.e. Thursday 07.11.2024, 08:15. 
By that time you must fill out the checklist on the learnit page to indicate which tasks you volunteer to present. 
You are very welcome to present incomplete solutions and describe what challenges you faced.

Reminder: Check the reading material for answers to questions which have not been addressed during the lecture. 


## Task 1: Theory

a. Which projection preserves parallel lines? 

b. Describe the input and output of a Nerf. Specifically describe the 2 components for view direction, and why there are not 3 components. 

c. What training data do you need to train a Nerf?

d. Given the following 3D points $P_1​=(1,1,2)$, $P_2​=(3,0,4)$, $P_3​=(2,−1,3)$.
Assume the camera is placed directly along the z-axis (orthographic projection), which projects points onto the x-y plane. 
Write down the 2D projections of these points on the image plane. (Assume 2 cameras.)

e. Using the 2D coordinates from the previous task to create a measurement matrix $W$ in the same format as described in the Tomasi Kanade paper. 

f. Write out the SVD factorization for your measurement matrix. Only write down the equation, you do not need to compute it. What preprocessing is necessary before the factorization?
Add the dimensions to the matrices. 
Note that there are more steps to retrieve shape and motion from the measurement matrix. YOu are free to elaborate or leave them entirely for the programming task.




## Task 2: 3D reconstruction by factorization
You received data in form of 2D facial feature points from the same face, but different view angles and translations. The goal is to estimate the 3D face from those points. 
The following steps outline the procedure. (Revisit the material for the details.)
Assuming an orthographic camera model, use SVD on the measurement matrix to retrieve the projection information and the estimated 3D shape. 

Note: investigate the additional provided files. We provide a helper function to plot 3D shapes, but you are free to use your own new implementation or the previous implementation from the PCA exercise.

a. Load the data. 
The 2D shapes are in file "list_of_2Dfaces", the true 3D shape is in "face_true.npy".

b. Arrange and preprocess the 2D data points into the measurement matrix $\bf{W}$. (Follow the descriptions from lecture and reading material.) Compute the rank the measurement matrix before and after you subtract the mean per row $\bf{W}$. 

c. Perform an SVD on the measurement matrix $\bf{W} = \bf{U}\bf{\Sigma}\bf{V}^T$.

d. Retrieve the shape and motion information from the matrices, i.e. $\bf{M} = \bf{P}\bf{X}$. 

Note: The factorization using SVD only is not unique. Tomasi and Kanade suggested constraints to overcome the ambiguity. 
We will leave this as an additional exercise to you, which you can choose to address or not.

e. Visualize the approximated 2D data points with the true ones. 

f. Plot your estimated 3D shape $\bf{X}$. Investigate it from different views if necessary. 

g. Make a second plot with the ground truth 3D shape, and compare the true vs. the estimated 3D shape. What is the difference if any?

EXTRA 1: Was there an assumption which was not met? 

EXTRA 2: IF you did resolve the ambiguity: What happens if you do the 3D reconstruction with and without resolving the ambiguity? 


<!-- 2F > P -->