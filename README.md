# Tutorial om Variational Eigen Solvers

## Lets start with the Scrodinger equation.

<iframe width="500" height="281"
 src="https://www.getyarn.io/yarn-clip/eddce405-0154-4b32-9b2f-d2dabc776104/embed?autoplay=false"
 frameborder="0"></iframe>

The scary looking time dependent Schrodinger equation.

For some wave function $\Psi(\mathbf{x},t)$
```math
$$ 
\newcommand{\pd}[2]{\frac{\partial{#1}}{\partial{#2}}}
\newcommand{\pdd}[2]{\frac{\partial^2{#1}}{\partial{#2}^2}}
\newcommand{\si}[0]{\Psi(\mathbf{x},t)}

i \hbar \frac{\partial}{\partial t}\si = \frac{\hbar ^ 2}{2m}  \pdd \si x  + V(x)\si
```
$$

How to deal with such a complex equation ? - Use Notional Hacks

$$
\newcommand{\pd}[2]{\frac{\partial{#1}}{\partial{#2}}}
\newcommand{\pdd}[2]{\frac{\partial^2{#1}}{\partial{#2}^2}}
\newcommand{\si}[0]{\Psi(\mathbf{x},t)}



i \hbar \frac{\partial}{\partial t}\si = (\frac{\hbar ^ 2}{2m} \frac{\partial^2{}}{\partial{x}^2} +  V(x)) \si

\\[0.5in]

i \hbar \frac{\partial}{\partial t}\Psi(\mathbf{x},t) = \hat H \Psi(\mathbf{x},t)
$$

Now we have $\hat H$ that represent the Hamiltonian of a system. Here H is function of x only.
Its better but still a little ugly. Lets use sepapration of variables to simplify it even more.
Since, V(x) can be very erratic, its difficult to say much about space dependence so lets deal with time dependence here.

$$
\newcommand{\si}[0]{\Psi(\mathbf{x},t)} 

\si = \Psi(x) * \Phi(t)

\\[0.5in]

i \hbar \frac{\partial}{\partial t}\Phi(t)\Psi(x) = \hat H (\Psi(x) * \Phi(t))

$$

Dividing both sides by $\Psi(x) * \Phi(t)$

$$
\newcommand{\pd}[1]{\frac{\partial{\Phi(t)}}{\partial{#1}}}

i \hbar \frac{1}{\Phi(t)} \pd t = \frac{ \hat H \Psi (x)}{\Psi (x)}

$$

As we can see the right side is a function of time and left side is a function of x, both these have to be euivalent to a constant for this to hold true. That constant here is $E$

$$
\newcommand{\pd}[1]{\frac{\partial{\Phi(t)}}{\partial{#1}}}

i \hbar \frac{1}{\Phi(t)} \pd t = \frac{ \hat H \Psi (x)}{\Psi (x)} = E

$$

On solving the two equations we will have 

$$ 
\newcommand{\pd}[1]{\frac{\partial{\Phi(t)}}{\partial{#1}}}

\hbar \frac{1}{\Phi(t)} \pd t = E

\\[0.5in]

\Phi(t) = E ^ {\frac{-itE}{\hbar}}

$$

If I equate this into Schrodinger Equation

$$

i \hbar \frac{\partial}{\partial t}\Psi(\mathbf{x},t) = \hat H \Psi(\mathbf{x},t)

\\[0.5in]

i \hbar \Psi(x) \frac{-iEt}{\hbar} \exp ^ {\frac{-iEt}{\hbar}}  = \hat H \Psi(x) \exp ^ {\frac{-iEt}{\hbar}}

\\[0.5in]

\hat H \Psi(x) = E \Psi(x)
$$

What we have now is time independent Schrodinger equation. We deal with this equation most of the time.

## What $ \hat H $ represents?

Here the Hamiltonian operator  $\hat H$ of a quantum system represents the total energy of that system. The Hamiltonian is a matrix and the eigenvalues of that matrix represent possible energy values that the system vcan take on.

## What are eigen values?

When you multiply a matrix with a vector, the vector rotates + scales. If there exists a vector whoch when multiplied to matrix would only cause the scaling effect but no rotation, that vector is the eigen vector. And corresponding scaling value is the eigen value.

Now that we know that Hamiltonian represents the energy of the system we can use this information to reach the ground state or the lowest energy of the system. 

## Why do we need the lowest energy values?

The lowest energy provides valuable information about the properties of the system which can further be utilised to understand the system, make predictions and exploit this information for further research.
