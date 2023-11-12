# Quantum Circuits

## What is boolean circuits?

In the classical world one of the fundamental ways of representing classical computation is using boolean circuits model. The boolean circuits are made up of fundamental circuit elements called gates. The most basic type of gate elements that can be used to create any kind of boolean circuits are AND($\land$), OR($\lor$) and NOT($\neg$) gates.

In the boolean circuits the wires are used to carry information and the gates are used to represent operation on the classical information. Specifically these gates represent boolean operations on the inputs. In the boolean circuit model the information is represented by bits and the boolean operations are applied on the same.

Remember that eventhough we call this model a circuit model, the feedback loop or closed paths are not allowed in these circuits. To make this clear when we draw the diagrams to represent these boolean circuits we connect and arrange them in such a way that the information will flow from the left side to the right side of the circuit diagram.

### Arithmetical circuits

The arithmetic circuits are similar to the boolean circuits. The main difference is that these circuits represent arithmetical operations instead of boolean operations(like addition(+), subtraction(-), multiplication($\times$) and division($\div$)). 

One useful connection between boolean and arithmetical circuits is that we can construct equivalent arithmetical circuit for any boolean circuit using the given below equations. If we apply boolean values, then both boolean circuits and their equivalent arithmetical circuits will give the same result.

$$
a \lor b = 1 - (1-a)(1-b) \\
a \land b = a \times b  \\
\neg a = 1-a
$$


## What is Quantum circuits?

Similar to how we use boolean circuits to represent classical computation, We use quantum circuits to represent quantum computations. Similar to the classical gates, we use quantum gates to represent quantum operations on the quantum information.

In previous blogs we have learnt about the operations on quantum information represented by a unitary matrices. In the quantum circuit we will represent those unitary operations using quantum gates. In the circuit diagram we represent the quantum gates by different shapes like square and circles with some labels. For example the Hadamard operation is represented by a square box with label H in the center of the box like given below. 


# Inner products, Orthonormal sets and Projective measurements

## What is inner product?

We have learnt about the row vector(`bra` notation) and column vector(`ket` notation) in previous lessons.  We have seen that the natural way of multiplying row vector with another row vector or column vector with another column vector is using tensor product. Similarly the natural way of multiplying row vector with column vector or column vector with row vector is using matrix multiplication. The specific case of multiplying row vector with the column vector using the matrix multiplication is called inner product. 

To understand the matrix multiplication of row vector with the column vector, we first understand the relationship between column vector and row vector. Usually we use column vector to represent the quantum state of the quantum system. We define the row vector as the conjugate transpose of the column vector.

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


## What is othogonal and orthonormal sets?


## What is Projections and Projective measurements?



# Limitations on quantum information


