# Make_Classification_on_Non
1. Make classification on non-linear data and get it ready
Let's begin by making some data.

We'll use the make_circles() method from Scikit-Learn to generate two circles with different coloured dots. There are several step
to follow:
   1.1 Input and output shapes
   1.2 Turn data into tensors and create train and test splits

2. Building a model
We'll break it down into a few parts.

  1. Setting up device agnostic code.
  2. Constructing a model by subclassing nn.Module.
  3. Defining a loss function and optimizer.
  4. Creating a training loop.
Now, we'll want a model capable of handling our `X` data as inputs 
and producing something in the shape of our `y` data as ouputs.
Let's create a model class that:
  1. Subclasses `nn.Module` (almost all PyTorch models are subclasses of `nn.Module`).
  2. Creates 2 `nn.Linear` layers in the constructor capable of handling the input and output shapes of `X` and `y`.
  3. Defines a `forward()` method containing the forward pass computation of the model.
  4. Instantiates the model class and sends it to the target `device`.

2.1 Setup loss function and optimizer
For a regression problem (predicting a number) you might used mean absolute error (MAE) loss. And for a binary classification problem (like ours), 
you'll often use binary cross entropy as the loss function. However, the same optimizer function can often be used across different problem spaces. 
For the optimizer we'll use torch.optim.SGD() to optimize the model parameters with learning rate 0.1.

Now let's also create an evaluation metric.

There are several evaluation metrics that can be used for classification problems but let's start out with accuracy. Accuracy can be measured by 
dividing the total number of correct predictions over the total number of predictions.

3. Train model
PyTorch training loop steps
Forward pass
Calculate the loss
Zero gradients
Perform backpropagation on the loss
Step the optimizer (gradient descent)
 3.1. Going from raw model outputs to predicted labels
 3.2 Building a training and testing loop
4. Make predictions and evaluate the model
In this case, the model achieves higher accuracy in terms of both testing and training.
