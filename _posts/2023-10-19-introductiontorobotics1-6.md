---
title:  "[Introduction to Robotics] Chapter 1-6. More on Representatino of Orientation"
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
문제에 대해 어떤 Orientation을 사용할지 명시해야 한다.

&nbsp;

&nbsp;

&nbsp;

# 2. X-Y-Z Fixed Angles
Frame \\(\lbrace A\rbrace \\)에 대해 Frame \\(\lbrace B\rbrace \\)를 \\(X_A\\)에 대해 \\(\gamma\\), \\(Y_A\\)에 대해 \\(\beta\\), \\(Z_A\\)에 대해 \\(\alpha\\)만큼 차례대로 회전시킨다.

&nbsp;

![image](/assets/images/IR_Figure2.17.png)

&nbsp;

\\(^A_B R_{XYZ} (\gamma, \ \beta, \ \alpha )=R_Z (\alpha) \ R_Y (\beta) \ R_X (\gamma) =\left[ \begin{matrix} c\alpha & -s\alpha & 0 \cr s\alpha & c\alpha & 0 \cr 0 & 0 & 1 \end{matrix} \right] \left[ \begin{matrix} c\beta & 0 & s\beta \cr 0 & 1 & 0 \cr -s\beta & 0 & c\beta \end{matrix} \right] \left[ \begin{matrix} 1 & 0 & 0 \cr 0 & c\gamma & -s\gamma \cr 0 & s\gamma & c\gamma \end{matrix} \right] \\)

\\(^A_B R_{XYZ} (\gamma, \ \beta, \ \alpha )=\left[ \begin{matrix} c\alpha \ c\beta & c\alpha \ s\beta \ s\gamma -s\alpha \ c\gamma & c\alpha \ s\beta \ c\gamma +s\alpha \ s\gamma \cr s\alpha \ c\beta & s\alpha \ s\beta \ s\gamma +c\alpha \ c\gamma & s\alpha \ s\beta \ c\gamma -c\alpha \ s\gamma \cr -s\beta & c\beta \ s\gamma & c\beta \ c\gamma \end{matrix} \right] \\)

