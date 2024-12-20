# Exercise week 6

This is your 6th mandatory exercise for the track "Advanced Machine Learning for Computer Vision".

The tasks will be published on 3rd October, and must be completed until a week later, i.e. Thursday 10.10.2024, 08:15.

By that time you must fill out the checklist on the learnit page to indicate which tasks you volunteer to present.

You are very welcome to present incomplete solutions and describe what challenges you faced.

Reminder: Check the reading material for answers to questions which have not been addressed during the lecture.

## Task 1: Theory

a. Given an image of size $224\times224$ with 3 channels, and a patch size of $16\times16$, how many patches does the Vision Transformer model divide the image into? Write the steps of your calculation down in an easy to follow manner.

$224*224 / (16*16) = 196$ patches

b. The intention behind this task is that you compute attention yourself.

Given 4 tokenized image patches, each represented by a 2-dimensional vector as follows:

- Patch 1: $p_1=[1,2]^T$
- Patch 2: $p_2=[2,0]^T$
- Patch 3: $p_3=[0,1]^T$
- Patch 4: $p_4=[1,1]^T$

Assume you are given the following transformation matrices for the queries, keys, and values:

$$
W_Q =\begin{pmatrix} 1 & 0\\\ 0 & 1\end{pmatrix}, ~W_K =\begin{pmatrix} 1 & 0\\\ 0 & 0\end{pmatrix},~W_V =\begin{pmatrix} 0 & 0\\\ 0 & 1\end{pmatrix}
$$

Compute the q, k and v vectors for each patch by multiplying the patch vectors with the respective matrices. (Note that this entails all combinations.)

Then compute the attention scores between all pairs of patches

$$
score(i,j)=\bf{q}_i^T\bf{k}_j.
$$

Finally, collect the weighted sum over all to retrieve the final output using the softmax function (You can use your technical helper of choice, this is about understanding the process.)

$$
\text{out}_i = \sum_j\text{softmax}\left( score(i,j)\right) \cdot\bf{v}_j.
$$

If you are uncertain about parts of the equation, elaborate.

Try to find a solution to your question. Dare to tick the box on this even if the last step is incomplete.

c. Revisit the pros and cons of CNNs, RNNs, and Transformers.

Create your own table to compare properties of your choice.

## Task 2: Programming

This task focusses on implementing and fine-tuning vision transformers for image classification.

Your task is to implement and fine-tune a Vision Transformer model for an image classification task based on the CIFAR-10 dataset.

The task is designed to help you gain experience in applying ViTs to real-world computer vision problems.

Feel free to use the huggingface/transformers library, which provides pre-built Vision Transformer models. Load the CIFAR-10 dataset using the torchvision.datasets module.

a. Load the CIFAR-10 dataset:

    Preprocess the images by resizing them to the appropriate size for Vision Transformers (e.g., 224x224).

    Normalize the dataset using standard image normalization techniques, and describe what those are.

b. Load a pre-trained Vision Transformer model:

    Use a pre-trained ViT model from the transformers library. For example, you can use ViTForImageClassification from huggingface/transformers.

    Initialize the model with pre-trained weights (such as google/vit-base-patch16-224).

c. Fine-tune the model:

    Freeze the lower layers of the Vision Transformer to leverage the pre-trained features.

    Fine-tune the top layers of the model for CIFAR-10 image classification (10 classes).

    Use a suitable optimizer (e.g., AdamW) and a learning rate scheduler (e.g., linear decay with warmup).

d. Train the model:

    Train the model for a fixed number of epochs (e.g., 10 epochs) and monitor the validation accuracy.

    Ensure that the model outputs the classification accuracy for both the training and validation sets after each epoch.

e. Evaluation:

    After training, evaluate the model on the test set and report the final accuracy.

    Plot the training and validation loss curves and the accuracy curves.

f. Visualize the attention maps from the Vision Transformer for some test images. Discuss how the model attends to different parts of the image for classification.
