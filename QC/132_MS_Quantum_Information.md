# Quantum Information(Multiple Systems)

In the previous blog we have seen about the classical information of the multiple systems. In this blog we will see about the quantum information of the multiple systems. The ideas are going to be very similar to the probabilistic part of the classical information of the multiple systems. When you think of multiple quantum systems as a single system similar to how we thought about multiple calssical systems, then the quantum state of multiple quantum systems can be represented by a unit vector. This unit vector is same as the one which we have used to represent the single quantum system but larger. Remember that unit vector is a vector with Euclidean norm equal to 1.

## How to represent quantum state of multiple systems?

So when we think about the multiple systems together as a single system then quantum state is represented by a unit vector similar to single systems. But now the entries of the unit vector correspond to the cartesian product of the classical state sets of individual systems. For example consider two qbits $X_1$ and $X_2$ with the classical state sets $\Sigma_1$ and $\Sigma_2$ and associated unit vectors represented by $|\psi_1\rangle$ and $|\psi_2\rangle$.

$$
\begin{equation}\tag{1}
\begin{split}
&\Sigma_1=\{0,1\}  \;\;\; \Sigma_2=\{0,1\} \\
&\Sigma_1 \times \Sigma_2 = \{ 00, 01, 10, 11 \}
\end{split}
\end{equation}
$$

The following are the examples of quantum state vectors represented using the dirac notation.

$$
\begin{equation}\tag{Ex-1}
\begin{split}
&|\psi\rangle = 
\frac{2}{\sqrt{8}}|00\rangle +
\frac{1}{\sqrt{8}}|01\rangle +
\sqrt{\frac{2}{8}}|10\rangle +
\frac{1}{\sqrt{8}}|11\rangle \\

&|\psi\rangle = 
\frac{3}{5}|00\rangle +
\frac{4}{5}|11\rangle \\

&|\psi\rangle = 
\frac{1}{\sqrt{2}}|00\rangle +
\frac{1}{\sqrt{2}}|11\rangle \\

&|\psi\rangle = |11\rangle

\end{split}
\end{equation}
$$

All the above vectors are valid quantum state vectors with Euclidean norm equal to 1. Note that we use square root($\sqrt{}$) notation repeatedly to just make examples simpler to verify the Euclidean norm. There are multiple ways we can reprsent the same qunautm state vector using dirac notation. All the given below notation are valid.

$$
\begin{equation}\tag{Ex-2}
\begin{split}

|\psi\rangle &= 
\frac{1}{\sqrt{2}}|00\rangle +
\frac{1}{\sqrt{2}}|11\rangle \\

&\equiv 
\frac{1}{\sqrt{2}}|0\rangle|0\rangle +
\frac{1}{\sqrt{2}}|1\rangle|1\rangle \\

&\equiv 
\frac{1}{\sqrt{2}}|0\rangle \otimes |0\rangle +
\frac{1}{\sqrt{2}}|1\rangle \otimes |1\rangle \\

&\equiv 
\frac{1}{\sqrt{2}}|0\rangle_{X_1} |0\rangle_{X_2} +
\frac{1}{\sqrt{2}}|1\rangle_{X_1} \otimes |1\rangle_{X_2} \\

\end{split}
\end{equation}
$$

Sometimes the last equation you see above is used to declar the order of the tensor product clearly. As an example for the quantum system $(X_1,X_2,X_3)$ sometimes we will write the order of the 