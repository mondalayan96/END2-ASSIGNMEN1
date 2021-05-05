# END2-ASSIGNMENT1
Question 3:

1.) What is a neural network neuron?

Ans- A neural network neuron is a mathematical function based on the model of a biological neuron. It is the fundamental &#39;memory storage&#39; or a &#39;signal&#39; unit of a neural network. A neuron consists of a set of weights(wi) and an activation function and receives a set of inputs(xi). The neuron computes the weighted sum of these inputs, and this sum is passed through a non-linear function called activation function to generate the output. The output of the neuron can be sent as input to the neurons of another layer or it could be the actual output of the neural network.

Let there be n inputs to the neuron, the output can be represented as : 

   <img src="https://render.githubusercontent.com/render/math?math=z = \tanh ( \sum_{i=1}^{n}  {w}_{i} {x}_{i} + b )">


where , b = bias of the neuron

2.) What is the use of the learning rate?

Ans- The learning rate is a hyper-parameter used in training of neural network that controls how much we are adjusting the weights of our network with respect to the loss gradient.
A small learning rate requires many updates to reach the minimum point whereas a larger learning rate causes drastic updates which may miss the minimum point. So, we should initialize a learning rate such that it swiftly reaches the minimum point.

3.) How are weights initialized?

Ans- Different techniques of weight initialization are as follows:

i. Random Normal Initialization - A random value is chosen such that it follows a normal distribution with a mean of 0 and standard deviation of 1.

ii. Uniform Initialization - A random value is chosen such that it follows a uniform distribution. The main idea of this initialization is to initialize the weights without being too small but close to zero in the range [-y, y], where y = 1 / sqrt (n) (n is the number of input units given to the neuron).

iii.Xavier Normal Initialization - A random value is chosen such that it follows a normal distribution with a mean of 0 and standard deviation (σ) = sqrt (2 / (fan\_in + fan\_out)), where fan\_in is the number of input units given to the neuron and fan\_out is the number of output units.

iv. Xavier Uniform Initialization - A random value is chosen such that it follows a uniform distribution, in the range [-y, y], where

y = sqrt (6) / sqrt (fan\_in + fan\_out), where fan\_in is the number of input units given to the neuron and fan\_out is the number of output units.

v. He Normal Initialization - A random value is chosen such that it follows a normal distribution with a mean of 0 and standard deviation (σ) = sqrt (2 / (fan\_in) ), where fan\_in is the number of input units given to the neuron.

vi. He Uniform Initialization - A random value is chosen such that it follows a uniform distribution, in the range [-y, y], where

y = sqrt (6) / sqrt (fan\_in), where fan\_in is the number of input units given to the neuron.

4.) What is &quot;loss&quot; in a neural network?

Ans - Loss is the prediction error of the neural network. Loss is used to calculate the gradients.
