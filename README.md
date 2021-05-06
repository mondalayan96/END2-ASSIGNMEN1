# END2-ASSIGNMENT1
Question 3:

1.) What is a neural network neuron?

Ans- A neural network neuron is a mathematical function based on the model of a biological neuron. It is the fundamental &#39;memory storage&#39; or a &#39;signal&#39; unit of a neural network. A neuron consists of a set of weights(wi) and receives a set of inputs(xi). The neuron computes the weighted sum of these inputs, and this sum is passed through a non-linear function called activation function to generate the output. The output of the neuron can be sent as input to the neurons of another layer or it could be the actual output of the neural network.

Let there be n inputs to the neuron, the output can be represented as :

<p align="center"><img src="https://render.githubusercontent.com/render/math?math=z = \tanh ( \sum_{i=1}^{n}  {w}_{i} {x}_{i} \+ {b} )"> </p>
where , b = bias of the neuron

2.) What is the use of the learning rate?

Ans- The learning rate is a hyper-parameter used in training of neural network that controls how much we are adjusting the weights of our network with respect to the loss gradient.

Learning rate is used to scale the magnitude of parameter updates during gradient descent. The choice of the value for learning rate can impact two things: 1) how fast the algorithm learns and 2) whether the cost function is minimized or not.

A small learning rate requires many updates to reach the minimum point whereas a larger learning rate causes drastic updates which may miss the minimum point. So, we should initialize a learning rate such that it swiftly reaches the minimum point.

3.) How are weights initialized?

Ans - The aim of weight initialization is to prevent layer activation outputs from exploding or vanishing during the course of a forward pass through a deep neural network. If either occurs, loss gradients will either be too large or too small to flow backwards beneficially, and the network will take longer to converge, if it is even able to do so at all.

The most used weight initialization techniques are described as follows:

| **Initialization method** | **Explaination** | **Pros.** | **Cons.** |
| --- | --- | --- | --- |
| **All-zeros initialization and Constant initialization** | This method sets all weights to zeros (respectively to constant). Also, all activations in all neurons are the same, and therefore all calculations are the same, making which makes the concerned model a linear model | Simplicity | Symmetry problem leading neurons to learn the same features |
| **Random initialization** | This technique improves the symmetry-breaking process and provides much greater precision. The weights are initialized very near to zero and randomly. This method prevents from learning the same feature for input parameters | Improves the symmetry-breaking process | - A saturation may occur leading to a vanishing gradient - The slope or gradient is small, which can cause the gradient descent to be slow |
| **LeCun initialization : normalize variance** | LeCun initialization aims to prevent the vanishing or explosion of the gradients during the backpropagation by solving the growing variance with the number of inputs and by setting constant variance. | Solves growing variance and gradient problems | - Not useful in constant-width networks - Takes into account the forward propagation of the input signal - This method is not useful when the activation function is non-differentiable |
| **Xavier initialization (Glorot initialization)** | Xavier proposed a more straightforward method, where the weights such as the variance of the activations are the same across every layer. This will prevent the gradient from exploding or vanishing. | Decreases the probability of the gradient vanishing/exploding problem | - This method is not useful when the activation function is non-differentiable - Dying neuron problem during the training |
| **He initialization (Kaiming initialization)** | This initialization preserves the non-linearity of activation functions such as ReLU activations. Using the He method, we can reduce or magnify the magnitudes of inputs exponentially | Solves dying neuron problems | - This method is not useful for layers with differentiable activation function such as ReLU or LeakyReLU |

4.) What is &quot;loss&quot; in a neural network?

The Loss Function is one of the important components of Neural Networks. Loss is nothing but a prediction error of Neural Net. And the method to calculate the loss is called Loss Function. In simple words, the Loss is used to calculate the gradients. And gradients are used to update the weights of the Neural Net. This is how a Neural Net is trained.

Few of the essential loss functions, which could be used for most of the objectives.

- **Mean Squared Error (MSE)** - **MSE**  loss is used for regression tasks. As the name suggests, this loss is calculated by taking the mean of squared differences between actual(target) and predicted values.

- **Binary Crossentropy (BCE) – BCE** loss is used for the binary classification tasks. If you are using BCE loss function, you just need one output node to classify the data into two classes. The output value should be passed through a _sigmoid _activation function and the range of output is (0 – 1).

- **Categorical Crossentropy (CC)** – When we have a multi-class classification task, one of the loss function you can go ahead is this one. If you are using CCE loss function, there must be the same number of output nodes as the classes. And the final layer output should be passed through a _softmax_ activation so that each node output a probability value between (0–1).

- **Sparse Categorical Crossentropy (SCC)** – This loss function is almost similar to CCE except for one change. When we are using SCCE loss function, you do not need to one hot encode the target vector. If the target image is of a cat, you simply pass 0, otherwise 1. Basically, whichever the class is you just pass the index of that class.


5.) What is &quot;chain rule&quot; in gradient flow?

Ans - In a neural network, the loss is back propagated to adjust the weights of the network so as to minimize the difference between the resultant output vector and the target vector. This is done by computing the gradient of the loss function with respect to the network parameters. As we know, there are several layers in a neural network and the loss is computed at the final layer. To update the weights of all the layers, the gradient of the loss needs to flow to the initial layers. The chain rule associates the loss with the parameters in the hidden layers.

For the final layer l, the gradient of the loss L computed using chain rule is –

  <p align="center"> <img src="https://render.githubusercontent.com/render/math?math=\frac{\partial L  }{\partial {w}^{l}}  = \frac{\partial L}{\partial {a}^{l}} \frac{\partial {a}^{l}}{\partial {z}^{l}} \frac{\partial {z}^{l}}{\partial {w}^{l}}"> </p>
For a hidden layer l, the gradient is further broken-down using chain rule in the following way –

<p align="center"> <img src="https://render.githubusercontent.com/render/math?math=\frac{\partial L  }{\partial {a}^{l}}  = \sum \frac{\partial L}{\partial {a}^{k}} \frac{\partial {a}^{k}}{\partial {z}^{k}} \frac{\partial {z}^{k}}{\partial {a}^{l}}"> </p>
Where the layers in between the final layer and the layer for which the gradient is being computed, a is the forward output of the neuron before applying activation function, z is the forward output of the neuron after applying activation function.

