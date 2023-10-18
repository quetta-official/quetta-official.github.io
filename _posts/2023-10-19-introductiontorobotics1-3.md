---
title:  "[Introduction to Robotics] Chapter 1-3. Operators: Translations, Rotations, and Transformations"
excerpt: "1. Spatial Descriptions and Transformations"

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

# 1. Introduction
프레임 사이의 점을 매핑하는 데 사용되는 동일한 수학적 형식은 점을 이동하거나, 벡터를 회전하거나, 둘 다 수행하는 연산자로 해석될 수도 있다.

&nbsp;

&nbsp;

&nbsp;

# 2. Translational Operators
Translation: 주어진 벡터에 따라 유한한 거리만큼 점 이동

&nbsp;

![image](/assets/images/IR_Figure2.9.png)

&nbsp;

구하고자 하는 것: \\(^A P_2\\)
- \\(^A P_1 \\)을 벡터 \\(^A Q\\)에 대해 translate 한 것
\\[^A P_2 =^A P_1 +^A Q\\]

&nbsp;

위 식을 행렬 연산으로 바꾸면 다음과 같다.\
(\\(q_x\\), \\(q_y\\), \\(q_z\\)는 벡터 \\(^A Q\\)의 성분)
\\[^A P_2 =D_Q (q) ^A P_1 \\]
\\[D_Q (q)=\left[ \begin{matrix} 1 & 0 & 0 & q_x \cr 0 & 1 & 0 & q_y \cr 0 & 0 & 1 & q_z \cr 0 & 0 & 0 & 1 \end{matrix} \right] \\]

&nbsp;

&nbsp;

&nbsp;

# 3. Rotational Operators
Rotation Matrix: \\(R_K (\theta )\\)
- \\(K\\)축에 대해 \\(\theta\\)만큼 회전시키는 연산

&nbsp;

Ex) \\(Z\\)축에 대해 \\(\theta\\)만큼 회전하는 연산\
\\[R_z (\theta )=\left[ \begin{matrix} R & 0 \cr 0 & 1 \end{matrix} \right] =\left[ \begin{matrix} cos\theta & -sin\theta & 0 & 0 \cr sin\theta & cos\theta & 0 & 0 \cr 0 & 0 & 1 & 0 \cr 0 & 0 & 0 & 1 \end{matrix} \right] \\]

&nbsp;

## 3-1. Example 2.3
![image](/assets/images/IR_Figure2.10.png)

&nbsp;

주어진 벡터 \\(^A P_1\\)를 \\(Z\\)축에 대해 \\(30^\circ\\) 회전한 벡터 \\(^A P_2\\)

\\(^A P_1 =\left[ \begin{matrix} 0.0 \cr 2.0 \cr 0.0 \end{matrix} \right] \\)

\\(R_Z (30.0) =\left[ \begin{matrix} 0.866 & -0.500 & 0.000 \cr 0.500 & 0.866 & 0.000 \cr 0.000 & 0.000 & 1.000 \end{matrix} \right] \\)

&nbsp;

\\(^A P_2 =R_Z (30.0) ^A P_1 =\left[ \begin{matrix} -1.000 \cr 1.732 \cr 0.000 \end{matrix} \right] \\)

&nbsp;

&nbsp;

&nbsp;

# 4. Transformation Operators
Transformation(순서 주의)
- \\(R\\)에 대해 Rotate
- \\(Q\\)에 대해 Translate

&nbsp;

\\(^A P_2 =T ^A P_1\\)

&nbsp;

## 4-1. Exmaple 2.4
![image](/assets/images/IR_Figure2.11.png)

&nbsp;

주어진 벡터 \\(^A P_1\\)를 \\(Z\\)축에 대해 \\(30^\circ\\) 회전시키고, \\(X_A\\) 방향으로 10, \\(Y_A\\) 방향으로 5만큼 이동.

&nbsp;

\\(^A P_1 =\left[ \begin{matrix} 3.0 \cr 7.0 \cr 0.0 \end{matrix} \right] \\)

\\(T=\left[ \begin{matrix} 0.866 & -0.500 & 0.000 & 10.0 \cr 0.500 & 0.866 & 0.000 & 5.0 \cr 0.000 & 0.000 & 1.000 & 0.0 \cr 0 & 0 & 0 & 1 \end{matrix} \right] \\)

&nbsp;

\\(^A P_2 =T ^A P_1 =\left[ \begin{matrix} 9.098 \cr 12.562 \cr 0.000 \end{matrix} \right] \\)
