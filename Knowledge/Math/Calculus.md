
-------------------------
TODO: cheat sheet stuff....

e.g. 

Nabla, Cartesian
$$\nabla f =
\frac{\partial f}{\partial x}\hat{x} +
\frac{\partial f}{\partial y}\hat{y} +
\frac{\partial f}{\partial z}\hat{z}$$
$$\nabla \cdot \mathbf{f} =
\frac{\partial f_x}{\partial x} +
\frac{\partial f_y}{\partial y} +
\frac{\partial f_z}{\partial z}$$
$$\nabla \times \mathbf{f} = 
(\frac{\partial f_z}{\partial y} - \frac{\partial f_y}{\partial z})\hat{x} +
(\frac{\partial f_x}{\partial z} - \frac{\partial f_z}{\partial x})\hat{y} +
(\frac{\partial f_y}{\partial x} - \frac{\partial f_x}{\partial y})\hat{z} +
$$
$$\nabla \times \nabla \cdot \mathbf{f} = 0 \text{ ..... in }R^3$$
$$\nabla \cdot \nabla \equiv \nabla^2 $$
For closed surfaces:
$$\int \mathbf{A} \cdot d\mathbf{s} =
\int \int \nabla \times \mathbf{A} \cdot d\mathbf{a}$$
$$\int \int \int (\nabla \cdot \mathbf{A}) dV) =
\int \int (\mathbf{F} \cdot d\mathbf{S})$$


Combining:

chain rule: $$d(f \circ g)_a = df_{g(a)} \cdot dg_a$$
total derivative (.... can variables be dependent)

$$\frac{df(a, b, c)}{dx} =
\frac{\partial f}{\partial t} + 
\frac{\partial f}{\partial a} \frac{\partial a}{\partial x} +
\frac{\partial f}{\partial b} \frac{\partial b}{\partial x} +
\frac{\partial f}{\partial c} \frac{\partial c}{\partial x}
$$



---------------------------

The limit is the value of $f(x)$ as $x$ goes to $a$.  The limit is denoted by:
\begin{equation*}
  \lim_{x \to a} f(x)
\end{equation*}

The right handed limit gives the limit when x approaches a where $x > a$:
\begin{equation*}
  \lim_{x \to a^+} f(x)
\end{equation*}

The left handed limit gives the limit when x approaches a where $x < a$:
\begin{equation*}
  \lim_{x \to a^-} f(x)
\end{equation*}

For example when $f(x) = \frac{x}{|x|}$, $\lim_{x \to 0^-} f(x) = -1$ and $\lim_{x \to 0^+} f(x) = 1$.


\section{Derivative}

\subsection{Definition}
To calculate the rate of change of a function with respect to a variable, we use a derivative.  A derivative
for f(x) is as follows:
\begin{equation*}
  \frac{df}{dx} = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h}
\end{equation*}

\subsection{Rules}
% addition
\begin{equation*}
  \frac{d(f + g)}{dx} = \frac{df}{dx} + \frac{dg}{dx}
\end{equation*}
% multiplication
\begin{equation*}
  \frac{d}{dx}(f \times g) = \frac{df}{dt} \times g + \frac{dg}{dt} \times f
\end{equation*}
% chain rule
\begin{equation*}
  \frac{d}{dx}(f(g(x))) =(\frac{df}{dg})(\frac{dg}{dx})
\end{equation*}
% multiple derivative
\begin{equation*}
  \frac{d^n}{dx^n}f \equiv (\frac{d}{dx})^{n}f
\end{equation*}
%zeroth derivative
\begin{equation*}
  (\frac{d}{dx})^{0}f = f
\end{equation*}


