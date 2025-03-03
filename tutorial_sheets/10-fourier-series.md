<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
    tex2jax: {
      inlineMath: [ ['$','$'], ["\\(","\\)"] ],
      processEscapes: true
    }
  });
</script>

<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-MML-AM_CHTML">
</script>
<script src="https://www.desmos.com/api/v1.5/calculator.js?apiKey=dcb31709b452b1cf9dc26972add0fda6"></script>
<script type="text/javascript" src="tutorialSheetScripts.js"> </script>
<script type="text/javascript" src="tutorialSheetGraphs.js"> </script>
<link rel="stylesheet" type="text/css" media="all" href="styles.css">

# Fourier series, Tutorial sheet 10

### Additional resources
* [SJC - Fourier Series](https://youtu.be/rbRwhrNQnH0)
* [An Interactive Introduction to Fourier Transforms - Jez Swanson](http://www.jezzamon.com/fourier/index.html)
* [But what is the Fourier Transform? A visual introduction.](https://youtu.be/spUNpyF58BY)
* [What is up with Noises? (The Science and Mathematics of Sound, Frequency, and Pitch) - Vihart](https://youtu.be/i_0DXxNeaQ0)
* [JPEG 'files' & Colour (JPEG Pt1) - Computerphile](https://youtu.be/n_uNPbdenRs)

<br><br><br><br>

# Problem sheet
## Essential Questions
### Problem 1.
State the time period and formula of the following periodic functions.

(a)
<!-- Calculator using the desmos API woooo -->
<div id="prob1a" style="width: 600px; height: 300px;"></div>
<script>
    latex = "x-2\\pi\\operatorname{floor}\\left(\\frac{x}{2\\pi}+0.5\\right)"
    makeSimpleGraph("prob1a", latex, piOptions);
</script>

<div class = "answer">
$\boxed{\text{Period} =2\pi \qquad f(x)=x, \space \text{for} -\pi < x < \pi}$
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br></div>

(b)
<div id="prob1b" style="width: 600px; height: 300px;"></div>
<script>
    latex = "\\frac{\\pi}{2}\\left(\\left(2\\operatorname{floor}\\left(\\frac{x}{2\\pi}\\right)-\\frac{x}{\\pi}+1\\right)+\\operatorname{abs}\\left(2\\operatorname{floor}\\left(\\frac{x}{2\\pi}\\right)-\\frac{x}{\\pi}+1\\right)\\right)"
    makeSimpleGraph("prob1b", latex, piOptions);
</script>

<div class = "answer">
$\boxed{\text{Period} =2\pi \quad f(x)=\left\{
\begin{array}{ll}
\pi-x, &\quad 0 < x < \pi{} \\
0, &\quad \pi{} < x < 2\pi
\end{array}\right.
}$
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br></div>

(c)
<div id="prob1c" style="width: 600px; height: 300px;"></div>
<script>
    latex = "\\left(x-2\\pi\\operatorname{floor}\\left(\\frac{x}{2\\pi}+0.5\\right)\\right)^{2}"
    calc = makeSimpleGraph("prob1c", latex, piOptions);
    calc.setMathBounds({
        left: -9,
        right: 9,
        bottom: -1,
        top: 10,
    })
</script>

<div class = "answer">
$\boxed{\text{Period} = 2\pi \qquad f(x)=x^2, \text{ for } -\pi < x < \pi}$
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br></div>

-----------------------------------------------------------------------------------

### Problem 2.
Sketch the following periodic functions, stating their period:

(a) $f(x) = 3\sin\left(\frac{x}{2}\right)$, over the interval $-\pi < x < 2\pi$ for $-4\pi < x < 4\pi.$

<div class = "answer">
$\Rightarrow{} \text{Period} = 3\pi$

<div id="prob2a" style="width: 600px; height: 300px;"></div>
<script>
    latex = "3\\sin\\left(\\frac{\\left(x-3\\pi\\operatorname{floor}\\left(\\frac{x}{3\\pi}+\\frac{1}{3}\\right)\\right)}{2}\\right)"
    calc = makeSimpleGraph("prob2a", latex, piOptions);
    calc.setExpression({ 
        id: 'graph2', 
        latex: "x=-4\\pi"
    });
    calc.setExpression({ 
        id: 'graph3', 
        latex: 'x=4\\pi'
    });
</script>

</div>

<div class = "workingout"><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br></div>

(b) 
$f(t) = \left\\{ 
\begin{array}{ll}
-t &\quad -\pi < t < 0 \newline
t &\quad 0 < t < \pi \end{array}\right.$
for  $-3\pi< t < 3\pi$

<div class = "answer">
$\Rightarrow{} \text{Period} = 2\pi$

<div id="prob2b" style="width: 600px; height: 300px;"></div>
<script>
    latex = "\\operatorname{abs}\\left(x-2\\pi\\operatorname{floor}\\left(\\frac{x}{2\\pi}+\\frac{1}{2}\\right)\\right)"
    calc = makeSimpleGraph("prob2b", latex, piOptions);
    calc.setExpression({ 
        id: 'graph2', 
        latex: "x=-3\\pi"
    });
    calc.setExpression({ 
        id: 'graph3', 
        latex: 'x=3\\pi'
    });
</script>

</div>

<div class = "workingout"><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br></div>

(c) $f\left(p\right)=\left\\{\begin{array}{l}\frac{p^2}{2}\ \ \ \ \ 0 < p <4 \newline
    8\ \ \ \ \ \ 4 < p < 6 \newline
    0\ \ \ \ \ \ 6 < p < 8 \end{array}\right.
    $
    for $-16<p<16$
 
<div class = "answer">
$\Rightarrow{} \text{Period} = 8$

<div id="prob2c" style="width: 600px; height: 300px;"></div> 
<script>
    latex = "\\min\\left(\\max\\left(\\frac{\\operatorname{sign}\\left(\\left(x-8\\operatorname{floor}\\left(\\frac{x}{8}+\\frac{1}{4}\\right)\\right)\\right)\\left(x-8\\operatorname{floor}\\left(\\frac{x}{8}+\\frac{1}{4}\\right)\\right)^{2}}{2},0\\right),8\\right)";
    calc = makeSimpleGraph("prob2c", latex, defaultGraphOptions);
    calc.setMathBounds({
        left: -16,
        right: 16,
        bottom: -1,
        top: 9,
    })
    calc.setExpression({ 
        id: 'graph2', 
        latex: "x=-16"
    });
    calc.setExpression({ 
        id: 'graph3', 
        latex: 'x=16'
    });
</script>
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br></div>

(d) $f\left(q\right)=2q-q^2\ \ \ \ \ 0< q < 2$, for $-8 < q < 8$
 
<div class = "answer">
$\Rightarrow{} \text{Period} = 2$

<div id="prob2d" style="width: 600px; height: 300px;"></div> 
<script>
    latex = "2\\left(x-2\\operatorname{floor}\\left(\\frac{x}{2}\\right)\\right)-\\left(x-2\\operatorname{floor}\\left(\\frac{x}{2}\\right)\\right)^{2}";
    calc = makeSimpleGraph("prob2d", latex, defaultGraphOptions);
    calc.setMathBounds({
        left: -8,
        right: 8,
        bottom: -1,
        top: 2,
    })
    calc.setExpression({ 
        id: 'graph2', 
        latex: "x=-8"
    });
    calc.setExpression({ 
        id: 'graph3', 
        latex: 'x=8'
    });
</script>
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br></div>

------------------------------------

### Problem 3.
State whether the following functions are periodic, and if so, find their period:

(a) $\cos(x) + \sin(2x)$
<div class = "answer">
Periodic: Summing two periodic functions results in a function that is still periodic.
The period of $\text{cos}(x) = 2\pi$ and $\text{sin}(2x) = \pi$. The lowest common multiple of $\pi$ and $2\pi$ is equal to the period of $\text{cos}(x) + \text{sin}(2x)$.

$\Rightarrow{} \boxed{ \text{Period } =2\pi}$
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br></div>

(b) $\sin{\left(x\right)}\cos{\left(x\right)}$

<div class = "answer">
Periodic: Multiplying two periodic functions results in a function that is still periodic.
Using the trigonometric identity 
$\text{sin}(a)\text{cos}(b) = \frac{1}{2}(\text{sin}(a + b) + \text{sin}(a - b))$ ,
$\text{sin}(x)\text{cos}(x)$ can be rewritten as $\frac{1}{2}\text{sin}(2x)$ which has a period of $\pi$.

$\Rightarrow{} \boxed{ \text{Period } = \pi}$
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br></div>

(c) $e^x\sin^2(x)$

<div class = "answer">
Not periodic: Multiplying a periodic function, $\text{sin}^2(x)$, with a non periodic function, $e^x$, results in a non periodic function. If you're struggling to show that $\text{sin}^2(x)$ is periodic, try writing it in terms of functions of $2x$.

$\Rightarrow{} \boxed{ \text{Not periodic }}$
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br></div>

------------------------------------

### Problem 4.
Determine if the function $f(x)$ is odd, even, or neither.

(a) $f\left(x\right)=\ x^2\sin{(2x)}$
<div class = "answer"> Break the function up: $x^3$ is an even function and $\text{sin}(2x)$ is an odd function. An even function multiplied by an odd function results in an odd function.
$\\ \Rightarrow \boxed{\text{Odd function}}$
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br></div>

(b) $f\left(x\right)=3\sin{\left(x\right)}\cos{\left(4x\right)}$
<div class = "answer">Break the function up: $3$ is an even function, $\text{sin}(x)$ is an odd function and $\text{cos}(4x)$ is an even function. An even function multiplied by an odd function, multiplied by an even function results in an odd function.
$\\ \Rightarrow \boxed{\text{Odd function}}$
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br></div>

(c) $f\left(x\right)=x^3e^3$
<div class = "answer">Break the function up: $x^3$ is an odd function and $e^3$ is an even function. An odd function multiplied by an even function results in an odd function.
$\\ \Rightarrow \boxed{\text{Odd function}}$
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br></div>

(d)
![class-c](10-fourier-series/even-odd-d.PNG)
<div class = "answer">
$\Rightarrow \boxed{\text{Odd function}}$
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br></div>

(e)
![class-c](10-fourier-series/even-odd-e.PNG)
<div class = "answer">
$\Rightarrow \boxed{\text{Even function}}$
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br></div>

(f)
![class-c](10-fourier-series/even-odd-f.PNG)
<div class = "answer">
$\Rightarrow \boxed{\text{Odd function}}$
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br></div>

------------------------------------

### Problem 5.
For the following functions
(I) Find the Fourier coefficients and series in general terms,
(II) Plot the function and the given partial sum over the given interval.

(a) $f\left(x\right)=x^3,\ \ \ \text{for}\ \left[ -1,1\right] \ $ with n = 5

<div class = "answer">
The first step is to work out whether the function $f\left(x\right)=x^3$ is odd, even, or neither. This can be done by eye for a simple function like $x^3$. To check, or for harder functions,  you could graph it on Desmos to have a visual representation of the function, or use the formulae found in the notes:

$$
f_{\textrm{even}}(x)=\frac{f(x)+f(-x))}{2} \qquad \qquad
f_{\textrm{odd}}(x)=\frac{f(x)-f(-x))}{2}
$$

The function $f\left(x\right)=x^3$ is odd, so the Fourier series representation will only contain sine terms and all $a_n = 0$.

<br>

The sine coefficients can be found using:

$$
b_n = \frac{1}{L} \int_{-L}^{L}f(x)\sin\left(\frac{n\pi x}{L}\right) dx
$$


where $L=1$ and $f(x) = x^3.$ Plugging these values in, we get:

$$
b_n = \int_{-1}^{1}x^3\sin\left(n\pi x\right) dx.
$$

This can be integrated quickly using WolframAlpha by typing in: 

<br>

"integrate x^3 sin(n pi x) between -1 and 1" 

<a href="https://www.wolframalpha.com/input/?i=integrate+x%5E3+sin%28n*pi*x%29+between+-1+and+1">WolframAlpha</a>

<br>

This results in: 

\begin{align*}
b_n  &= \frac{6(\pi^2n^2 - 2)\sin(\pi n) - 2\pi n (\pi^2 n^2 - 6) \cos(\pi n)}{\pi^4 n^4} \newline &=  (-1)^n 
\frac{- 2\pi n (\pi^2 n^2 - 6)}{\pi^4 n^4} \newline
&= (-1)^n \frac{2(6 - \pi^2 n^2)}{\pi^3 n^3} \text{ when } n \in \mathbb{Z} \text{ (when n is an integer.)}
\end{align*}

Note: the function simplification can be found by examining the values of $\sin(\pi n)$ and $\cos(\pi n)$ when $n$ is an integer. For any value of $n$, $\sin(\pi n) = 0$, and $\cos(\pi n) = (-1)^n$.


<br><br>

To integrate manually, use integration by parts: $\int f dg=fg-\int g df.$

\begin{align*}
f = x^3 \quad \quad
df = 3x^2 dx \quad \quad
dg = \sin(n \pi x) dx \quad \quad
g = -\frac{\cos(\pi n x)}{\pi n}
\end{align*}

$$
= \left. \left(-\frac{x^3 \cos(\pi n x)}{\pi n} \right) \right\vert^1_{-1} + \frac{3}{\pi n} \int^1_{-1}x^2 \cos(\pi n x) dx
$$ 

Repeating twice more to bring $x^2$ down to $1$ and then integrating the remaining expression, results in:

$$
= -\frac{12 \sin(\pi n)}{\pi^4 n^4} + \frac{12 \cos(\pi n)}{ \pi^3 n^3} + \frac{6 \sin(\pi n)}{\pi^2 n^2} - \frac{2 \cos(\pi n)}{\pi n} 
$$

$$
= \frac{12 (-1)^n}{ \pi^3 n^3} - \frac{2 (-1)^n}{\pi n} 
$$

$$
= \frac{12 (-1)^n - 2 n^2 \pi^2 (-1)^n}{ \pi^3 n^3} 
$$

$$
= (-1)^n \frac{2(6 - \pi^2 n^2)}{\pi^3 n^3}
$$

Note: doing fourier expansions manually can get very long and complicated, in this example you would have to integrate by parts three times! But you won't get tested on this in an exam, as you can just (and are encouraged to) use WolframAlpha to solve it.

<br><br>
$\therefore$ the Fourier series representation is:

$$ \boxed{
f\left(x\right)=\sum_{n=1}^{\infty{}}{(-1)}^n\frac{2(6-n^2{\pi{}}^2)}{n^3{\pi{}}^3}\
\sin{(n\pi{}x)}
}$$
<iframe src="https://www.desmos.com/calculator/vxqjspzae0" width="850px" height="500px" style="border: 1px solid #ccc" frameborder=0></iframe>

<br>

(Try moving the slider under N)

</div>

<div class = "workingout"><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br></div>

(b) $f\left(x\right)=\left \\{\begin{array}{l}1+x,\ \ \ \ \ \text{for}\ -1\leq{}x\leq{}0 \newline
1,\ \ \ \ \ \ \ \ \ \ \text{for}\ \ 0 < x\leq{}1\end{array} \right. $
with n = 2

<div class = "answer">
This function has both odd and even parts, so both $a_n$ and $b_n$ must be found.

<br>

(1) First find $a_0$ by subbing in $n = 0$:

\begin{align*}
a_0=\frac{1}{L}\int_{-L}^Lf(x)\
dx=\int_{-1}^0(1+x)dx+\int_0^1dx=\
\left.\left(x+\frac{1}{2}x^2\right)\right\vert_{-1}^{0}+1 = \frac{1}{2} + 1 = \frac{3}{2}
\end{align*}

$$ \therefore \boxed{\frac{a_0}{2} = \frac{\frac{3}{2}}{2} = \frac{3}{4}} $$

(2) Then looking at the $a_n$ coefficient:

\begin{align*}
a_n&=\frac{1}{L} \int_{-L}^{L}f(x)\cos\left(\frac{n\pi x}{L}\right) dx
&=\int_{-1}^{0}(x+1)\cos\left(n\pi x\right) dx + \int_{0}^{1}\cos\left(n\pi x\right) dx
\end{align*}

The second integral is straight forward:

$$
\int_{0}^{1}\cos\left(n\pi x\right) dx = \left. \frac{1}{n\pi{}}\sin{\left(n\pi{}x\right)} \right\vert_{0}^1=\frac{1}{n\pi{}}\left(0-0\right)=0
$$

The first integral can be done quickly using WolframAlpha by typing in:

<br>

"integrate (x+1)cos(n* pi x) from -1 to 0" 

<a href="https://www.wolframalpha.com/input/?i=integrate+%28x%2B1%29cos%28n*+pi+x%29+from+-1+to+0">WolframAlpha</a>

<br>

This evaluates to:

$$= \frac{1 - \cos(\pi n)}{\pi^2 n^2}$$

To do this manually, apply integration by parts:

\begin{align*}
\int_{-1}^{0}(x+1)\cos\left(\frac{n\pi x}{L}\right) dx &=\left[ \frac{\left(1+x\right)\sin{\left(n\pi{}x\right)}}{n\pi{}}+{\frac{\cos(n\pi{}x)}{n^2{\pi{}}^2}} \right]_{-1}^0
\newline
\newline
&=
\frac{1 - \cos(\pi n)}{\pi^2 n^2},\ \ \ for\ any\ n\geq{}1, 
\end{align*}

<br>

$$\therefore \boxed{a_n = \frac{1 - \cos(\pi n)}{\pi^2 n^2} + 0 =  \frac{1 - (-1)^n}{\pi^2 n^2}}.$$

(3) Similarly, we can find $b_n$:

\begin{align*}
b_n &= \int_{-L}^Lf\left(x\right)\sin{(n\pi x)\
dx=}\int_{-1}^0\left(x+1\right)\sin{(n\pi x)\ dx+}\int_0^1\sin{(n\pi x)\ dx\ }
\newline \newline
\end{align*}

The second integral is straight forward:

$$
\int_{0}^{1}\sin\left(n\pi x\right) dx = \left. - \frac{1}{n\pi{}}\cos{\left(n\pi{}x\right)} \right\vert_{0}^1=- \frac{1}{n\pi{}}\left(\cos{\left(n\pi \right)}- 1\right) 
$$

The first integral can be done quickly using WolframAlpha by typing in:
<br>
"integrate (x+1)sin(n* pi x) from -1 to 0"

<a href="https://www.wolframalpha.com/input/?i=integrate+%28x%2B1%29sin%28n*+pi+x%29+from+-1+to+0">WolframAlpha</a>

<br>

This evaluates to:

$$= \frac{\sin(\pi n) - \pi n}{\pi^2 n^2}$$

It can also be done manually using integration by parts in a similar way to which $b_n$ was found.
<br><br>

$$\therefore \boxed{b_n = \frac{\sin(\pi n) - \pi n}{\pi^2 n^2} - \frac{1}{\pi{} n}\left(\cos{\left(\pi n \right)}- 1\right) = \frac{- 1}{\pi n} - \frac{\left((-1)^n- 1\right)}{\pi{} n} = \frac{- (-1)^n}{\pi n} = \frac{(-1)^{n+1}}{\pi n}}$$

Thus,

$$ \boxed{ f\left(x\right) =
\frac{3}{4}+
\frac{1}{ {\pi{}}^2}\sum_{n=1}^{\infty{}}\frac{1 - (-1)^n}{n^2}\cos(n\pi{}x)
+\frac{1}{\pi{}}\sum_{n=1}^{\infty{}}\frac{ {\left(-1\right)}^{n+1}}{n} \sin⁡(n\pi{}x)
}$$

<br>

Note: this solution includes a mixture of manual working out and WolframAlpha. In an exam, you won't be required to do any of the manual working out as you can just use WolframAlpha!

<br>

<iframe src="https://www.desmos.com/calculator/6lglrfcrfl" width="850px" height="500px" style="border: 1px solid #ccc" frameborder=0></iframe>

</div>

<div class = "workingout"><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br></div>

(c) $f\left(x\right)=\left\\{\begin{array}{l}0,\ \ \ \ \ \text{if}\ -2\leq{}x\leq{}-1 \newline
    1,\ \ \ \ \ \text{if}\ -1 < x < 1 \newline
    0,\ \ \ \ \ \text{if}\ \ 1\leq{}x\leq{}2\end{array}\right.
    $
<div class="answer">
This function is even (and therefore contains no odd Fourier series components), so the $b_n$ terms will all be $0$.
<br>
Starting with $a_0$:

$$
\frac{a_0}{2}=\frac{1}{2} \times \frac{1}{L}\int_{-L}^Lf\left(x\right)dx = \frac{1}{4}\int_{-1}^1 1 \space dx = \frac{1}{2}
$$

Note: we are ignoring what happens when the function is at $0$, because integrating $0$ is just $0$.

<br>

Moving onto the $a_n$ terms:

\begin{align*}
a_n &= \frac{1}{L}\int_{-L}^Lf\left(x\right)\cos{\left(\frac{n\pi{}x}{2}\right)}dx = \frac{1}{2}\int_{-1}^1 1 \cdot \cos{\left(\frac{n\pi{}x}{2}\right)dx}	
\newline \newline
&=
\frac{2}{n\pi{}}\sin{\left(\frac{\pi{}}{2}n\right)}.
\end{align*}

Note: this can be found easily using WolframAlpha by typing in "integrate 1/2 cos((n pi x)/2) between -1 and 1". 

<a href="https://www.wolframalpha.com/input/?i=integrate+1%2F2+cos%28%28n+pi+x%29%2F2%29+between+-1+and+1">WolframAlpha</a>

<br>

$$
\therefore
\boxed{f(x) = 
\frac{1}{2}+\sum_{n=0}^{\infty{}}\frac{2}{n\pi{}}\sin{\left(\frac{\pi{}}{2}n\right)} \cdot \cos\left(\frac{\pi}{2}nx\right)}
$$

<iframe src="https://www.desmos.com/calculator/qrmj8iw5ha" width="850px" height="500px" style="border: 1px solid #ccc" frameborder=0></iframe>

</div>

<div class = "workingout"><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br></div>

(d) $f\left(x\right)=\sin{\left(x\right)}{\cos}^2\left(x\right),\ \ \ \text{on}\
    [ -\pi{},\pi{} ]$

<div class = "answer">
To shortcut this problem, you can make the guess (after plotting the function, perhaps) that $\sin(x)\cos(x)^2$ might be able to be rearranged into a sum of sine components. Entering "sin(x)cos(x)^2" and going to the "Alternate form" section in WolframAlpha reveals that:

$$\sin(x)\cos(x)^2 = \boxed{ \frac{1}{4}\sin(x) + \frac{1}{4}\sin(3x) }$$

This function can already directly be represented in terms of a sum of sine components and therefore, we do not need to compute the series within the given interval (this would reveal that there is an exact approximation with a finite number of terms; the two we just found).

<br><br>

To compute terms manually, using the definition of the Fourier series:

<br>

Note that $f(x)=\sin\left(x\right)\cos^2\left(x\right)$ is odd on the interval $\left[ -1,1\right ]$. Therefore, the Fourier series representation will only contain sine $b_n$ terms.

$$
b_n=\frac{1}{\pi{}}\int_{-\pi{}}^{\pi{}}f(x)\sin{\left(\frac{n\pi{}x}{\pi{}}\right)\ dx=}\
\frac{2}{\pi{}}\int_0^{\pi{}}\sin{(x)}\
{\cos}^2\left(x\right)\sin{\left(nx\right)}dx\
$$

Substituting $ \ \sin(2x)=2\sin(x)\cos(x)$,

$$
b_n=\frac{1}{\pi{}}\int_0^{\pi{}}\cos{\left(x\right)}\sin{(2x)}\sin{\left(nx\right)}\ dx
$$

Using the sine product to sum identity,

$$
\sin{(nx)}\sin{(2x)}=\frac{1}{2}[ \cos{(nx-2x)}-\cos{(nx+2x)}]
$$

$$
b_n=\frac{1}{\pi{}}\int_0^{\pi{}}\cos(x)\frac{1}{2}\left[ \cos({\left(n-2\right)}x)-\cos({\left(n+2\right)x})\right]\
dx
$$

$$
=\ \frac{1}{2\pi{}}\int_0^{\pi{}}\cos(x)\cos((n-2)x)\
dx-\frac{1}{2\pi{}}\int_0^{\pi{}}\cos(x)\cos((n+2)x)\ dx
$$

Using the cosine product to sum identity,

<br>

For the first integral on the right

$$
\frac{1}{2\pi{}}\int_0^{\pi{}}\frac{1}{2}\left[ \cos{\left(\left(n-2\right)+1\right)x+\cos{\left(\left(n-2\right)-1\right)x}}\right]\
dx
$$

$$
=\frac{1}{4\pi{}}\
\left[ \frac{\sin{(n-1)x}}{n-1}+\frac{\sin{(n-3)x}}{n-3}\right]_0^\pi=0
\text{Provided} n\not=1,3
$$
 

<br>

Similarly, the second integral is also zero. 

<br>

Note: because the integral is undefined for certain values of $n$, we need to find what happens at these values ($n=1$ and $n=3$).

<br>

At $n=1$:

$$
b_1=\frac{2}{\pi{}}\int_0^{\pi{}}{\sin}\left(x\right){\sin}\left(x\right){\cos}^2\left(x\right)\
dx
$$

$$
=\frac{1}{\pi{}}\int_0^{\pi{}}{\sin}\left(2x\right){\sin}\left(x\right){\cos}\left(x\right)\
dx
$$

$$
=\frac{1}{\pi{}}\int_0^{\pi{}}{\sin}\left(2x\right)\frac{1}{2}{\sin}\left(2x\right)\
dx
$$

$$
=\frac{1}{2\pi{}}\int_0^{\pi{}}{\sin}^2\left(2x\right)\
dx
$$

$$
=\frac{1}{2\pi{}}\
\left[ \frac{1}{8}(4x-\sin(4x))\right]_0^\pi=\frac{4\pi}{16\pi}=\frac{1}{4}
$$
<br>
Note: to simply the initial equation you use $ \ \sin(x)\cos(x) = \frac{1}{2}\sin(2x)$

<br>

At $n=3$:

$$
b_3=\frac{2}{\pi{}}\int_0^{\pi{}}\sin(x){\cos}^2(x)\sin(3x)\ dx
$$

$$
=\
\frac{1}{\pi{}}\int_0^{\pi{}}\cos(x)\sin(2x)\sin(3x)\
dx
$$

$$
=\frac{1}{\pi{}}\int_0^{\pi{}}(\cos(x))\frac{1}{2}\left[ \cos{\left(3x-2x\right)-\cos{\left(3x+2x\right)}}\right]\
dx
$$

$$
=\frac{1}{2\pi{}}\int_0^{\pi{}}{\cos}^2(x) dx-\frac{1}{2\pi{}}\int_0^{\pi{}}\cos(x)\cos(5x)dx\
$$

For the first integral,

$$
\frac{1}{2\pi{}}\int_0^{\pi{}}\frac{1+\cos(2x)}{2}dx=\frac{1}{4\pi{}}\left[ x+\frac{1}{2}\sin(2x)\right]_0^\pi=\frac{1}{4}
$$

For the second integral,

$$
\frac{1}{2\pi{}}\int_0^{\pi{}}\frac{1}{2}\left[ \cos{\left(5x+x\right)+\cos{\left(5x-x\right)}}\right]dx=\frac{1}{4\pi{}}\int_0^{\pi{}}(\cos{6x+\cos{4x)}}dx
$$

$$
=\frac{1}{4\pi{}}\left[ \frac{1}{6}\sin(6x)+\frac{1}{4}\sin(4x)\right]_0^\pi=0
$$

So $b_3=\frac{1}{4}$, meaning the Fourier series representation is:

$$\boxed{
f\left(x\right)\approx b_1\sin(x)+b_3\sin(3x)\approx \frac{1}{4}\sin(x)+\frac{1}{4}\sin(3x)
}$$

Note: this could have been solved using WolframAlpha as well rather than by hand. You will not be required to solve it by hand in an exam.

<br>

<iframe src="https://www.desmos.com/calculator/qtufiqgvrl" width="850px" height="500px" style="border: 1px solid #ccc" frameborder=0></iframe>

</div>

<div class = "workingout"><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br></div>

(e) $f\left(x\right)=\left\\{\begin{array}{l}\sin{\left(\frac{\pi{}x}{2}\right)},\ \ \
    \ \text{for} \ -2\leq{}x\leq{}0 \newline
    0,\ \ \ \ \ \ \ \ \ \ \ \ \ \text{for}\ \ \
    0 < x\leq{}2\end{array}\right.
    $ with n=3

<div class = "answer">

The function is neither odd nor even therefore it requires both sine and cosine terms.

The expressions for the terms can be found quickly using Wolfram Alpha: 

<br>

$a_0 = $ "integrate 1/2 * sin(pi * x / 2) from -2 to 0"
<a href="https://www.wolframalpha.com/input/?i=integrate+1%2F2+*+sin%28pi+*+x+%2F+2%29+from+-2+to+0">WolframAlpha</a>
<br> 

$a_n = $ "integrate 1/2 * sin(pi * x / 2)cos(n* pi * x / 2) from -2 to 0"

<a href="https://www.wolframalpha.com/input/?i=+integrate+1%2F2+*+sin%28pi+*+x+%2F+2%29cos%28n*+pi+*+x+%2F+2%29+from+-2+to+0">WolframAlpha</a>
<br>

$b_n = $ "integrate 1/2 * sin(pi * x / 2)sin(n* pi * x / 2) from -2 to 0" 
<a href="https://www.wolframalpha.com/input/?i=integrate+1%2F2+*+sin%28pi+*+x+%2F+2%29sin%28n*+pi+*+x+%2F+2%29+from+-2+to+0">WolframAlpha</a>
<br>

<br>

To compute manually,

<br>

$a_0$ coefficient:

\begin{align*}
a_0=\frac{1}{L}\int_{-L}^Lf(x)\
dx=\frac{1}{2}\int_{-2}^0\sin(\frac{\pi x}{2})dx=\frac{1}{2}\
\left.\left(\frac{-2 \cos(\frac{\pi x}{2})}{\pi}\right)\right\vert_{-2}^{0}= \frac{-2}{\pi}
\end{align*}

$$\therefore \frac{a_0}{2} = \frac{\frac{-2}{\pi}}{2} = \frac{-1}{\pi}$$


$a_n$ coefficients:

\begin{align*}
a_n &=\frac{1}{L}\int_{-L}^Lf\left(x\right)\cos{\left(\frac{n\pi{}x}{L}\right)dx=}\frac{1}{2}\int_{-2}^0\sin{\left(\frac{\pi{}x}{2}\right)\cos{\left(\frac{n\pi{}x}{2}\right)}}\
dx
\newline \newline
&=
\frac{1}{2}\int_{-2}^0\frac{1}{2}\left[ \sin{\left(\frac{\left(1+n\right)\pi{}x}{2}\right)}+\sin{\left(\frac{\left(1-n\right)\pi{}x}{2}\right)}\right]\
dx
\newline \newline
&=
\frac{1}{4}\left[ -\frac{2}{\pi{}\left(1+n\right)}\cos{\frac{\left(1+n\right)\pi{}x}{2}}-\frac{2}{\pi{}\left(1+n\right)}\cos{\frac{\left(1-n\right)\pi{}x}{2}}\right]\binom{0}{-2}
\newline \newline
&=
-\frac{1}{4} \left( \frac{4}{\pi{}\left(1+n\right)\left(1-n\right)}+\frac{ {\left(-1\right)}^n4}{\pi{}\left(1+n\right)\left(1-n\right)} \right) =\frac{ {\left(-1\right)}^{n+1}-1}{\pi{}\left(1+n\right)\left(1-n\right)},\
\ \ \ \ for\ \ n\not=1
\newline \newline
a_1 &= \frac{1}{2}\int_{-2}^0\sin{\left(\frac{\pi{}x}{2}\right)\cos{\left(\frac{\pi{}x}{2}\right)\
dx=\frac{1}{4}}}\int_{-2}^0\sin{\pi{}x}\ \ dx=0,\ \ \ \ for\ n=1
\end{align*}

$b_n$ coefficients:

\begin{align*}
b_n &= \frac{1}{L}\int_{-L}^Lf\left(x\right)\sin{\left(\frac{n\pi{}x}{L}\right)dx=\frac{1}{2}}\int_{-2}^0\sin{\left(\frac{nx}{2}\right)}\sin{\left(\frac{n\pi{}x}{2}\right)}dx
\newline \newline
&=
\frac{1}{2}\int_{-2}^0\frac{1}{2}\left[ \left(\cos{\frac{\left(1-n\right)\pi{}x}{2})-(\cos{\frac{\left(1+n\right)\pi{}x}{2}}}\right)\right]\ dx
\newline \newline
&=
\frac{1}{4}\left[ \frac{2}{\pi{}\left(1-n\right)}\sin{\frac{\left(1-n\right)\pi{}x}{2}}-\frac{2}{\pi{}\left(1+n\right)}\sin{\frac{\left(1+n\right)\pi{}x}{2}}\right]\binom{0}{-2}=0,\
\ \ \ for\ n\not=1
\newline \newline
b_1 &= \frac{1}{2}\int_{-2}^0\sin^2{(\frac{\pi{}x}{2})} dx
=\frac{1}{2}\int_{-2}^0\frac{1-\cos{\pi{}x}}{2}\
dx=\frac{1}{4}\left[ x-\frac{1}{\pi{}}\sin{\pi{}x}\right]\binom{0}{-2}=\frac{1}{2}\
,\ \ \ \ for\ n=1\
\end{align*}

Therefore, the fourier series representation is:

$$ \boxed{
f\left(x\right)\approx\frac{-1}{\pi{}}+\frac{1}{2}\sin{\left(\frac{\pi{}x}{2}\right)+\frac{1}{\pi{}}\sum_{n=2}^{\infty{}}\frac{ {\left(-1\right)}^{n+1}-1}{1-n^2}\cos{ \left(\frac{n\pi{}x}{2} \right)}}
}$$

<br>
Note: as in problem 5 d), when calculating the coefficients, you end up with expressions which are undefined for certain values of $n$. In this case for both $a_n$ and $b_n$, $n$ was undefined at $n=1$. So we need to verify what happens at $a_1$ and $b_1$ like we did above.
<br>

<iframe src="https://www.desmos.com/calculator/cepdzyeggd" width="850px" height="500px" style="border: 1px solid #ccc" frameborder=0></iframe>

</div>

<div class = "workingout"><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br></div>



---------------
## Exam Style Questions
### Problem 6.
(a) Consider the function $\ \ y = 10 e^{2x^8} - 8 \ \$ in the interval $\ \ {-3} \ {<} \ x \ {<} \ 3$ . State whether the Fourier Series of this function would contain sine or cosine terms, justifying your answer.

<div class = "answer">
$\Rightarrow \boxed{\text{ The function will only contain cosine terms}}$.
<br>
Justification:
<br>
The function $ \ y = 10 e^{2x^8} - 8 \ $  is an even function, hence it only contains cosine terms.
<br>
For a function to be even $f(-x)=f(x)$:
<br>
$$ \ f(-x) = 10 e^{2(-x)^8} - 8  = 10 e^{2x^8} - 8 = f(x)\ $$
<br>
Note: the function could also be sketched to determine whether its odd or even. You could also get WolframAlpha to tell you whether it is odd, even or neither by typing "Parity of 10e^(2x^8)-8"
<a href="https://www.wolframalpha.com/input/?i=parity+of+10e%5E%282x%5E8%29+-+8">WolframAlpha</a>

<iframe src="https://www.desmos.com/calculator/amhmuk0znf" width="850px" height="500px" style="border: 1px solid #ccc" frameborder=0></iframe>
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br></div>

(b) Sketch the piecewise periodic function $f\left(x\right)=\left\\{\begin{array}{l}-5,\ \ \ \ \
    \ \text{for} \ -2\pi\leq{}x\leq{}\ 0 \newline
    5,\ \ \text{for}\ \ \
    0 < x\leq{}2\pi\end{array}\right.
    $

<div class = "answer">
<iframe src="https://www.desmos.com/calculator/akfeysxfu9" width="850px" height="500px" style="border: 1px solid #ccc" frameborder=0></iframe>
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br></div>

(c) Add additional curves to this plot to represent the first and third order Fourier series approximation in the interval  $\ \ {-2\pi} \ {<} \ x \ {<} \ 2\pi$.

<div class = "answer">
The first step would be to find out what the Fourier series approximation of this function is for the first and third order. Because the function is odd, it will only contain $b_n$ terms.
<br>
Finding the $b_n$ terms:
<br>
$$b_n = \frac{1}{L} \int_{-L}^Lf(x)\sin(\frac{n\pi x}{L})dx  = \frac{1}{2 \pi} \left( \int_{-2 \pi}^0 5\sin \left(\frac{n x}{2}\right)dx + \int_{0}^{2 \pi} -5\sin\left(\frac{n x}{2}\right)dx \right)$$
<br>

To solve each integral on WolframAlpha:
<br>

"integrate 5 sin((n x)/2) between -2pi and 0"
<a href="https://www.wolframalpha.com/input/?i=integrate+5+sin%28%28n+x%29%2F2%29+between+-2pi+and+0">WolframAlpha</a>
<br>

"integrate -5 sin((n x)/2) between 0 and 2pi"
<a href="https://www.wolframalpha.com/input/?i=integrate+-5+sin%28%28n+x%29%2F2%29+between+0+and+2pi">WolframAlpha</a>
<br>

You then end up with:

<br>

$$b_n = \frac{1}{2 \pi} \left(\frac{10(\cos(\pi n) - 1)}{n} + \frac{10(\cos(\pi n) - 1)}{n}\right)
= \frac{1}{2 \pi} \left(\frac{20(\cos(\pi n) - 1)}{n}\right)
= \frac{1}{2 \pi} \left(\frac{20((-1)^n - 1)}{n}\right) $$

<br>

By substituting $n=1$, $n=2$ and $n=3$ we can now calculate $b_1$, $b_2$ and $b_3$:
<br>
$$b_1 = \frac{- 20}{\pi},  \quad b_2 = 0,  \quad b_3 = \frac{- 20}{3 \pi}$$


Finally the fourier expansions $ \ \boxed{b_1 = \frac{- 20}{\pi} \sin \left(\frac{x}{2}\right)} \ $ and  $ \ \boxed{b_3 = \frac{- 20}{\pi} \sin \left(\frac{x}{2}\right) - \frac{20}{3 \pi} \sin \left(\frac{3x}{2}\right)} \ $ can be written down and sketched on the graph.
<br>

<iframe src="https://www.desmos.com/calculator/8gnc2tmdjt" width="850px" height="500px" style="border: 1px solid #ccc" frameborder=0></iframe>
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br></div>

(d) Where would you expect Gibb's ringing to occur as the series was expanded?

<div class = "answer">

You would expect Gibbs ringing to occur at $2 n \pi$, where $n \in \mathbb{Z} $ .</div>

<div class = "workingout"><br><br><br><br><br><br><br><br></div>


----------------------
## Challenging Questions
### Problem 7.
(a) Given the real Fourier series expansion for a periodic function, $f(x)$, with a $2\pi{}$ period,
$$
f\left(x\right) = \frac{1}{2}a_0+\sum_1^{\infty{}}(a_n\cos{\left(nx\right)}+b_n \sin{(nx)}) \space ,
$$
find an expression for the coefficients, $C_n$, of the complex Fourier series,
$$
f\left(x\right) = \sum_{n=-\infty}^{\infty} C_n e^{i n x}
\space .
$$
Give your answer in terms of the real coefficients $a_0$, $a_n$, and $b_n$.

Next express $C_n$ in terms of $f(x)$.

Comment on the relationship between $C_n$ and $C_{-n}$ for real functions.

<div class = "answer">
Looking at the complex Fourier series, there are three differences from the real series:
there is a complex exponential instead of sines and cosines;
the sum is from $-\infty$ to $\infty$ rather than $1$ to $\infty$;
and there is an $a_0$ term.
Let's treat these in order.

First, use Euler's identity to convert the complex exponential to trig functions,

$$f\left(x\right) = \sum_{n=-\infty}^{\infty} C_n \left(
  \cos(n x) + i \sin(n x) \right)
\space .$$

Next, split out the sum into three parts, negative, zero, positive,
\begin{align*}
f\left(x\right) &=
\sum_{n=-1}^{-\infty} C_n \left( \cos(n x) + i \sin(n x) \right) \newline
&+ C_0 \newline
&+ \sum_{n=1}^{\infty} C_n \left( \cos(n x) + i \sin(n x) \right)
\;.
\end{align*}
For the negative sum, we can substitute $n$ for $-n$ as it is a variable within the sum (being summed over). Changing the limits and the coefficient to represent the same negative sum. Noting that $\cos$ is an even function and $\sin$ is odd so that $i \sin(n x)$ becomes $-i \sin(n x)$.
\begin{align*}
f\left(x\right) &=
\sum_{n=1}^{\infty} C_{-n} \left( \cos(n x) - i \sin(n x) \right) \newline
&+ C_0 \newline
&+ \sum_{n=1}^{\infty} C_n \left( \cos(n x) + i \sin(n x) \right)
\;.
\end{align*}
Now the sums are over the same range, they can be combined,
\begin{align*}
f\left(x\right) &= C_0 +
\sum_{n=1}^{\infty} \left( (C_n + C_{-n}) \cos(n x) + i(C_n - C_{-n}) \sin(n x) \right)
\;.
\end{align*}
By inspection, we can now compare terms from our expression to the real Fourier series,
\begin{align*}
    a_0 &= 2 C_0 \newline
    a_n &= C_n + C_{-n} \newline
    b_n &= i C_n -i C_{-n}
\end{align*}
Then to solve this part, rearrange these simultaneous equations in terms of $a_n$, $b_n$
\begin{align*}
    C_0 &= \frac{a_0}{2} \newline
    C_n &= \frac{a_n - i b_n}{2} \newline
    C_{-n} &= \frac{a_n + i b_n}{2}
\end{align*}

For the next part, we'll take our expression for $C_n$ and write the $a$ and $b$ terms as their integral forms.
\begin{align*}
C_n &= \frac{a_n - i b_n}{2} \newline
&= \frac{1}{2}\left(\frac{1}{\pi}\int_{-\pi}^{\pi} f(x) \cos(n x)- i \frac{1}{\pi}\int_{-\pi}^{\pi} f(x) \sin(n x) \right) \newline
&= \frac{1}{2\pi}\int_{-\pi}^{\pi} f(x) \left( \cos(n x)- i \sin(n x) \right) \newline
C_n &= \frac{1}{2\pi}\int_{-\pi}^{\pi} f(x) e^{-i n x}
\end{align*}

Finally for the comment,
given $C_n = (a_n - i b_n) / 2$
and $C_{-n} = (a_n + i b_n) / 2$,
then for real functions, $a$ and $b$ are real,
so $C_{-n} = C_n^*$

</div>

<div class = "workingout"><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br></div>

(b) Find the real Fourier series to the following function.
$$\left(3+4i\right)e^{-2ix}+{\left(3-4i\right)e}^{2ix}$$

<div class = "answer">

$$
\Rightarrow{}\left(3+4i\right)\left[ \cos{\left(2x\right)-i\sin{\left(2x\right)}}\right]+\left(3-4i\right)\left[ \cos{\left(2x\right)+i\sin{\left(2x\right)}}\right] \\\\
$$

$$
=\left(3+4i\right)\cos{\left(2x\right)+}\left(4-3i\right)\sin{\left(2x\right)+}\left(3-4i\right)\cos{\left(2x\right)+\left(4+3i\right)\sin{\left(2x\right)}} \\\\
$$

$$
=\left[ \left(3+4i\right)+\left(3-4i\right)\right]\cos{\left(2x\right)+\left[ \left(4-3i\right)+\left(4+3i\right)\right]\sin{\left(2x\right)}} \\\\
$$

$$
=6\cos{(2x)}+8\sin{(2x)} \\\\
$$

In second line, we must use the fact that $\left(3+4i\right)i=\ -4+3i$ and $\left(3-4i\right)i=4+3i$ in finding the coefficients in front of the $\sin{(2x)}$ term.
</div>

<div class = "workingout"><br><br><br><br><br><br><br><br><br><br><br><br><br><br></div>

------------------------------------
### Problem 8.
Find the complex Fourier series representation of $f(x) = x^3$ over the interval [-$\pi{}$, $\pi{}$]

<div class = "answer">

$$
C_n=\frac{1}{2\pi{}}\int_{-\pi{}}^{\pi{}}x^3e^{-inx}dx
$$

Using the integration by parts, we have

\begin{align*}
C_n &=\frac{1}{2\pi{}}\left[ \frac{ {ix}^3e^{-inx}}{n}+\frac{ {3x}^2e^{-inx}}{n^2}-\frac{ {i6xe}^{-inx}}{n^3}-\frac{ {6e}^{-inx}}{n^4}\right]\binom{\pi{}}{-\pi{}} 
\newline \newline 
&=\
\frac{1}{2\pi{}n^4}\left[ e^{-inx}(in^3x^3+3n^2x^2-i6nx-6\right]\binom{\pi{}}{-\pi{}}
\newline \newline
&=\
\frac{1}{2\pi{}n^4}\left[ {\left(-1\right)}^n\left(-in^3{\pi{}}^3+{3n}^2{\pi{}}^2-i6n\pi{}-6\right)-{\left(-1\right)}^n(-in{\pi{}}^3+3n^2{\pi{}}^2+i6n\pi{}-6\right]
\newline \newline
&=
\frac{ {(-1)}^n}{2\pi{}n^4}\left[ {2in}^3{\pi{}}^3-12in\pi{}\right]=\frac{ {\left(-1\right)}^n}{n^3}\left(n^2{\pi{}}^2-6\right), \ \ \ \ for\ n\not=0 \newline \newline
\end{align*}

$$
\Rightarrow \quad C_0=\frac{1}{2\pi{}}\int_{-\pi{}}^{\pi{}}x^3dx=0,\ \ \ for\ n=0
$$

Since $x^3$ is odd on $\left[ -\pi{},\pi{}\right]$. Hence,

$$
f\left(x\right)=\
\sum_{n=-\infty{}}^{\infty{}}C_ne^{inx}=\sum_{n\not=0}\frac{ {\left(-1\right)}^ni(n^2{\pi{}}^2-6)}{n^3}e^{inx}
$$

</div>

<div class = "workingout"><br><br><br><br><br><br><br><br><br><br><br><br><br><br></div>


<br>


## Answers

<button id="showAnswerButton" type="button" onclick="displayAnswerButtons('block')">Show answer buttons</button>
<button style="display: none" id="hideAnswerButton" type="button" onclick="displayAnswerButtons('none')">Hide answer buttons</button>
<button id="showAnswers" type="button" onclick="displayAnswers('block')">Show all answers</button>
<button style="display: none" id="hideAnswers" type="button" onclick="displayAnswers('none')">Hide all answers</button>
<br><br>

## For Printing
<button id="showPrint" type="button" onclick="prepareForPrint('block')">Add whitespace</button>
<button style="display: none" id="hidePrint" type="button" onclick="prepareForPrint('none')">Remove whitespace</button>

<br><br>

# Next week, Multivariate Calculus!