# Exercise week 7

This is your 5th mandatory exercise for the track "Advanced Machine Learning for Computer Vision".
The tasks will be published on 10th October, and must be completed until a week later (plus autumn break this time), i.e. Thursday 24.10.2024, 08:15. 
By that time you must fill out the checklist on the learnit page to indicate which tasks you volunteer to present. 
You are very welcome to present incomplete solutions and describe what challenges you faced.

Reminder: Check the reading material for answers to questions which have not been addressed during the lecture. 


## Task 1: Theory - GAN background 
Note: Carefully revisit the reading material, and choose additional sources if needed. 

a. Briefly explain why the Generator’s loss function only depends on the Discriminator's output for generated images. (Note: different representations.)

b. Explain what mode collapse is. Look into the [Wasserstein GAN](https://arxiv.org/abs/1701.07875), and explain how this method combats the issue. 
Hint: Start with explaining the key difference between WGAN loss and the standard GAN loss in terms of how they evaluate the Generator’s success. 
Note: please feel free to use other resources. 
If you find other approaches to circumvent this problem, please add those to your discussion.

c. Discuss one potential ethical issue that could arise from this GAN’s application.


## Task 2: Programming - Generative Adversarial Networks
Training a GAN can be challenging. In this exercise we invite you to try it for yourself, and see if you can succeed. 
We provide a sample notebook, which you can use as a starting point. 
You probably need to download some data first. 

Please note: In the provided sample notebook *script_gan.ipynb*, we use [CIFAR10](https://www.cs.toronto.edu/~kriz/cifar.html). You are free to use another dataset, [MNIST](http://yann.lecun.com/exdb/mnist/) or [celebA](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html). You might find it helpful to read more about the [pytorch dataloader](https://pytorch.org/vision/0.16/datasets.html). 

Note: Remember to change the data path in the notebook.


<ol type ="a">
  <li>Complete the notebook by adding the implementation for the generator and discriminator.</li>
  <li>Which parts of the notebook have to be changed if you want to use another dataset? How do you need to change them? </li>
  <li>Please document your findings when executing the notebook. Did your training converge? How did the intermediate generated images look like?</li>
  <li>Name several things which can be changed to receive a different result after training.</li>  
  <li>Choose something to change, e.g. setting, preprocessing or parameters, and run the notebook (at least) 2 more times with different configurations. Save your results. Did the training converge? How do the generated images look like? How do the three different models perform in comparison?</li> 
</ol>

Non-mandatory: Comment on your suggestions to change the code. 