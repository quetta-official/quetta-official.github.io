---
title:  "[Introduction to Robotics] Chapter 1-1. Descriptions: Positions, Orientations, and Frames"
excerpt: "1. Spatial Descriptions and Transformations"

categories:
  - Introduction to Robotics
tags:
  - [Robotics]

toc: true
toc_sticky: true
 
date: 2023-09-18
last_modified_at: 2023-09-18
---

&nbsp;

# 1. Introduction
- Robotic Manipulation은 part와 tool이 일종의 메커니즘에 의해 공간 내에서 이동된다는 것을 의미한다.
- 이는 part, tool, 메커니즘의 위치와 방향을 표현할 필요가 있다.
- 위치와 방향을 나타내기 위해 좌표계를 정의하고 표현 규칙을 정해야 한다.
- Cartesian coordinate system을 기준으로 모든 위치와 방향을 설명한다.

&nbsp;

&nbsp;

&nbsp;

# 2. Description
조작 시스템이 다루는 다양한 객체의 속성을 지정한다.

&nbsp;

&nbsp;

&nbsp;

# 3. Description of a position
좌표계가 설정되면 어떠한 점도 \\(3 \times 1\\) Position vector로 나타낼 수 있다.\
\\(^A P\\)는 좌표계 \\(A\\)에서 측정된 점 \\(P\\)의 위치를 의미한다.
\\[^A P=\left[ \begin{matrix} P_x \cr P_y \cr P_z \end{matrix} \right]\\]

![image]()

&nbsp;

&nbsp;

&nbsp;

# 4. Description of an Orientation
공간상의 점을 표시하기 위해 Orientation을 표시해야 할 수도 있다.\
좌표계 \\(B\\)에 대해 표시된 점의 위치를 좌표계 \\(A\\)에 대해 표시할 경우 Orientation을 사용할 수 있다.

&nbsp;

좌표계 \\(A\\)에서 볼 때 좌표계 \\(B\\)의 축 벡터 표기는 다음과 같이 나타낸다.
\\[Rotation \ Matrix: \ ^A _B R=\left[ \begin{matrix} ^A \hat X _B & ^A \hat Y _B & ^A \hat Z _B \end{matrix} \right] =\left[ \begin{matrix} ^B \hat X ^T _A \cr ^B \hat Y ^T _A \cr ^B \hat Z ^T _A \end{matrix} \right] \\]

&nbsp;

Rotation Matrix는 Unit vector의 Dot product로 나타낼 수 있다.
\\[^A _B R=\left[ \begin{matrix} ^A \hat X _B & ^A \hat Y _B & ^A \hat Z _B \end{matrix} \right] = \left[ \begin{matrix} \hat X _B \cdot \hat X _A & \hat Y _B \cdot \hat X _A & \hat Z _B \cdot \hat X _A \cr \hat X _B \cdot \hat Y _A & \hat Y _B \cdot \hat Y _A & \hat Z _B \cdot \hat Y _A \cr \hat X _B \cdot \hat Z _A & \hat Y _B \cdot \hat Z _A & \hat Z _B \cdot \hat Z _A \end{matrix} \right]\\]

&nbsp;

## 4-1. Example
![image]()

&nbsp;

\\{^A _B R=\left[ \begin{matrix} 0 & 1 & 0 \cr 0 & 0 & 1 \cr 1 & 0 & 0 \end{matrix} \right] \\)

![image]()
\\{^A _B R=\left[ \begin{matrix} c\theta & -s\theta & 0 \cr s\theta & c\theta & 0 \cr 0 & 0 & 1 \end{matrix} \right] \\)
