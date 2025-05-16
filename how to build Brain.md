AI is taking the drastic turn with new tools and models to automate the workflow and bring new interventions to the tech world and alternative solutions to the underlying problems…. Seeing all these many are interested in learning and becoming AI Engineer or ML Engineer and many new roles are emerging when AI Agents got more recognitions with MCP.
![image](https://github.com/user-attachments/assets/1b16ec26-a07c-439b-abf6-a83a9022bd0e)

Building Brain with Deep Neural Networks
Building Brain with Deep Neural Networks
In this article I’m not going to talk about what is AI/ML and how it works.. Instead We will See “HOW TO BUILD BRAIN”.
Let’s do an old-school project like beginners used to..

Weare building Image Classification of Fashion MNIST dataset, which has 10 categories of articles of clothing.

Dataset contains: [train_images, train_labels, valid_images, valid_labels] .
When We are Building Brain or Neural Network we need three Building Blocks: Define Architecture — → Initiate Training — -> Evaluate Model

Define Architecture:
Biologically
What is the Brain? — A Organ Of Human Body Which Controls the Sensory System. Which has Neurons, which stimulates the actions to perform based the sense a human feel.
![image](https://github.com/user-attachments/assets/e5a4cfdf-99fb-43c3-a124-877af261aa75)

How It Works? — It has A Neural System with tons of neuron connected to stimulate the information received from the organs.


Neuron
What We can get from this is basic biology — Neuron: primary building block — Sends electronic impulse or signals under specific stimuli. results in the actions to be performed by the humans and activates the memory blocks and neurological developments.

Receives Signals from dendrites — — — → sends impulse down the axon — — → out through terminals

As Artificial Neural network — Results in numerical o/p with numerical i/p

Mathematically
![image](https://github.com/user-attachments/assets/668c7b40-9176-4b27-9323-f1290a76673d)

Mathematical Logics of building Neuron that mimics the human brain functions.
So, Mathematically we use Linear Regression function y = mx + b . where computer’s brain is numerical with discrete 0s & 1s, it attempts to mimic the biological neuron to stimuli the process. and x and y are input and output respectively which X → takes i/p (through dendrites), Y — -> o/p (out through Terminals), m is equivelent to w i.e,. Weights as Images that we are presenting to the computer brain it takes it as pixels, each px value takes from 0 to 255 (0 → black, 255 → white). Each px assigns weights: first weight → w0, second weight → w1 and so on…

Now the linear regression equation becomes:

y = w0x0 + w1x1 + w2x2 + ……… + b

so each image is 28 x 28 pixels gets to 784px, and here Fashion MNIST dataset has 10 categories of clothing need to be classified. Our computer brain will be subjected to learn first and based on what i has learnt it will guess the answers for the new i/p questions. each one is article of clothing. if neuron assigned to “Trouser” it labels as #1 and has highest o/p compared to other neurons, Model will guess “Trouser” for given question.

We use Keras (Deep learning Framework) integrated into Tensorflow makes this kind of model easy to build. and here we use Sequential API that allows us to stack the neural layers.

We have 2 layers in Neural Network →1. Flatten and 2. Dense layer , Flatten converts multi-dimensional data into 1D, where as Dense layer which is a “Row” of neuron each has weight (w) for each i/p [from dataset we have 10 neuron as it has 10 categories]

![image](https://github.com/user-attachments/assets/c79359fd-9689-4f21-a152-bf07e2ab1056)

Model
![image](https://github.com/user-attachments/assets/4047409d-7332-48dd-a424-a7a9f772924d)

Verifying Model: “Sequential”
784 is i/p shape for each image is in 28 x 28 px height x width, 10 is classes of clothing from dataset, parameter is : for each px there should be a weight for each of our classes. so 784 which is h * w — -> multiply with (np.uint8(10)) we get 7840 parameter counts as no_of_weights.

So far linear regression eq looks like

y = o/p

x = i/p (10 classes of clothing — as dataset has 10 categories of clothing 10 dense and flattened neurons)

w = weight 28 * 28 px

b = ? The bias is typically one per output neuron, 10

Our model is now subjected to train_images and train_labels to learn and get ready to get quizzed.

Now we need to give model a function to grade its performance and we have term called Loss Function

In this case we’ll use type function specific to classification called SparseCategoricalCrossentropy

Sparse → how our label is an integer index for our categories

Categorical → classifies the labels

Cross-entropy → its more confident it scores incorrect guess to worst score and 100% confident for wrong it scores -ve infinity

from_logits → its a linear o/p this will be transformed into probability. this can be interpreted as model’s classification confidence when its correct for given i/p.

accuracy → monitors how well they are performing.
![image](https://github.com/user-attachments/assets/82b39323-0f24-4b14-8249-40eca2c1d1e1)


Model’s Loss function and Accuracy
Evaluate the model which now has learned and ready to guess.

fit → method helps our model to study and quiz it, epoch → reviews training data, after epoch model is quizzed with validation data.

![image](https://github.com/user-attachments/assets/c613f1ab-4ddc-4372-bfed-8044e24701e4)

Model Evaluation
So Our Model at 5th epoch its (apx 80%) accurate and graded its performance well. but still need to do feature engg to optimize the model for better performance.

Now Predict Model
![image](https://github.com/user-attachments/assets/03f39517-6dd8-4410-b69c-7579a26f7272)


Model Prediction
It takes 10 data samples to predict the train_lables of each train_images.

Here our Model Brain is ready and it gets to learn and guesses the o/p, then uses what it has learnt and then based on it now it is precisely predicting with new data.

Thank you reading i hope its gets interesting to compare and learn how we build our own neural network.
