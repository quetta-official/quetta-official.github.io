---
title:  "[Introduction to Robotics] Chapter 1-4. Transformation Arithmetic"
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
여러 개의 Transform Matrix를 차례로 곱해 첫 지점과 마지막 지점을 변환하는 하나의 Transform Matrix 계산 가능

&nbsp;

예) \\(^B_1 T ^1_2 T ^2_3 T ^3_4 T ^4_E T= ^B_E T\\)

&nbsp;

&nbsp;

&nbsp;

# 2. Compound Transformations
![image](/assets/images/IR_Figure2.12.png)

&nbsp;

주어진 \\(^C P\\)에 대해 \\(^A P\\) 계산

&nbsp;

\\(^B P=^B_C T ^C P\\)
- \\(^B_C T=\left[ \begin{matrix} ^B_C R & ^B P_{CORG} \cr 0 & 1 \end{matrix} \right]

&nbsp;

\\(^A P=^A_B T ^B P\\)
- \\(^A_B T=\left[ \begin{matrix} ^A_B R & ^A P_{BORG} \cr 0 & 1 \end{matrix} \right]
 
&nbsp;

\\(^A P=^A_C T ^C P=^A_B T ^B_C T ^C P\\)

\\(^A_C T =^A_B T ^B_C T =\left[ \begin{matrix} ^A_B R ^B_C R & ^A_B R ^B P_{CORG} +^A P_{BORG} \cr 0 & 1 \end{matrix} \right] \\)

&nbsp;

&nbsp;

&nbsp;

# 3. Inverting a Transform
