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

\\(^B_W T=^0_3 T=\left[ \begin{matrix} c _{123} & -s _{123} & 0 & L_1 \ c_1 +L_2 \ c _{12} \cr 
s _{123} & c _{123} & 0 & L_1 \ s_1 +L_2 \ s _{12} \cr 0 & 0 & 1 & 0 \cr 0 & 0 & 0 & 1 \end{matrix} \right] \\)
- 변수로 표현된 값

\\(^B_W T=\left[ \begin{matrix} c_\phi & -s_\phi & 0 & x \cr s_\phi & c_\phi & 0 & y \cr 0 & 0 & 1 & 0 \cr 0 & 0 & 0 & 1 \end{matrix} \right] \\)
- 숫자로 표현된 값
- 위 식과 같다고 두고 \\(x\\), \\(y\\), \\(\phi\\) 값 계산

&nbsp;

\\(c_\phi =c_{123}\\)\
\\(s_\phi =s_{123}\\)\
\\(x=L_1 \ c_1 +L_2 \ c_{12}\\)\
\\(y=L_1 \ s_1 +L_2 \ s_{12}\\)

&nbsp;

\\(\rightarrow \ x^2 +y^2 =(L_1^2 \ c_1^2 +2L_1 L_2 c_1 c_{12} + L_2^2 \ c_{12}^2)+(L_1^2 \ s_1^2 +2L_1 L_2 s_1 s_{12} + L_2^2 \ s_{12}^2)\\)

\\(=L_1^2 +L_2^2 +2L_1 \ L_2 \ c_2 \\)

Note that \\(c_1 \ c_{12} +s_1 \ s_{12} = c_2\\)

\\(\rightarrow \ c_2 =\dfrac{x^2 +y^2 -L_1^2 -L_2^2}{2L_1 \ L_2} \\)

\\(\rightarrow \ s_2 =\pm \sqrt{1-c_2^2} \\)
- 부호는 초기 자세를 보고 직접 설정해야 함

&nbsp;

**\\(\theta _2 =Atan2(s_2 , \ c_2 )\\)**

&nbsp;

\\(c_{12} =c_1 \ c_2 -s_1 \ s_2 \\)

\\(s_{12} =s_1 \ c_2 +c_1 \ s_2 \\)

&nbsp;

다음 식에 대입\
\\(x=L_1 \ c_1 +L_2 \ c_{12}\\)

\\(y=L_1 \ s_1 +L_2 \ s_{12}\\)

\\(\rightarrow x=k_1 \ c_1 -k_2 \ s_1\\)

\\(\rightarrow y=k_1 \ s_1 +k_2 \ c_1\\)

where \\(k_1 =L_1 +L_2 \ c_2\\), \\(k_2 =L_2 \ s_2\\)

&nbsp;

## 1-1. Method 1: Perform a Change of Variables
\\(r=\sqrt{x^2 +y^2} = \sqrt{k_1^2 +k_2^2 } \\) 라고 정의하면 다음이 성립한다.\
\\(\gamma =Atan2(k_2 , \ k_1)\\)
- \\(x\\)축을 \\(k_1\\), \\(y\\)축을 \\(k_2\\)라고 할 때 \\(r\\)은 원점에서 \\((k_1 , \ k_2 ) \\) 까지의 거리, \\(\gamma\\)는 \\(x\\)축과 원점과 \\((k_1 , \ k_2 ) \\)를 지나는 직선 사이의 각도라고 할 수 있다.

&nbsp;

\\(k_1 =r \ cos\gamma \\)\
\\(k_2 =r \ sin\gamma \\)

&nbsp;

이를 \\(x\\), \\(y\\)에 대한 식에 대입한다.\
\\(\dfrac xr =cos\gamma \ cos\theta _1 -sin\gamma \ sin\theta_1 =cos(\gamma +\theta _1 )\\)

\\(\dfrac yr =sin\gamma \ cos\theta _1 +cos\gamma \ sin\theta_1 =sin(\gamma +\theta _1 )\\)

&nbsp;

\\(\gamma +\theta _1 =Atan2(\dfrac yr , \ \dfrac xy ) =Atan2(y, \ x)\\)

**\\(\theta _1 =Atan2(y, \ x)-Atan2(k_2 , \ k_1)\\)**

&nbsp;

\\(c_\phi =c_{123}\\)\
\\(s_\phi =s_{123}\\)

\\(\rightarrow \ \theta _1 +\theta _2 +\theta _3 =Atan2(s _\phi , \ c _\phi ) =\phi \\)

**\\(\rightarrow \ \theta _3 =\phi -\theta _1 -\theta _2 \\)**

&nbsp;

## 1-2. Method 2: Matrix
