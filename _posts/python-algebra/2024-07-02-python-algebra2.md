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
last_modified_at: 2024-07-02
---

&nbsp;

# 1. The 'cancel()' Function and the 'simplify()' Function
**(Ex 1) Simplify the expression \\(\displaystyle 5x+3x^2 -\frac{1}{x} -\frac{7}{x^3}\\)**

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
**(Ex 2) Simplify the expression \\(\displaystyle \frac{\sqrt{5} +\sqrt{20} x}{\sqrt{3} +\sqrt{12} x}\\)**

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
