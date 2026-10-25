# Deep Neural Network(DNN) Architecture
It is a chain of layers trying to port model weights to specific task using the relevent data.

## Neuron
It is a building block of each layer. Each neuron can be represented by the simple mathematical equation.

```math
 y = \sum_{i=1}^{k}{W_i X_i} + b \\
 W_i - weight \space vector \\
 X_i - input \space vectors \\
 b - bias \space value
 y - output scalar value
```

## Layers
a DNN has sequence of layers, each with specific properties and set of neurons.
- Each input will be converted to vectors and passed through each each neuron in the first layer.
- Each subsequent layer takes output from the previous layer as the input.
- If the layer `i-1` has `m` neurons, then all the `m` outputs will be used to construct a vector of dimension `m` and passed to each neuron in the `i`'th layer.


### Type of Layers
There are different types of layers in the DNN. These layers are used in combination to improve the performace and training efficiency in a single DNN.

- **Linear/Dense Layer** Connects every input neuron of the current layer to every output neuron of the previous layer to learn global patterns
- **Convolutional Layer(CNN)** Uses filters to scan data and identify spatial featurs in images
- **Recurrent Layer(RNN)** Passes information sequentially through time, designed for text, audion, and time-series data.
- **Normalization Layer(Batch/Layer Norm)** Rescale the output of specific layer using mean and variance to make training fast and stable by avoiding too small or too big values.
- **Pooling Layer** Downsamples the data(like Max pooling) to reduce spatial size and computation. For example, max pooling slides 2x2 window matrix over the input matrix only selecting max value in each window reducing the size to 50%.
- **Dropout Layer** Randomly deactivates neurons during training to prevent overfitting. During training randomly sets a chosen percentage of output from previous layer to zero while passing onto the next layer. During inference it is turned off.
- **Attention / Transformer Layer** It is also a type of layer in the DNN. But it is not purely scalar neuron. Instead we call them attention heads. Weighs the importance of different parts(like every word in a sentence) of the input data dynamically and it is widely used in modern AI.



## Attention / Transformer Layer 
Transformer layer uses something called attention heads instead of a single scalar function like neurons.

Each attention head has its own unique set of weight matrices ($W_Q, W_K, W_V$). So a self attention layer would be array of these attention heads instead of simple array of neurons. 

Each head tries to learn different aspects of same input. For example, grammer, meaning, emotion of a word.

- **The Matrix Multiplication**: It calculates three vectors for every input: Queries (what it is looking for), Keys (what it contains), and Values (the actual content). It does by multiplying input embeddings with three trained weight matrix.
- **Similarity Matching**: The layer multiplies(dot product) the Query of word A and Key of word(B) to calculate a compatibility score. It does this for every single element in the sequence (e.g., matching the word "bank" with "river" instead of "money" based on context). e.g ``Score = Q . K^T``
- **Normalisation**: These scores are divided by scalling factor(to keep numbers mathematically stable) and run through softmax function. This turns scores in percentage. These percentages represent the Attention Weights—telling the model exactly where to focus.
- **Blending the Content(the output)** those attention weights multiplied by the Values(V of each input). The layer adds up all these weighted Values to create a single, deeply contextualized vector for the input word. If a word has 90% attention weight its value is nearly passed throguh. If a word has only 10% attention weight, then its value is mostly filtered out in the context of the input word.

```math
Attention(Q,K,V) = softmax(\frac{QK^T}{\sqrt{d_k}}) V \\
d_k - dimention \space of \space K
```

### Single Attention Head of a Self Attention Layer

It simultaneously enriches the context for all input vectors in a single pass.

Here is how the dimensions actually work and why it handles everything at once.

#### 1. The Matrix Shape: Rows vs. Columns

In a standard Transformer input matrix $X$:

- **Rows** typically represent the **tokens** (words) in your sequence.
- **Columns** represent the **embedding dimensions** (the features or traits describing that word, e.g., $d_{\text{model}} = 768$ or $4096$).

So, if you have a sequence of 10 words, and each word is represented by a 768-dimensional vector, your input matrix $X$ has a shape of **$10 \times 768$**.


#### 2. What Happens in One Pass? (Matrix Multiplication)

When this $10 \times 768$ matrix enters the attention layer, it is multiplied by the weight matrices ($W_Q, W_K, W_V$) to produce the $Q, K,$ and $V$ matrices, which are also **$10 \times 768$**.

Now, look at what happens when you compute the attention scores:


$$\text{Scores} = Q \times K^T$$

- Matrix $Q$ is $(10 \times d_k)$.
- Matrix $K^T$ (transposed) is $(d_k \times 10)$.
- The resulting **Scores** matrix is **$10 \times 10$**.

#### 3. What does that $10 \times 10$ grid mean?

Every single row represents a **Query word**, and every column represents a **Key word**:

- **Row 1** contains the attention weights of word 1 looking at all 10 words.
- **Row 5** (your example) contains the attention weights of **word 5** looking at all 10 words.
- **Row 10** contains the attention weights of word 10 looking at all 10 words.

All 10 rows are computed **simultaneously** in a single parallelized matrix multiplication step on the GPU.


#### 4. The Final Output

When you multiply those attention weights by the Value matrix ($V$), you get a final output matrix of shape **$10 \times 768$**.

- **Row 5** of this output matrix is now a fully contextualized vector for word 5, rich with information from words 1 through 10.
- At the exact same time, **Row 1** is a fully contextualized vector for word 1, and **Row 10** is for word 10.
- If you multiply a first row with all the columns, then it bring the context of all the word to the first word based on how much attention each word has for the first word.

You aren't looping through words one by one. The Transformer treats the entire sentence as a single image or grid, multiplying matrices so that **every word computes its relationship with every other word at the exact same millisecond**.