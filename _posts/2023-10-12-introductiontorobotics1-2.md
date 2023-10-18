---
title:  "[Introduction to Robotics] Chapter 1-2. Mappings: Changing Descriptions from Frame to Frame"
excerpt: "1. Spatial Descriptions and Transformations"

categories:
  - Introduction to Robotics
tags:
  - [Robotics]

toc: true
toc_sticky: true
 
date: 2023-10-12
last_modified_at: 2023-10-12
---

&nbsp;

# 1. Introduction
- mapping: 동일한 물리량에 대해 기준 frame을 바꾸는 작업.
- mapping을 사용하면 동일한 대상을 다양한 좌표계에서 표현할 수 있다.

&nbsp;

&nbsp;

&nbsp;

# 1. Mappings involving translated frames
![image](/assets/images/IR_Figure2.4.png)

&nbsp;

위 좌표계에서 \\(^A P_{BORG}\\), \\(^B P\\)가 주어졌을 때, \\(^A P\\)는 다음과 같다.\
\\[^A P=^B P+ ^A P_{BORG}\\]
이는 벡터의 합과 비슷하게 생각할 수 있다.

&nbsp;

해당 점의 물리적 위치는 변하지 않는다.\
좌표계가 달라짐에 따라 해당 점을 표현하는 방식이 달라지는 것이다.

&nbsp;

&nbsp;

&nbsp;

# 2. Mappings involving rotated frames
한 frame의 orientation을 다른 frame의 좌표로 표현하는 방법\
좌표계 \\(A\\)에 대한 좌표계 \\(B\\)를 표현하는 Rotation matrix은 \\(^A _B R\\)이라 한다.\
\\[^A _B R=^B _A R^{-1} =^B _A R^T \\]
\\[^A _B R=\left[ \begin{matrix} ^A \hat{X} _B & ^A \hat{Y} _B & ^A \hat{Z} _B \end{matrix} \right] = \left[ \begin{matrix} ^B \hat{X} ^T _A \cr ^B \hat{Y} ^T _A \cr ^B \hat{Z} ^T _A \end{matrix} \right] \\]

&nbsp;

\\(^A _B R\\), \\(^B P\\)의 Dot Product를 구하면 \\(^A P\\)를 구할 수 있다.
\\[^A p_x =^B \hat{X} _A \cdot ^B P, \ ^A p_y =^B \hat{Y} _A \cdot ^B P, \ ^A p_z =^B \hat{Z} _A \cdot ^B P \\]
\\[\rightarrow \left[ \begin{matrix} ^B \hat{X} ^T _A \ ^B P \cr ^B \hat{Y} ^T _A \ ^B P \cr ^B \hat{Z} ^T _A \ ^B P \end{matrix} \right] \\]
\\[^A P=^A _B R \ ^B P\\]

&nbsp;

## 2-1. Example 2.1
![image](/assets/images/IR_Figure2.6.png)

&nbsp;

Frame \\(\lbrace B \rbrace \\)가 Frame \\(\lbrace A \rbrace \\)에 대해 \\(Z\\)축을 기준으로 \\(30^\circ \\) 회전했을 때 Rotation matrix.

&nbsp;

\\[^A _B R = \left[ \begin{matrix} c30^\circ & -s30^\circ & 0 \cr s30^\circ & c30^\circ & 0 \cr 0 & 0 & 1 \end{matrix} \right] = \left[ \begin{matrix} 0.866 & -0.500 & 0.000 \cr 0.500 & 0.866 & 0.000 \cr 0.000 & 0.000 & 1.000 \end{matrix} \right] \\]

&nbsp;

&nbsp;

&nbsp;

# 3. Mappings involving general frames
![image](/assets/images/IR_Figure2.7.png)

&nbsp;

구하고자 하는 것: \\(^A P\\)\
Frame \\(\lbrace A\rbrace \\)를 기준으로 Frame \\(\lbrace B\rbrace \\)의 원점을 가리키는 벡터: \\(^A P_{BORG}\\)\
Frame \\(\lbrace B\rbrace \\)를 Frame \\(\lbrace A\rbrace \\)의 방향으로 회전시키는 Rotation Matrix: \\(^A _B R\\)

&nbsp;

General Transformation Mapping: \\(^A P=^A _B R ^B P+ ^A P_{BORG}\\)\
Conceptual form(간단히 표현): \\(^A P=^A _B T ^B P\\)

&nbsp;

Homogeneous Transformation Matrix: \\(\left[ \begin{matrix} ^A P \cr 1\end{matrix} \right] =^A _B T \left[ \berin{matrix} ^B P \cr 1\end{matrix} \right] =\left[ \begin{matrix} ^A _B R & ^A P_{BORG} \cr 0_{1\times 3} & 1\end{matrix} \right] \left[ \berin{matrix} ^B P \cr 1\end{matrix} \right] \\)
