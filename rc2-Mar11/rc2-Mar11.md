# VE401 Probabilistic Methods in Eng. 

## RC#2 Discrete Distributions & Continuous Random Variables

>  By TA: DONG Juechu, Mar. 2021

### Discrete Distributions

#### ==$$X \sim \text{Bernoulli} (p)$$==

$$
X: S \rightarrow\{0,1\} \subset \mathbb{R}
$$
$$
f_{X}:\{0,1\} \rightarrow \mathbb{R}, \quad f_{X}(x)=\left\{\begin{array}{ll}
1-p & \text { for } x=0 \\
p & \text { for } x=1
\end{array}\right. \qquad( 0 < p <1)
$$
Then $X$ is said to be a **==Bernoulli random variable==** or follow a Bernoulli distribution with parameter $p$. 

#### ==Binomial Distribution== ==$$X \sim B(n, p)$$==

Getting x success in n Bernoulli trails:
$$
X: S \rightarrow \Omega=\{0, \ldots, n\} \subset \mathbb{R}\qquad (n \in \mathbb{N} \backslash\{0\})
$$
$$
f_{X}: \Omega \rightarrow \mathbb{R}, \quad \quad f_{X}(x)=\left(\begin{array}{l}
n \\
x
\end{array}\right) p^{x}(1-p)^{n-x} \qquad (0<p<1)
$$
Then $X$ is said to be a **binomial random variable with parameters $n$ and $p$.** 

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/75/Binomial_distribution_pmf.svg/1280px-Binomial_distribution_pmf.svg.png" alt="Binomial Dis" style="zoom: 33%;" />

#### ==Geometric Distribution==  ==$X \sim \operatorname{Geom}(p)$.==

Getting the first success on the xth Bernoulli trail:

Let $S$ be a sample space and
$$
X: S \rightarrow \Omega=\mathbb{N} \backslash\{0\}
$$
Let $0<p<1$ and define the density function $f_{X}: \mathbb{N} \backslash\{0\} \rightarrow \mathbb{R}$ given by
$$
f_{X}(x)=(1-p)^{x-1} p .
$$
We say that $X$ is a **geometric random variable with parameter $p$.**

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4b/Geometric_pmf.svg/1920px-Geometric_pmf.svg.png" alt="geo distribution" style="zoom: 33%;" />

- <u>moment generating function</u> : $$q = 1-p$$
	$$
	m_{X}:(-\infty,-\ln q) \rightarrow \mathbb{R},\qquad m_{X}(t)=\frac{p e^{t}}{1-q e^{t}} \\
	$$

- <u>Expectation & Variance</u> 
	$$
	E[X] = \frac{1}{p}\qquad Var[X]=\frac{q}{p^2}
	$$

#### ==Pascal Distribution==

obtain the rth success at xth trail:
$$
\begin{aligned}
X: S \rightarrow \Omega &=\mathbb{N} \backslash\{0,1, \ldots, r-1\} \\
&=\{r, r+1, r+2, \ldots\}
\end{aligned} \qquad (r \in \mathbb{N} \backslash\{0\})
$$
$$
f_{X}: \Omega \rightarrow \mathbb{R}, \qquad
f_{X}(x)=\left(\begin{array}{l}
x-1 \\
r-1
\end{array}\right) p^{r}(1-p)^{x-r}, \quad 0<p<1
$$
is said to follow a **Pascal distribution with parameters $p$ and $r$.**

- <u>M.G.F.</u>
	$$
	m_{X}:(-\infty,-\ln q) \rightarrow \mathbb{R}, \quad m_{X}(t)=\frac{\left(p e^{t}\right)^{r}}{\left(1-q e^{t}\right)^{r}}, \quad q=1-p
	$$
	
- <u>Expectation & Variance</u> 
	$$
	E[x] = \frac{r}{p} \qquad Var[X] = \frac{rq}{p^2}
	$$

- $$
	
	$$

	

#### ==Negative binomial distribution==

Experience x failures before the r success:
$$
\begin{aligned}
X: S \rightarrow \Omega &=\mathbb{N}
\end{aligned}, \qquad r \in \mathbb{N} \backslash\{0\}
$$

$$
f_{X}: \Omega \rightarrow \mathbb{R}, \qquad
f_{X}(x)=\binom{x+r-1}{r-1} p^{r}(1-p)^x, \quad 0<p<1
$$

is said to follow a **Pascal distribution with parameters $p$ and $r$**.

<img src="https://upload.wikimedia.org/wikipedia/commons/8/83/Negbinomial.gif" alt="Neg Bino Dis" style="zoom:150%;" />

> Show that the sum of two independent and identical geometric random variables follows a Pascal distri-
> bution with r = 2.

#### ==Poison distribution==

arrival in a continuous time interval:

Assumptions

1. Independence: If the intervals T1, T2 doesn't overlap (except perhaps at one point), then the numbers of arrivals in these interval are independent of each other.

2. Constant rate of arrivals

	Let $$k = \lambda t, \lambda\text{ arriving rate}, t\text{ time interval}$$

$$
f_{X}(x)=\frac{k^{x} e^{-k}}{x !}
$$
is said to have a **Poisson distribution with parameter $k$.**

-  <u>M.G.F.</u>

$$
m_{X}: \mathbb{R} \rightarrow \mathbb{R}, \quad m_{X}(t)=e^{k\left(e^{t}-1\right)}
$$
-  <u>Expectation & Var</u>
	$$
	\mathrm{E}[X]=k\qquad \operatorname{Var}[X]=k
	$$

- <u>cumulative distribution function</u>

$$
F(x)=P[X \leq x]=\sum_{y=0}^{\lfloor x\rfloor} \frac{e^{-k} k^{y}}{y !}
$$
> #### Poisson Approximation to the Binomial Distribution
>
> Consider the density $f$ of the binomial distribution,
> $$
> f(x)=\left(\begin{array}{l}
> n \\
> x
> \end{array}\right) p^{x}(1-p)^{n-x}
> $$
> Let $k$ be fixed so that $n p=k$ and set $p=k / n$. Replace $p$ by $k / n$ everywhere in $(*)$ and then let $n \rightarrow \infty$. Use Stirling's formula $^{1}$ to show that for every $x, f(x) \rightarrow\left(k^{x} / x !\right) e^{-k},$ the density of the Poisson distribution with parameter $k$.
>
> ${ }^{1}$ Stirling's formula states that
> $$
> n ! \sim \sqrt{2 \pi n}\left(\frac{n}{e}\right)^{n} \quad \text { as } n \rightarrow \infty
> $$
> where $f(n) \sim g(n)$ as $n \rightarrow \infty$ means that $\lim _{n \rightarrow \infty} \frac{f(n)}{g(n)}=1$



### Continuous Random Variable

Let $S$ be a sample space. A continuous random variable is a map $X: S \rightarrow \mathbb{R}$ together with a function $f_{X}: \mathbb{R} \rightarrow \mathbb{R}$ with the properties that

(i) $f_{X}(x) \geq 0$ for all $x \in \mathbb{R}$ and

(ii)$$\int_{-\infty}^{\infty} f_{X}(x) d x=1 \text { . }$$

The integral of $f_{X}$ is interpreted as the probability that $X$ assumes values $x$ in a given range, i.e.,
$$
P[a \leq X \leq b]=\int_{a}^{b} f_{X}(x) d x
$$
The function $f_{X}$ is called the **==probability density function==** (or just density) of the random variable $X$.
$$
F_{X}(x):=P[X \leq x]=\int_{-\infty}^{x} f_{X}(y) d y
$$
$$F_X$$ is called the **==cumulative distribution function==**. We can obtain the density $f_{X}$ from $F_{X}$ :$$f_{X}(x)=F_{X}^{\prime}(x)$$
$$
\begin{array}{l}

\mathrm{E}[X]:=\int_{\mathbb{R}} x \cdot f_{X}(x) d x \\
\mathrm{E}[\varphi \circ X]=\int_{-\infty}^{\infty} \varphi(x) \cdot f_{X}(x) d x \\
\operatorname{Var}[X]:=\mathrm{E}\left[(X-\mathrm{E}[X])^{2}\right]=\mathrm{E}\left[X^{2}\right]-\mathrm{E}[X]^{2} \\
m_{X}(t)=E\left[e^{t X}\right]=\int_{-\infty}^{\infty} e^{t x} f_{X}(x) d x
\end{array}
$$

- **==median $M_{X}$:==** defined by $P\left[X \leq M_{X}\right]=0.5 .$ aka the time where half of the components will have failed
- **==mean E[X].==**
- **==mode $x_{0},$==**: the location of the maximum of $f_{X}$ (if there is a unique maximum location).aka. the time with the greatest failure density, i.e., the time around which failure is most likely. For the exponential distribution, $x_0=0$

#### Transformation of random variables

1.3.13. Theorem. Let $X$ be a continuous random variable with density $f_{X}$. Let $Y=\varphi \circ X,$ where ==$\varphi: \mathbb{R} \rightarrow \mathbb{R}$ is strictly monotonic and differentiable.== The density for $Y$ is then given by
$$
f_{Y}(y)=f_{X}\left(\varphi^{-1}(y)\right) \cdot\left|\frac{d \varphi^{-1}(y)}{d y}\right| \quad \text { for } y \in \operatorname{ran} \varphi
$$
and
$$
f_{Y}(y)=0 \qquad \text { for } y \notin \operatorname{ran} \varphi \text { . }
$$
#### ==Exponential Distribution==

The probability of x arrivals in the time interval [0,t] 

Time of the first arrival (continuous random variable) T

$F_T(t)$ the cumulative distribution on the density of T

$f_T(t) = \frac{d}{dt}F_T(t) = \lambda e^{-\lambda t}$ (exponential distribution with $\beta = \lambda$)
$$
f_{\beta}(x)=\left\{\begin{array}{ll}
\beta e^{-\beta x}, & x>0 \\
0, & x \leq 0
\end{array}\right.\\
E[X] = \frac{1}{\beta}\qquad Var[X] = \frac{1}{\beta^1} \qquad m_X(t) = \frac{\beta}{\beta-t}
$$
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/02/Exponential_probability_density.svg/1024px-Exponential_probability_density.svg.png" alt="expo dis" style="zoom: 33%;" />

#### ==Gamma/Chi Square Distribution==

The time of r arrivals

$F_{Tj}(t) = \lambda e^{-\lambda t}\frac{(\lambda t)^{j-1}}{(j-1)!}$

Let $\alpha, \beta \in \mathbb{R}, \alpha, \beta>0$. A continuous random variable $\left(X, f_{\alpha, \beta}\right)$ with density
$$
\begin{array}{l}
f_{\alpha, \beta}(x)=\left\{\begin{array}{ll}
\frac{1}{\Gamma(\alpha) \beta^{\alpha}} x^{\alpha-1} e^{-x / \beta}, & x>0 \\
0, & x \leq 0,
\end{array}\right.
\end{array}
$$
is said to follow an **gamma distribution with parameters $\alpha$ and $\beta$.**
Here
$$
\Gamma(\alpha)=\int_{0}^{\infty} z^{\alpha-1} e^{-z} d z, \quad \alpha>0
$$
is the Euler gamma function. $(n !=\Gamma(n+1))$

![Euler gamma](https://upload.wikimedia.org/wikipedia/commons/thumb/5/52/Gamma_plot.svg/488px-Gamma_plot.svg.png)

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e6/Gamma_distribution_pdf.svg/1280px-Gamma_distribution_pdf.svg.png" alt="gamma dis" style="zoom: 33%;" />

- $$E[X] = \alpha\beta \qquad Var X = \alpha \beta^2$$

- M.G.F

	$$m_{X}:(-\infty, 1 / \beta) \rightarrow \mathbb{R}, \quad m_{X}(t)=(1-\beta t)^{-\alpha}$$

Let $\gamma \in \mathbb{N}$. A continuous random variable $\left(\chi_{\gamma}^{2}, f_{X}\right)$ with density
$$
f_{\gamma}(x)=\left\{\begin{array}{ll}
\frac{1}{\Gamma(\gamma / 2) 2^{\alpha}} x^{\gamma / 2-1} e^{-x / 2}, & x>0 \\
0, & x \leq 0
\end{array}\right.
$$
is said to follow a **==chi-squared distribution with $\gamma$ degrees of freedom==**.
chi-squared distribution is simply that of a ==gamma random variable with $\beta=2$ and $\alpha=\gamma / 2$.== 
$$
E\left[\chi_{\gamma}^{2}\right]=\gamma, \quad \operatorname{Var}\left[\chi_{\gamma}^{2}\right]=2 \gamma
$$

> #### Stock Control Problems
>
> https://www.jstor.org/stable/3007410?seq=7#metadata_info_tab_contents
>
> In order to ensure a high standard of serviceability without incurring unnecessary aircraft delay, an airline
> adopts the following replacement policy for its repairable aircraft components:
>
> 1. An unserviceable component is removed from an aircraft and sent for inspection to repair.
> 2. An immediate demand for a serviceable replacement is made to the stores. If available, the replacement
> 	is at once fitted to the aircraft.
> 3. When the previously unserviceable component has been repaired to be serviceable, it is placed in the
> 	stores.
>
> Suppose that the components are delivered serviceable to stores in the same order as they are removed
> from aircraft. We denote that
>
> - "Demand": a component for repair.
>
> - "Lead time" with parameter k: the time interval between the removal of the component and its
> 	entry into stores, i.e., the time interval for the store to deliver an order of k specified components.
>
> What is the probability $p_{rk}$ of exactly r demands during the lead time when the parameter value is
> k?

