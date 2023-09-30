In this post, I summarize the approach used by Bell to show that quantum mechanics is incompatible with a theory of hidden variables. I use the following article: **On the Einstein Podolsky Rosen paradox, J. S. Bell, Physics Physique Fizika 1, 195 – Published 1 November 1964**

# The EPR argument

The main message of the article written by Einstein, Podolsky and Rosen (**Can Quantum-Mechanical Description of Physical Reality Be Considered Complete?**) can be summarized by the criterion they use to define a theory describing physical reality:

_If, without in any way disturbing a system, we can predict with certainty (i.e., with probability equal to unity) the value of a physical quantity, then there exists an element of physical reality corresponding to this physical quantity._ 

For instance, if one assumes the existence of some state $\psi$ such that it is an eigenstate of the operator $\hat{A}$ and for which the eigenvalue $a$ is associated with certainty: $\hat{A}\psi = a\psi$. Then, there is an element of physical theory associated to the physical quantity $\hat{A}$.

Moreover, in quantum mechanics, exists the possibility that two operators $\hat{A}$ and $\hat{B}$ do not commute. If one measures first $\hat{A}$, then it collapses the state and one can't measure $\hat{B}$ afterwards, and vice versa. From this observation, there are two conclusions: either the wavefunction is not complete, meaning it lacks predictive power and must be supplemented (completed) by a better wavefunction or the operators $\hat{A}$ and $\hat{B}$ can't exist in the same physical reality simulateneously.

To support their idea of quantum theory being incomplete, they give the example of two systems $S_{1}$ and $S_{2}$, allowed to interact in a certain time T, which are then leaved to evolve freely. 

Let's suppose the first system possesses eingenvalues $a_{1},a_{2}\dots$ for some physical quantity $\hat{A}$ and eigenfunctions $u_{1}(x_{1}),u_{2}(x_{2})\dots$, for $x_{1}$ the variable describing $S_{1}$. The wavefunction of the combined system $S_{1}+S_{2}$ after the interaction is then:

$$
\begin{equation}
\Psi(x_{1},x_{2}) = \sum_{n=1}^{\infty}c_{n}(x_{2})u_{n}(x_{1})
\end{equation}
$$

Where $x_{2}$ is the variable describing $S_{2}$ and $c_{n}(x_{2})$ the coefficients of the expansion. Therefore, if one measures the quantity $\hat{A}$ for the first system and finds $a_{j}$, the whole system will be in the final state $c_{j}(x_{2})u_{j}(x_{1})$. Similarly, if the different physical quantity $\hat{B}$ was chosen the state of the two systems is:

$$
\begin{equation}
\Psi(x_{1},x_{2}) = \sum_{m=1}^{\infty}d_{n}(x_{2})t_{n}(x_{1})
\end{equation}
$$

Since the two systems can't interact, if the first system is disturbed, then nothing will happen to the other one. However, we've just seen that the wavefunction is different for different operators. This means that both $c_{j}$ and $d_{j}$ exist in the same reality. If an experimenter decides to measure one or the other quantity for $S_{1}$ and finds a value, he can predict instantaneously the state of $S_{2}$, even though the two systems can't possibly exchange the measurement information (space-like separation for example).

