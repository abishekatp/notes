# Quantum Circuits

## What is boolean circuits?

In the classical world one of the fundamental ways of representing classical computation is using boolean circuits model. There are some other theoretical models for classical computation such as Turing machine model. One more thing to know is that the boolean circuit model is more fundamental model than the Turing machine model because boolean circuits directly align with how we think about implementing these operations in a hardware level. Since we are trying to learn about quantum circuit model we won't focus on the Turing machine model in this blog.


Now more specifically the boolean circuits are made up of boolean gates and wires. The commonly used boolean gates are AND($\land$), OR($\lor$) and NOT($\lnot$). I assume that most of you already know about these boolean gates so I am not going to explain about them further. Eventhough we call this model a circuit model(usually circuit means closed path), the feedback loops or closed paths are not allowed in the boolean circuit model. 


Already you might have guessed why do we call this circuit a boolean circuit? you are correct its because these circuits operates on boolean inputs(or which we call bits 0 or 1). In boolean circuit wires carry either 0 or 1 and boolean gates apply boolean operation on them.


### Arithmetical circuits

The arithmetic circuits are similar to the boolean circuits. The main difference is that these circuits represent arithmetical operations instead of boolean operations(like addition(+), subtraction(-), multiplication($\times$) and division($\div$)). 

One useful connection between boolean and arithmetical circuits is that we can construct equivalent arithmetical circuit for any boolean circuit using the given below equations. If we apply boolean values, then both boolean circuits and their equivalent arithmetical circuits will give the same result.

$$
a \lor b = 1 - (1-a)(1-b) \\
a \land b = a \times b  \\
\lnot a = 1-a
$$


## What is Quantum circuits?

Similar to how we use boolean circuits to represent classical computation, We use quantum circuits to represent quantum computations. Similar to the classical gates, we use quantum gates to represent quantum operations on the quantum information.

In previous blogs we have learnt about the operations on quantum information represented by a unitary matrices. In the quantum circuit we will represent those unitary operations using quantum gates. In the circuit diagram we represent the quantum gates by different shapes like square and circles with some labels. For example the Hadamard operation is represented by a square box with label H in the center of the box like given below. 


# Inner products, Orthonormal sets and Projective measurements

## What is inner product?

We have learnt about the row vector(`bra` notation) and column vector(`ket` notation) in previous lessons.  We have seen that the natural way of multiplying row vector with another row vector or column vector with another column vector is using tensor product. Similarly the natural way of multiplying row vector with column vector or column vector with row vector is using matrix multiplication. The specific case of multiplying row vector with the column vector using the matrix multiplication is called inner product. 

To understand the matrix multiplication of row vector with the column vector, we first understand the relationship between column vector and row vector. Usually we use column vector to represent the quantum state of the quantum system. We define the row vector as the conjugate transpose of the column vector and vice versa.

Suppose lets define the following column vector and its conjugate transpose.

$$
\begin{equation}\tag{1}
\begin{split}
|\psi\rangle &= 
\begin{pmatrix}
\end{pmatrix} \\

\langle \psi| &= (|\psi\rangle)^{\dagger}
\end{split}
\end{equation}
$$


## What is othogonal set?


## What is orthonormal sets?


## How do we compute projection matrix?


## How can we do the projective measurement?

> **A different way of thinking about projective measurement**\
> In the standard basis measurement we can only get the probability associated with the one of the classical states of the quantum system. But sometime we may need measure the outcome based on some other basis such as Bell basis. In that case the standard basis measurement doesn't give us any direct way(We will see soon that there is a way to do this using standard basis measurement also using some indirect way) of measuring the probability associated with one of the states from the Bell basis. 
> You can think of the standard basis measurement as one of the kind of projective measurements that project any quantum state vector $|\psi\rangle$ onto the standard basis set(remember that standard basis set is also a orthonormal basis set). So this way we get the probability associated with each state of the classical state set. 
> Since we can define the projection matrix for any orthonormal basis set and Bell basis is also a orthonormal basis, We can compute a projection matrix for the Bell basis. Now this new projection matrix will project any quantum state vector onto the each state of the Bell basis. Here again by projecting I mean measuring the probability associated with each state of the Bell basis. This way the projective measurement gives us a general and more intutive way of measuring quantum state vector $|\psi\rangle$ by not only based on the classical state set but also based on any orthonormal basis set that spans the vector space of the quantum state vector $|\psi\rangle$.
> Soon we will see that we can represent any projective measurement by some quantum circuits with unitary operation followed by a standard basis measurement. So Projective measurement doesn't give us any specific advantage over the standard basis measurement. Rather It gives us more intutive and general way of defining the measurement of quantum systems
> Remember that the Bell basis is an orthonormal basis set that spans the four dimensional vector space(that represents two qbits). Because all the four vectors in the bell basis are unitary and they are orthogonal(inner product is 0) to each other.


# Limitations on quantum information


