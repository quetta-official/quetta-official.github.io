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
조작 시스템이 다루는 다양한 객체의 속성을 지정한다.\

&nbsp;

&nbsp;

&nbsp;

# 3. Description of a position
좌표계가 설정되면 어떠한 점도 \\(3 \times 1\\) Position vector로 나타낼 수 있다.\
\\(^A P\\)는 좌표계 \\(\{A\}\\)에서 측정된 점 \\(P\\)의 위치를 의미한다.
