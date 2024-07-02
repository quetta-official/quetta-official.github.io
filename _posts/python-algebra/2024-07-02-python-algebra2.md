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
**(Ex 1) Simplify the expression \\(\displaystyle 5x+3x^2 -/frac{1}{x} -\frac{7}{x^3}\\)**

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
