# Exercise week 8

This is your 8th mandatory exercise for the track "Advanced Machine Learning for Computer Vision".
The tasks will be published on 24th October, and must be completed until a week later (plus autumn break this time), i.e. Thursday 31.10.2024, 08:15.
By that time you must fill out the checklist on the learnit page to indicate which tasks you volunteer to present.
You are very welcome to present incomplete solutions and describe what challenges you faced.

Reminder: Check the reading material for answers to questions which have not been addressed during the lecture.

## Task 1: Theory

a. Describe common properties and differences between GANs, VAE, and diffusion model. 
(Note that this question is phrased very open intentionally.)

b. Revisit the reading material. Describe what the difference between DDPM and DDIM is. 

c. Explain what a Markov Chain is. If you wish to approximate a joint distribution of 5 timesteps, how would you express is using a (first order) Markov Chain? $p(x_1,...,x_5)=?$

d. Research practise: Choose one generative image or video method or tool which is available for your to use. E.g. stable diffusion. 
Try to find answers about: What data is being used? How is the model defined and trained exactly? Is the information you found enough to reimplement it? Add your sources. 
(We recommend that you add a timer to stop, otherwise you might run into a loop-hole.)


## Task 2: Implement your own Diffusion Model (DDPM)

The goal of this exercise is for you to create your own diffusion model from MNIST. 
You are welcome to use code you find to speed up to the process. If so, please share where you found it. 
The goal is to familiarize yourself with the steps.  

Note: You are welcome to start smaller and choose a 1D example or a lower resolution dataset instead. 

a. Load the MNIST database, and investigate it. 

In the following specify which references did you choose for your implementation.
Define in each step what you used, e.g. "Algorithm 1 in reading material xyz", "code snippet from ...". 

b. Forward Process: define a function which adds noise to an image. 
Be considerate about the type of noise and the size of the variables involved. 
What about normalization? 

c. Define a number of steps. We recommend that you start with a small number. 
Use the forward process function to iteratively add noise to images according to your chosen number of steps. 
Display the result for different choices (minimum 2). Does it look like expected?

d. Backward Process: Implement the reverse process where the model learns to remove noise from the noisy images. 
Train a neural network that predicts the noise added to the images so that it can be subtracted to reconstruct the original image.

e. Train your model on the MNIST dataset. 
Use Mean Squared Error (MSE) as your loss function to measure the difference between the predicted noise and the actual noise added in the forward process.

f. Image Generation: use your model to generate images. 
How good or bad are your results? 
(Note that the quality is not important.)

g. What would you need to change in your code to make it DDIM instead of DDPM?
(Adding: In the [original paper about DDIM](https://arxiv.org/abs/2010.02502) they generalize DDPMs. This question refers: What would make your code "not" DDPM.)