\subsection{Common Derivatives}
\begin{align*}
  &\frac{d}{dx}c = 0					&&	\frac{d}{dx}x^n = nx^{n-1} 			\\[0.8ex]
  &\frac{d}{dx}sin(x) = cos(x)				&&	\frac{d}{dx}cos(x) = -sin(x)			\\[0.8ex]
  &\frac{d}{dx}tan(x) = sec^2(x) 			&&	\frac{d}{dx}cot(x) = -csc^2(x)			\\[0.8ex]
  &\frac{d}{dx}sec(x) = sec(x)tan(x)			&&	\frac{d}{dx}csc(x) = -csc(x)cot(x)		\\[0.8ex]
  &\frac{d}{dx}e^x = e^x				&&	\frac{d}{dx}a^x = a^x ln (a)			\\[0.8ex]
  &\frac{d}{dx}(ln(x)) = \frac{1}{x}			&&	\frac{d}{dx}log_{a}x = \frac{1}{xln(a)}		\\[0.8ex]
  &\frac{d}{dx}sin^{-1}(x) = \frac{1}{\sqrt{1-x^2}}	&&	\frac{d}{dx}cos^{-1}x = -\frac{1}{\sqrt{1-x^2}} \\[0.8ex] 
  &\frac{d}{dx}tan^{-1}(x) = \frac{1}{1 + x^2}		&&	\frac{d}{dx}cot^{-1}x = -\frac{1}{1 + x^2}	\\[0.8ex]
  &\frac{d}{dx}sec^{-1}(x) = \frac{1}{|x|\sqrt{x^2 - 1}}&&	\frac{d}{dx}csc^{-1}(x) = -\frac{1}{|x|\sqrt{x^2 - 1}}	
\end{align*}

\subsection{Applications}

\subsubsection{Rate of Change}
Derivatives gives us the rate of change of a property.  For example, if $f(t) = 10t$ is the distance covered by an object
and $t$ is the time then we can find the instantaneous speed of the object by:
\begin{equation*}
  \frac{d}{dt}(10t^2) = 20t
\end{equation*}

\subsubsection{Local Minimum and Local Maximumnnn}
The local minimum and local maximum of a function must occur at $x = b$ where $\frac{d}{dx}f(x=b) = 0$.  
If this were not so, one could either increase or decrease $x$ to increase or decrease $f(x)$ at this point.
The inverse is not true: $\frac{d}{dx}f(x=b) = 0$ does not imply $x=b$ is a local maximum or local minimum.
If $\frac{d^2}{dx^2}f(x=b) > 0$ then $x=b$ is the minimum.  If $\frac{d^2}{dx^n}f(x=b) < 0$ then $x=b$
is the maximum.

For example, the profits of a company are $p(u) = -u^2 + 60u -10$ where $u$ is the number of units sold.  
Since we have $\frac{d}{dx}p(u) = -2u + 60 = 0$, we know that $u=30$ is either a local maximum or local minimum.
We can plug $u=30$ into the equation to 

\subsubsection{L'Hospital's Rule}
If
\begin{equation*}
 lim_{x \to a}\frac{f(x)}{g(x)} = \frac{0}{0}\ \ \ OR\ \ \ lim_{x \to a}\frac{f(x)}{g(x)} = \frac{\pm \infty}{\pm \infty}
\end{equation*}
then
\begin{equation*}
 lim_{x \to a}\frac{f(x)}{g(x)} = lim_{x \to a} \frac{\frac{d}{dx}f(x)}{\frac{d}{dx}g(x)}
\end{equation*}

For example
\begin{equation*}
lim_{x \to 0}\frac{sin(x)}{x} = lim_{x \to 0}\frac{cos(x)}{1} = 1
\end{equation*}

\subsubsection{Approximating a Function}
If we know the value of a point $a$ and want to approximate $b$ using $f(x)$, then
\begin{equation*}
 f(b) \approx f(a) + \frac{d}{dx}(f(a))(b - a)
\end{equation*}

The value of $f(b)$ is usually better approximated with an increasing $n$ where
\begin{equation*}
 \sum_{j = 0}^{j = n} \frac{(b-a)^j}{j!} \frac{d^j}{dx^j}f(a)
\end{equation*}
As $n$ get sufficiently large, the difference between the approximation and the actual function approaches zero.

\section{Integrals}

\subsection{Definition}

For a continuous function, the area under a curve can be approximated by adding the area of many rectangles with 
heights of $f(x)$ and widths of $x$
\begin{equation*}
 Approximation\ for\ area\ under\ curve\ = \sum_{n}f(a + n * \Delta x) \Delta x
