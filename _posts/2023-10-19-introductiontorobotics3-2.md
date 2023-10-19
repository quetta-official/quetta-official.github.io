---
title:  "[Introduction to Robotics] Chapter 3-2. Algebraic VS Geometric"
excerpt: "3. Inverse Manipulator Kinematics"

categories:
  - Introduction to Robotics
tags:
  - [Robotics]

toc: true
toc_sticky: true
 
date: 2023-10-19
last_modified_at: 2023-10-19
---

&nbsp;

# 1. Algebraic Solution
![image](/assets/images/IR_Figure4.7.png)

&nbsp;

\\(^B_W T=^0_3 T=\left[ \begin{matrix} c_{123} & -s_{123} & 0 & L_1 \ c_1 +L_2 \ c_{12} \cr s_{123} & c_{123} & 0 & L_1 \ s_1 +L_2 \ s_{12} \cr 0 & 0 & 1 & 0 \cr 0 & 0 & 0 & 1 \end{matrix} \right] \\)
- 변수로 표현된 값

\\(^B_W T=\left[ \begin{matrix} c_\phi & -s_\phi & 0 & x \cr s_\phi & c_\phi & 0 & y \cr 0 & 0 & 1 & 0 \cr 0 & 0 & 0 & 1 \end{matrix} \right] \\)
- 숫자로 표현된 값
- 위 식과 같다고 두고 \\(x\\), \\(y\\), \\(\phi\\) 값 계산

&nbsp;

\\(c_\phi =c_{123}\\)\
\\(s_\phi =s_{123}\\)\
\\(x=L_1 \ c_1 +L_2 \ c_{12}\\)\
\\(y=L_1 \ s_1 +L_2 \ s_{12}\\)\

&nbsp;

\\(\rightarrow \ x^2 +y^2 =(L_1^2 \ c_1^2 +2L_1 L_2 c_1 c_{12} + L_2^2 \ c_{12}^2)+(L_1^2 \ s_1^2 +2L_1 L_2 s_1 s_{12} + L_2^2 \ s_{12}^2)=L_1^2 +L_2^2 +2L_1 \ L_2 \ c_2 \\)\
Note that \\(c_1 \ c_{12} +s_1 \ s_{12} = c_2\\)\
\\(\rightarrow \ c_2 =\dfrac{x^2 +y^2 -L_1^2 -L_2^2}{2L_1 \ L_2} \\)\
\\(\rightarrow \ s_2 =\pm \sqrt{1-c_2^2} \\)

&nbsp;

\\(\theta _2 =Atan2(s_2 , \ c_2 )\\)
