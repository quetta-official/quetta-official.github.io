---
title:  "[Python-Algebra] Chapter 2. Polynomial, Rational, and Radical Expressions"
excerpt: ""

categories:
  - Python-Algebra
tags:
  - [Python, Algebra]

toc: true
toc_sticky: true
 
date: 2024-07-02
last_modified_at: 2024-07-03
---

&nbsp;

# 1. The 'cancel()' Function and the 'simplify()' Function
**(Ex 1) Simplify the expression \\(\displaystyle 5x+3x^2 -\frac{1}{x} -\frac{7}{x^3}\\).**

&nbsp;

```python
import sympy as sym
from IPython.display import display, Math

x=sym.symbols("x")
exp=5*x+3*(x**2)-1/x-7/(x**3)

display(Math("%s" %sym.latex(exp)))
display(Math("%s" %sym.latex(sym.cancel(exp))))
display(Math("%s" %sym.latex(sym.simplify(exp))))
```

&nbsp;

In the previous post, I explained that Python simplifies expressions automatically when you store them in variables. However, when you simply print the variable 'exp', it displays the original expression without any simplification. This means, Python calculate the same terms to simplify but doesn't automatically combine fractions as required in this example. To achieve the desired simplification, I used both the 'cancel()' and 'simplify()' functions.

&nbsp;

Both functions share similar features but with some key differences. The 'cancel()' function is primarily used to canceling fractions by removing common divisors from both the denominator and numerator. On the other hand, the 'simplify()' function is typically used for numerical simplification tasks such as factorization. In many cases, these functions yield the same results. However, in certain scenarios, such as the example provided, they may produce slightly different outputs due to their distinct approaches to simplication.

&nbsp;

You can observe that the 'cancel()' function generates the standard rational expression. In contrast, the 'simplify()' function further simplifies the numerator.

&nbsp;

**Output**\\
\\(\displaystyle 5x+3x^2 -\frac{1}{x} -\frac{7}{x^3}\\)\\
\\(\displaystyle \frac{3x^5 +5x^4 -x^2 -7}{x^3}\\)\\
\\(\displaystyle \frac{x^4 (3x+5)-x^2 -7}{x^3}\\)

&nbsp;

# 2. Rationalizing the Denominator
**(Ex 2) Simplify the expression \\(\displaystyle \frac{\sqrt{5} +\sqrt{20} x}{\sqrt{3} +\sqrt{12} x}\\).**

&nbsp;

```python
import sympy as sym
from IPython.display import display, Math

x=sym.symbols("x")
exp=(sym.sqrt(5)+sym.sqrt(20)*x)/(sym.sqrt(3)+sym.sqrt(12)*x)

display(Math("%s" %sym.latex(sym.simplify(exp))))
```

&nbsp;

**Output**\\
\\(\displaystyle \frac{\sqrt{15}}{3}\\)

&nbsp;

# 3. Canceling
**(Ex 3) Simplify the expression \\(\displaystyle \frac{3x^6 +21x^4}{x^4 +11x^2 +28}\\).**

&nbsp;

```python
import sympy as sym
from IPython.display import display, Math

x=sym.symbols("x")
exp=(3*(x**6)+21*(x**4))/(x**4+11*(x**2)+28)

display(Math("%s" %sym.latex(sym.simplify(exp))))
```

&nbsp;

**Output**\\
\\(\displaystyle \frac{3x^4}{x^2 +4}\\)

&nbsp;

# 4. Using Two Unknowns
**(Ex 4) Simplify the expression \\(\displaystyle \frac{3x^2 +5xy+2y^2}{15x+10y}\\).**

&nbsp;

```python
import sympy as sym
from IPython.display import display, Math

x, y=sym.symbols("x, y")
exp=(3*(x**2)+5*x*y+2*y**2)/(15*x+10*y)

display(Math("%s" %sym.latex(sym.simplify(exp))))
```

&nbsp;

I used the same method as in the previous examples in the code above, but with a different way to define unknowns. This is because there are two unknowns in this example. You can define two unknowns by seperating 'x' and 'y' with a comma(,).

&nbsp;

**Output**\\
\\(\displaystyle \frac{x}{5} +\frac{y}{5}\\)

&nbsp;

# 5. Substitution
**(Ex 5) Simplify the expression \\(5x+7y-25\\) where \\(y=x+1\\).**

&nbsp;

```python
import sympy as sym
from IPython.display import display, Math

x, y=sym.symbols("x, y")
exp=5*x+7*y-25
suby=2*x+1

new_exp=exp.subs(y, suby)
display(Math("%s" %sym.latex(new_exp)))
```

&nbsp;

The variable 'exp' in the code above stores the expression that should be simplified. I stored \\(y=x+1\\) in the variable 'suby'. If you store the expression directly in the variable 'y', Python will define a new variable 'y' different from the original 'y' defined by the 'symbols()' function, which may result in incorrect outputs. Afterward, store the new expression created by substituting the value of 'y' in the variable 'new_exp'. You can use the 'subs()' function to substitute 'y'. The structure of the 'subs()' function is as follows:

&nbsp;

```python
expression.subs(variable, value)
```

&nbsp;

**Output**\\
\\(19x-18\\)

&nbsp;

# 6. Determining the Cancel Possibility
**(Ex 6) Find the natural number y less than 10 that makes the expression \\(\displaystyle \frac{10x^3 +33x^2 +23x -y}{2x+3}\\) cancelable, and print the result.**

&nbsp;

```python
import sympy as sym
from IPython.display import display, Math

x, y=sym.symbols("x, y")
exp=(10*x**3+33*x**2+23*x-y)/(2*x+3)

for yi in range(1, 10):
    tempexp=exp.subs(y, yi)
    if sym.fraction(sym.cancel(tempexp))[1]==1:
        print("y =", yi)
        display(Math("%s" %sym.latex(sym.simplify(tempexp))))
        break
```

&nbsp;

In the code above, the variable 'yi' takes values from 1 to 9 and is sequentially substituted into 'y'. The code stores each expression, created by substituting 'yi' into 'y', in the variable 'tempexp'. The 'fraction()' function used in the 'if' statement returns the given expression in the form of a fraction. The 'fraction()' function returns a tuple, which sequentially stores the numerator and the denominator. This means the 'if' statement cancels the expression 'tempexp' using the 'cancel()' function and checks whether the denominator is 1. If the denominator is 1, the expression is successfully canceled, indicating that the value of 'yi' is a solution. When Python finds a solution, it stops executing the remaining code. If there is no solution within the given range, the code will terminate without printing anything.

&nbsp;

**Output**\\
\\(y=6\\)\\
\\(5x^2 +9x-2\\)