\end{equation*}

As $\Delta x$ approaches $0$, the difference between the approximation and real value for the area under the curve
approaches $0$ as well.  We thus define the integral as:
\begin{equation*}
 \int_{a}^{b}f(x)dx = \lim_{\Delta x \to 0} \left( \sum_{n=0}^{n=\frac{b-a}{\Delta x}-1}f(a + n * \Delta x) \Delta x \right)
\end{equation*}

$f(x)$ is the antiderivative of $\frac{df}{dx}$ 
\subsection{Fundamental Theorem of Calculus}
For $y=f(x)$
\begin{equation*}
 f(a) + \int_{a}^{b}\frac{dy}{dx}dx = f(a) + \sum_{x=a}^{x=b}\frac{dy}{dx}* dx = f(a) + \sum_{x=a}^{x=b}dy = f(b)
\end{equation*}

\subsection{Rules}
\begin{equation*}
 \int_{a}^{b} k f(x) dx = k \int_{a}^{b}f(x) dx
\end{equation*}

\begin{equation*}
 \int_{a}^{b} f(x) dx = -\int_{b}^{a} f(x) dx
\end{equation*}

\begin{equation*}
 \int_{a}^{b} f(x) + g(x) dx = \int_{a}^{b}f(x)dx + \int_{a}^{b}g(x)dx
\end{equation*}

\begin{equation*}
 f(x) + C = \int_{a}^{b} \frac{df}{dx} dx
\end{equation*}

\begin{equation*}
 \int f(g(x)) * \frac{dg}{dx} dx = \int f(u) du,\ \ \ where\ u=g(x)
\end{equation*}

\subsection{Applications}

\subsubsection{Area Between Curves}
The area between two curves, $f(x)$ and $g(x)$ is
\begin{equation*}
 \int f(x) - g(x) dx
\end{equation*}

For example, the area between $f(x) = x^2$ and $g(x) = 2x$ from $a=5$ to $b=10$ is
\begin{equation*}
 \int_{5}^{10} x^2 - 2x dx = \left[ \frac{x^3}{3} - {x^2} \right]^{10}_{5} = 
 \frac{1000}{3} - 100 - \frac{125}{3} + 25 = \frac{500}{3}
\end{equation*}

\subsubsection{Volume of Solid of Revolution}
A small section of volume $dV$ from rotation can be thought of as
$dV = \pi r^2dx$ where $r$ is the radius of a circle.  We can calculate
the area of a solid that is rotated around the x-axis through
\begin{equation*}
 Volume\ = \int \pi r^2 dx
\end{equation*} 
For example, the volume of a cone created by $f(x)= x$ rotated around the x-axis
from $x=0$ to $x=h$ is
\begin{equation*}
 \int_{0}^{h}\pi x^2 dx = h^3 \frac{\pi}{3}
\end{equation*}

\subsubsection{Average Value of Function}
The average value of $f(x)$ from $x=a$ to $x=b$ is given by 
\begin{equation*}
 \frac{1}{b-a}\int_{a}^{b}f(x)dx
\end{equation*}

\subsubsection{Length of a Curve}
The length of a curve can be found by adding up various segments $ds$ where
$ds = \sqrt{dx^2 + dy^2}$.  We can find the total length of a curve by
\begin{equation*}
 \int ds
\end{equation*}
For example, we can find the length of the segment given by
$x = \frac{2}{3}(y - 1)^{\frac{3}{2}}$ from $x=1$ to $x=9$.  The length is given by
\begin{equation*}
 \int_{x=1}^{x=9} ds = \int_{1}^{9}\sqrt{1 + \left( \frac{dx}{dy} \right)^2}dy
= \int_{1}^{9}\sqrt{1 + \left(\sqrt{y-1}\right)^2}dy = \int_{1}^{9}\sqrt{y}dy
= \left[ \frac{2}{3}y^{\frac{3}{2}}\right]^{9}_{1} = \frac{52}{3}
\end{equation*}

