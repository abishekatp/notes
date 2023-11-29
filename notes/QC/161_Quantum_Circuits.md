# Quantum Circuits


### What is Circuit model?

- In the classical world one of the fundamental ways of representing classical computation is using boolean circuits model. There are some other theoretical models for classical computation such as Turing machine model. 

- Due to the fact that the circuit model is more close to how we implement these logics using hardware, the circuit model is more fundamental than turing machine model.

### What is boolean circuits?

The boolean circuits are made up of boolean gates and wires. The commonly used boolean gates are AND($\land$), OR($\lor$) and NOT($\lnot$). Here the word circuit doesn't mean the closed path. The feedback loops and closed paths are not allowed in the boolean circuit model. The boolean circuits operate on classical state set called Bit(0 or 1 practically 0 or 5 voltage).

### Can circuit model have non boolean inputs?

In general ciruit model can also operate on non boolean inputs(though not used in practical sense). One example is arithematical circuit which uses arithematic operations instead of boolean operations. The given below is arithmetical equivalent of XOR gate.
$$
a \lor b = 1 - (1-a)(1-b) \\
a \land b = a \times b  \\
\lnot a = 1-a
$$

### What is a Quantum circuit?

Quantum circuit will operate on quantum states instead of classical states. Similar to how we use the boolean circuits to represent a classical system we use a quantum circuit to represent a quantum system.

Quantum circuits can be implemented using quantum gates(Similar to boolean gates). For example the Hadamard gate is a quantum gate that can compute the Hadamard operation on a quantum state. 


# Inner products, Orthonormal sets and Projective measurements

## What is inner product?

If we multiply a row vector with a column vector using the same rules as matrix multiplication, then it is called inner product. This is important because the inner product of a vector with itself will give us a square of Euclidean norm of that vector.

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




# Limitations on quantum information


