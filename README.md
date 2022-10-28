# Python Neural Network only using NumPy
A Neural Network written in Python without the use of any ML libraries, so only NumPy. It will be trained on the [MNIST](https://www.kaggle.com/datasets/oddrationale/mnist-in-csv?resource=download) dataset, but in csv format, because it is much easier to use.


## Network Structure
__NOTE: GitHub uses latex syntax for inline maths, the syntax is correct (tested in latex) but my browser is not displaying some of it correctly__

#### Syntax (note the layer is the list of activated latent variables):
 * $L_{in}$: the input layer
 * $L_{out}$: the output layer
 * $L_h$: the hidden layer (there will be only one)
 * $\sigma_x$: activarion function where $x$ signifies the actual function itself
 * $z$: the latent variables
 * $Z_l$: list of all variables in layer $l$
 * $x$: input neurons
 * $y$: output neurons
 * $(b_1, ..., b_n)$: the weights, $n$ is the number of neurons
 * $b_0$: the bias

#### Predicting (Forward Propagation)
To get a prediction out of the network, I will be using forward propagation, with ReLU for the hidden layer and softmax for the output layer. I will use ReLU because it acts like a linear function but it isn't, meaning that complex features can be learned and I can also use gradient descent for my backpropagation. I will be using softmax for the output layer because it is great for multi-class classification problems, which is exactly what I am doing here, another bonus is that softmax will give me a confidence (out of 1) for the given prediction. Here is the maths for forward propagation, starting with the equation for the latent variables:

$z = b_0 + \sum ^{m}_{i=1} (x_i + b_i )$

and $Z_h = \{z_1, z_2, ..., z_n\}$, also:
$L_h = g_{ReLU}(Z_h)$.

Then, to get the output variables we can use:

$y=b_0 \sum ^m_{i=1} (g_{ReLU}(z_i) + b_i)$

where $Z_{out} = \{y_1, y_2, ..., y_n\}, and finally activate the neurons to get: $L_{out} = g_{softmax}(Z_{out})$


## Requirements 
The requirements for the project are:
* numpy 
* pandas

They can be installed using `pip install -r requirements.txt`
