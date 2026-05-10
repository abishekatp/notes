# Neuron
This page explains the basic knowledge about a single Neuron and how the back propagation on
that Neuron is implemented. Also this explains how we can stack up those Neurons to create a neurol network layer. Then we can arrange these neural network layers to construct a deep neural network.

You can find the Rust implementation of this concept [here](https://github.com/abishekatp/nn_learn_andrej_karpathy/tree/main/micrograd).

## Value Object
    This value object is the programatic implementation of the theorectical Neuron.

### What is Value object:
  Value is a fundamental unit of the neural network. All the logic is build
on top of this Value Object. It will have the following properties.

- The ultimate purpose of a Value is storing some floating point number in the
    `data` field and computing it gradient value w.r.t to some arbitrary output Value that
    being computed using the Value.

- Each operation(like addition, multiplication, division of two Value objects) that is
    implemented on the Value will have its own corresponding gradient implementation. This
    gradient implementation will compute the gradient of the Value object that is being
    used with the particular operation(e.g addition, multiplication, etc) to compute some
    output Value.

- The gradient will tell you, how the small change in the `data` field of the Value
    w.r.t a particular operation will affect the output Value's `data` field.
    But remember that the `grad` field stores the global gradient of the Value.

- The global gradient of the Value will be equal to the
    gradinet of the current Value multiplied by the gradient of the output Value.
    This multiplication will continue until we reach the final output Value. Sicne
    the output Value of the current operation might be used in another computation
    together with some other operation. This is based on the chain rule of derivation.

- The global gradient will tell us how small change to the `data` field of the current Value
    will affect the final output Value's `data` field. The final output will be depending on
    the current Value either directly or indirectly.

### Use case:
- We can construct a complex expression using multiple such Values and it's implemented operations,
    then we can copute the global gradient of each of these Values using the back propogation.

- The Value is wrapped with Rc and RefCell to be able clone and reuse the same
    Value in a computation of different output Values. The `grad` field will store the
    sum of the gradient values computed for each instance of the usage of the Value.

- Suppose we have the Value A, B, C and E. C = A + B, D = A * C and E = C + D. then the gradient
    of A will be sum of gradient w.r.t C and D. This is because A will affect the final
    output Value E in two ways. The first way is through the addition with B and the second way
    is through the multiplication with C.



### The chain rule of derivation can be explained as follows:
    equation-1 -> C = A + B
    equation-2 -> F = (D * C) + E
    equation-3 -> O = F * G

- Then the local derivative of equation-1 is dC/dA = 1 and dC/dB = 1. Similarly for equation-2 are
dF/dD = C, dF/dC = D and dF/dE = 1. Similarly for equation-3 dO/dF = G and dO/dG = F.
- Then global gradient of A with respect to the final output O is defined as follow,

dO/dA => dO/dF * dF/dC * dC/dA = G * D * 1

- Similarly we can compute the global gradient of any variable in the the above equations.

- The gradient of addition operator can be derived as follows. Suppose in the equation-1 there
is a small change h in the input value A, then how will that affect the output C.

C1 = A + B
C2 = (A + h) + B
dC/dA = (C2 - C1)/((A+h)-A) = (((A+h)+B) - (A+B)) / h = (A+h+B-A-B)/h = 1

- Similarly we can derive the gradient of multiplication and other operators also.



## Neural Network

### What is Neuron?
- Each Neuron will store list of weights that are of type Value(or equivalently MVal) and
    one bias Value.

- The lenght of a input array(or list) should be equal to the length of the
    list of weights of a Neuron.

- A Neuron will adjust each of its weights to port itself to compute the expected output.
    Each weight of a Neuron are adjusted based on the corresponding `grad` property of each weight of the Neuron.

- The `grad` property of each of its weights will tell us how a small change to that weight has
    affected its output for the last passed input. Based on this we can adjust its weight
    such that it minimises the difference between computed output and actual expected output.

- By default each neuron will use the Tanh activation. which means the sum of multiplication
    of input values and their corresponding weights will be passed to the tanh function before
    returning the final output. But Neuron can also use ReLU or Linear activation function.
    The activation function is used to introduce non-linearity in the model. Otherwise
    the model might become just a linear regression model. Which is just a linear equation
    of the form y = mx + b.

### What is Layer?
- the Layer is a list of Neurons. Usually we will pass the same input to each Neuron of
    the first layer. Our intution is that each Neuron will learn differnt property of
    the same input instance.
- Other inner Layers are expected to captures complex connections among these outer layer
    Neurons.

### What is MLP?
- The MLP stands for multi layer perceptron. As we have discussed in the Layer section
    it will have multiple layers of Neurons.

- The first layer will directly depend on its inputs.
    The i'th layer will depend on outputs of the (i-1)'th layer.

- If i'th layer has 10 Neurons, then it will have 10 outputs. Then each Neuron in the (i+1)'th
    layer will have 10 inputs and 10 corresponding weights and one bias Value.

### How to Use it?
- First define a MLP with number of input for each neuron in the first layer and
    number of neurons in each layer. For example in the following code we are defining a
    MLP with 2 inputs, 16 neurons in first layer, 16 neurons in the second layer and 1 neuron in
    the last layer.
        `let mut model = MLP::new(2, vec![16, 16, 1]);`

- Then call the forward method on MLP with each input instance. The model will make a
    prediction and return a list of outputs. The length of output list will be equal to number of
    neurons in the last layer of the MLP.
        `let pre = model.forward(v);`

- Each of the predicted output will be of type MVal(Rc<RefCell<Value>>). So you can construct a
    loss of type MVal on top of these predicted outputs.
        `loss = loss + (1.0 - pre.clone() * out.as_f64());`

- The above loss calculation is just a simple example. But the actual loss can be computed using any
    logic based on the use case. Now for the loss of type MVal you can calculate gradient for all its depedencies using
        `loss.zero_grad();
            loss.backward();`

- Since the computation of loss depends on all the weights of the neural MLP either directly or indirectly,
    calling `loss.backward()` will compute the gradient each of these weights in the MLP.

- These gradient values will tell us how a small change to these weights
will affect the loss value. Weather increasing or decreasing the weights will increase or decrease the loss.

- Based on these gradient we can update the `data` field of the weights. Then go to the first step
and continue this process with next input instance.

- Remember that there are diffent ways of choosing the training data, computing the loss and
updating the weights. These decisions are made based on the specific use case.