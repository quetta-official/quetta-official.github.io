---
title:  "[Modern Robotics] Chapter 1-3. Configuration Space: Topology and Representation"
excerpt: "1. Configuration Space"

categories:
  - Modern Robotics
tags:
  - [Robotics, Modern Robotics, Topology]

toc: true
toc_sticky: true
 
date: 2023-08-24
last_modified_at: 2023-08-24
---

&nbsp;

# 1. Configuration Space Topology
공간의 위상은 공간 그 자체의 근본적인 특징이다.\
공간에서 점을 표현하기 위해 선택하는 좌표와 위상은 독립적이다.
> 원 위의 점을 표현하기 위해 어떠한 좌표를 선택하더라도 공간 그 자체는 변하지 않는다.

&nbsp;

> **Topologically Equivalent(위상 동형)**\
> 하나의 공간을 자르거나 붙이지 않고 다른 공간으로 연속적으로 변형할 수 있는 경우

&nbsp;

&nbsp;

&nbsp;

# 2. Configuration Space Representation
![image](/assets/images/MR_Figure2.9.png)

&nbsp;

**1) Point on a Plane**\
위상: 평면\
예시 표현: \\((x, \ y)\\)

&nbsp;

**2) Spherical Pendulum**\
위상: 구\
예시 표현: \\([-180\degree , \ 180\degree ) \ \times \ [-90\degree , \ 90\degree]\\)

&nbsp;

**3) 2R Robot Arm**\
위상: 도넛\
예시 표현: \\([0, \ 2\pi ) \ \times \ [0, \ 2\pi )\\)

&nbsp;

**4) Rotating Sliding Knob**\
위상: 원통\
예시 표현: \\(\[mathbb{R}\] ^1 \ \times \ [0, \ 2\pi )\\)