\subsubsection{Center of Mass in one dimension}
The center of mass is given by
\begin{equation*}
 \frac{\int_a^{b} xf(x)dx}{\int_a^{b}f(x)dx}
\end{equation*}

For example, the center of mass of a rod with density $f(x) = x$
from $x=0$ to $x=1$ is
\begin{equation*}
 \frac{\int_0^{1} x^2dx}{\int_0^{1}xdx} = \frac{\frac{1}{3}}{\frac{1}{2}} = \frac{2}{3}
\end{equation*}

\subsection{Integrating Multiple Times}
A function can be integrated more than one time.  One can use the following if something needs
integrated twice
\begin{equation*}
 \int_{a}^{b} \int_{a}^{t} f(t) dt dt
\end{equation*}

\section{Three Dimensions}
\subsection{Vectors}

% notation
\begin{equation*}
  \vec{r} = x\hat{x} + y\hat{y} + z\hat{z} = r_x\hat{x} + r_y\hat{y} + r_z\hat{z} = <x,y,z>
\end{equation*}

% addition
\begin{equation*}
  <x_1,y_1,z_1> + <x_2,y_2,z_2> = <x_1 + x_2, y_1 + y_2, z_1 + z_2>
\end{equation*}

% multiplication
\begin{equation*}
  c<x,y,z> = <cx, cy, cz>
\end{equation*}

% dot product
\begin{equation*}
  \vec{r} \cdot \vec{s} = \sum_{i=1}^3 r_i s_i = rs(cos\theta)
\end{equation*}

% euclidean norm
\begin{equation*}
  |\vec{r}| = \sqrt{\vec{r} \cdot \vec{r}} = r
\end{equation*}

\begin{equation*}
 \hat{r} = \frac{\vec{r}}{|\vec{r}|}
\end{equation*}

%cross product
\begin{equation*}
  \vec{r} \times \vec{s} = det 
  \begin{bmatrix}
    \hat{x} & \hat{y} & \hat{z} \\ 
    r_x & r_y & r_z \\ 
    s_x & s_y & s_z
  \end{bmatrix}
  = rs(sin\theta)\hat{n}
\end{equation*}



\subsection{Basic Calculus in Three Dimensions}
\begin{equation*}
 \frac{d\vec{r}}{dt} = <\frac{dx}{dt}, \frac{dy}{dt}, \frac{dz}{dt}>
\end{equation*}

\begin{equation*}
 \frac{d(c\vec{r})}{dt} = c\frac{d\vec{r}}{dt}
\end{equation*}

\begin{equation*}
 \frac{d}{dt}(\vec{r} + \vec{u}) = \frac{d\vec{r}}{dt} + \frac{d\vec{u}}{dt}
\end{equation*}

\begin{equation*}
 \frac{d}{dt}(\vec{r} \cdot \vec{u}) = \frac{d\vec{r}}{dt} \cdot \vec{u} + \vec{r} \cdot \frac{d\vec{u}}{dt}
\end{equation*}

\begin{equation*}
 \frac{d}{dt}(\vec{r} \times \vec{u}) = \frac{d\vec{r}}{dt} \times \vec{u} + \vec{r} \times \frac{d\vec{u}}{dt}
\end{equation*}

\begin{equation*}
 \int \vec{r} dt = <\int x dt, \int y dt, \int z dt>
\end{equation*}

\begin{equation*}
 ds = \sqrt{dx^2 + dy^2 + dz^2}  = 
 \left(\sqrt{\left(\frac{dx}{dt}\right)^2 + \left(\frac{dy}{dt}\right)^2 + \left(\frac{dz}{dt}\right)^2}\right) dt
\end{equation*}

\subsection{Properties of Three Dimensional Functions}
The tangent unit vector to $\vec{r}(t)$ is
\begin{equation*}
 \vec{T} = \frac{\frac{\vec{r}(t)}{dt}}{|\frac{\vec{r}(t)}{dt}|}
\end{equation*}