The solution to this present as thought by Einstein and his colleagues (and presented in Bell's paper) is to postulate the existence of hidden variables in order to allow the _pre-determination_ of the results observed by the experimenter. These hidden variables are any parameters $\lambda$, continuous or discret. 

Bell take the example of two entangled particles that are each subjected to a magnetic field in some direction: $\vec{a}$ for the first particle and $\vec{b}$ for the second particle. The result of each measurement depend on the magnetic field direction and on a continuous variable lambda, distributed according to a probability density $\rho(\lambda)$ such as $A(\vec{a},\lambda) = \pm 1$ for the first particle and $B(\vec{b},\lambda)=\pm 1$ for the second particle.

What he aims to show is that the expectation value of obtained by considering hidden variables, is fundamentally different from the expection value predicted by standard quantum mechanics.


# Bell's proof

Let's write the expectation value of the product of the measurement results $\vec{\sigma_{1}}\cdot\vec{a}$ and $\vec{\sigma_{2}}\cdot\vec{b}$, with $\vec{\sigma_{i}}$ is the spin of the $i$-th particle:

$$
\begin{equation}
P(\vec{a},\vec{b}) = \int d\lambda\, \rho(\lambda)A(\vec{a},\lambda)B(\vec{b},\lambda)
\end{equation}
$$

First, we can see that in the case of the two particles' spin being entangled in the singlet state $\vert\psi\rangle=\frac{1}{\sqrt{2}}(\vert\uparrow\downarrow\rangle-\vert\downarrow\uparrow\rangle)$ and both magnetic fields in the same direction $\vec{a} = \vec{b}$, the results are opposed by sign and $P(\vec{a},\vec{b}) = -1$ (using $\int d\lambda\, \rho(\lambda)=1$). We can then let $A(\vec{a},\lambda) = -B(\vec{a},\lambda)$, which leads to:

$$
\begin{equation}
P(\vec{a},\vec{b}) = -\int d\lambda\, \rho(\lambda)A(\vec{a},\lambda)A(\vec{b},\lambda)
\end{equation}
$$

In quantum mechanics, however, the expectation value of the product of these two measurements is given by:

$$
\begin{equation}
\langle \vec{\sigma}_{1}\cdot\vec{a}\,\vec{\sigma}_{2}\cdot\vec{b}\rangle = -\vec{a}\cdot\vec{b}
\end{equation}
$$

We want to show that equations (3) and (5) cannot be strictly equal nor can they be made as close as possible.

We look at the average of the expectation values in order to avoid angles for which this approach might be inconclusive. We suppose first the difference between $\bar{P}(\vec{a},\vec{b})$ and $-\overline{\vec{a}\cdot\vec{b}}$ is very small, , for all $\vec{a}$ and $\vec{b}$:
<!---
We can also take the difference between the expectation values of $B$ measurement in different bases:

$$
\begin{equation}
\begin{split}
P(\vec{a},\vec{b})-P(\vec{a},\vec{c}) &= -\int d\lambda\, \rho(\lambda)\left[A(\vec{a},\lambda)A(\vec{b},\lambda)-A(\vec{a},\lambda)A(\vec{c},\lambda)\right]\\
&= -\int d\lambda\, \rho(\lambda)A(\vec{a},\lambda)A(\vec{b},\lambda)\left[A(\vec{b},\lambda)A(\vec{c},\lambda)-1\right]
\end{split}
\end{equation}
$$

The second line was found using $A(\vec{b},\lambda)A(\vec{b},\lambda) = +1$. Taking the absolute value and keeping in mind that $\vert A(\vec{a},\lambda)A(\vec{b},\lambda)\vert \le 1$, we get:

$$
\begin{equation}
\vert P(\vec{a},\vec{b})-P(\vec{a},\vec{c})\vert \le \int d\lambda\, \rho(\lambda)\left[1-A(\vec{b},\lambda)A(\vec{c},\lambda)\right] = 1-P(\vec{b},\vec{c})
\end{equation}
$$
--->


$$
\begin{equation}
\vert \bar{P}(\vec{a},\vec{b})+\overline{\vec{a}\cdot\vec{b}}\vert \le \epsilon
\end{equation}
$$

We'll see this inequality leads to a contradiction.
In the same spirit, we suppose that the difference between the averaged quantum expection value and the quantum expectation value is very small too, for all $\vec{a}$ and $\vec{b}$:

$$
\begin{equation}
\vert \overline{\vec{a}\cdot\vec{b}}-\vec{a}\cdot\vec{b}\vert \le \delta
\end{equation}
$$


Combining the two previous equations, we get:

$$
\begin{equation}
\vert \bar{P}(\vec{a},\vec{b})+\vec{a}\cdot\vec{b}\vert \le \epsilon+\delta
\end{equation}
$$

We define the left-hand side of this inequality such as:

$$
\begin{equation}
\bar{P}(\vec{a},\vec{b}) = \int d\lambda\, \rho(\lambda)\bar{A}(\vec{a},\lambda)\bar{B}(\vec{b},\lambda)
\end{equation}
$$

For $\vec{a} = \vec{b}$:

$$
\begin{equation}
\int d\lambda\, \rho(\lambda)\left[\bar{A}(\vec{a}=\vec{b},\lambda)\bar{B}(\vec{b},\lambda)+1\right]\le \epsilon+\delta
\end{equation}
$$

Then looking at the difference between the average expectation values of distinct B measurements:

$$
\begin{equation}
\begin{split}
\bar{P}(\vec{a},\vec{b})-\bar{P}(\vec{a},\vec{c}) &= \int d\lambda\, \rho(\lambda)\bar{A}(\vec{a},\lambda)\bar{B}(\vec{b},\lambda)\left[1+\bar{A}(\vec{b},\lambda)\bar{B}(\vec{c},\lambda)\right]\\
&-\int d\lambda\, \rho(\lambda)\bar{A}(\vec{a},\lambda)\bar{B}(\vec{c},\lambda)\left[1+\bar{A}(\vec{b},\lambda)\bar{B}(\vec{b},\lambda)\right]
\end{split}
\end{equation}
$$

Thus taking the absolute value and using again the fact that $\vert \bar{A}(\vec{a},\lambda)\vert\le 1$ and $\vert \bar{B}(\vec{a},\lambda)\vert\le 1$ and a simple triangle inequality:

$$
\begin{equation}
\begin{split}
\vert \bar{P}(\vec{a},\vec{b})-\bar{P}(\vec{a},\vec{c})\vert&\le \int d\lambda\, \rho(\lambda)\left[1+\bar{A}(\vec{b},\lambda)\bar{B}(\vec{c},\lambda)\right]+\int d\lambda\, \rho(\lambda)\left[1+\bar{A}(\vec{b},\lambda)\bar{B}(\vec{b},\lambda)\right]\\
&\le 1+\bar{P}(\vec{b},\vec{c})+\epsilon+\delta
\end{split}
\end{equation}
$$

Also, we know that $\bar{P}(\vec{b},\vec{c})\le \epsilon+\delta-\vec{b}\cdot\vec{c}$ and:

$$
\begin{equation}
\vert \bar{P}(\vec{a},\vec{b})-\bar{P}(\vec{a},\vec{c})\vert\ge\vert\vec{a}\cdot\vec{c}-(\epsilon+\delta)+\bar{P}(\vec{a},\vec{b})\vert\ge\vert\vec{a}\cdot\vec{c}-\vec{a}\cdot\vec{b}-2(\epsilon+\delta)\vert
\end{equation}
$$

It gives finally, by combining both sides:
$$
\begin{equation}
4(\epsilon+\delta)\ge \vert\vec{a}\cdot\vec{c}-\vec{a}\cdot\vec{b}\vert+\vec{b}\cdot\vec{c}-1
\end{equation}
$$

Suppose that we choose as measurement basis $\vec{a}\cdot\vec{c}=0$ and $\vec{a}\cdot\vec{b}=\vec{b}\cdot\vec{c}=1/\sqrt{2}$, which we use in the previous equation to get:

$$
\begin{equation}
4(\epsilon+\delta)\ge \sqrt{2}-1\Rightarrow\epsilon\ge\frac{\sqrt{2}-1}{4}-\delta
\end{equation}
$$

Since by definition $\delta$ is arbitrary small, we see that $\epsilon$ is bounded from below by $0.10$. We got a contradiction and therefore the inequality (6) is not true. The hidden variable theory doesn't predict the same values as the standard quantum theory.