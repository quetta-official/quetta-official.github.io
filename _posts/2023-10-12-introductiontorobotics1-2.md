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
!image[/assets/images/IR_Figure2.4.png]

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
\\[^A _B R=\left[ \begin{matrix} ^A \hat{X} _B & ^A \hat{Y} _B & ^A \hat{Z} _B \end{matrix} \right] = left[ \begin{matrix} ^B \hat{X} ^T _A \cr ^B \hat{Y} ^T _A \cr ^B \hat{Z} ^T _A \end{matrix} \right] \\]

&nbsp;