Since $|\vec{T}(t)| = c$ and $\frac{d (\vec{T}(t) \cdot \vec{T}(t))}{dt} = \frac{d}{dt}(c^2) = 0$, then 
$\frac{d (\vec{T}(t))}{dt} \cdot \vec{T} = 0$.  We define the normal vector as perpendicular
to the tangent vector.  The normal unit vector is defined as 
\begin{equation*}
 \vec{n} = \frac{\frac{\vec{T}(t)}{dt}}{|\frac{\vec{T}(t)}{dt}|}
\end{equation*}

The curvature, $K$, measures the amount the tangent unit vector changes.
It is given by the equation
\begin{equation*}
 K = \left|\frac{d\vec{T}}{ds}\right|
\end{equation*}

\subsection{Partial Derivative}
A partial derivative is a derivative of one variable while
all other variables are considered constant.  For example, if
$f(x,y,z) = xy + z$ then $\frac{\partial f}{\partial y} = x$

For $f(x(t),y(t),z(t))$, the chain rule can be given by 
\begin{equation*}
 \frac{df}{dt} = \frac{\partial f}{\partial x} \frac{dx}{dt} +
 \frac{\partial f}{\partial y} \frac{dy}{dt} + 
 \frac{\partial f}{\partial z} \frac{dz}{dt}
\end{equation*}

\subsection{Del Operator}
\subsubsection{Definition}
We define the del operator, $\nabla$, as
\begin{equation*}
 \nabla = \left< \frac{\partial}{\partial x},
 \frac{\partial}{\partial y},
 \frac{\partial}{\partial z}
 \right>
\end{equation*}


\subsubsection{Del Operator Applications}

We can use the del operator to find the gradient of a function $f$.
The gradient is a measure of how the function of $f$ is changing at each point.
The gradient is given by 
$$ \nabla f$$

The divergence of a function measure how much the vector field is
leaving a point.  The divergence is given as 
$$ \nabla \cdot \vec{v} $$

The curl of a functions measure how much the field curls around a point.
The curl is given by
$$ \nabla \times \vec{v} $$

\subsection{Useful theorems}
The fundamental theorem of line integrals is analagous to the 
fundamental theorem of calculus.  It is given by
\begin{equation*}
 \int_{b}^{a} \nabla f \cdot d\vec{r} = f(\vec{r}(b))- f(\vec{r}(a) 
\end{equation*}

If we integrate the curl of a vector function $\vec{f}$ in a plane $s$,
the result will be the same as integrating the vector function
in the direction of counterclockwise around the boundary, $c$.  if we
integrate the curl of a vector function over a plane, all
points would cancel except for those at the boundary. Stokes' Theorem
can be written as
\begin{equation*}
 \oint\limits_{c} \vec{f} \cdot d\vec{r} =
 \oiint\limits_{s} ((\nabla \times \vec{f}) \cdot d\vec{s}
\end{equation*}

If we have a solid,$E$, in three dimensions, the total divergence will
leave the surface of the solid, $s$.  Gauss's Theorem can be written as
\begin{equation*}
 \oiint\limits_{s} \vec{f} \cdot d\vec{s} =
 \iiint\limits_{E}\nabla\vec{f}dV
\end{equation*}

\subsection{Other Coordinate Systems}
cylindrical:
\begin{align*}
x&=rcos(\phi)   &  r&=\sqrt{x^2 + y^2}  \\
y&=rsin(\phi)   & \phi&=arctan(\frac{y}{x}) \\
z&		&	z&\\
\vec{r}&=x\hat{x} + y\hat{y} + z\hat{z}		&	\hat{r}&=\frac{\vec{r}}{|\vec{r}|} \\
&		&	\frac{d\hat{r}}{dt}&=\dot{\phi}\hat{\phi} \\
&		&	\frac{d\hat{\phi}}{dt}&=-\dot{\phi}\hat{r} \\
&		&	\vec{r}&= r\hat{r} + z\hat{z}
\end{align*}

% spherical
spherical:
\begin{align*}
&x = \rho sin(\phi)cos(\theta) & \rho = \sqrt{x^2 + y^2 + z^2}\\
&y = \rho sin(\phi)sin(\theta) \\
&z = \rho cos(\phi)
\end{align*}
