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

## 1-1. Examples
![image](/assets/images/MR_Figure2.9.png)

&nbsp;

**1) Point on a Plane**\
위상: 평면\
예시 표현: \\((x, \ y)\\)

&nbsp;

평면에서 움직이는 점의 위상은 2차원 유클리드 공간이며 형상은 두 개의 실수로 나타낼 수 있다.

&nbsp;

**2) Spherical Pendulum**\
위상: 구\
예시 표현: \\([-180^\circ , \ 180^\circ ) \ \times \ [-90^\circ , \ 90^\circ]\\)

&nbsp;

구의 중심을 기준으로 구면을 회전하는 구면 진자의 위상은 구의 2차원 표면이며 형상은 위도(Latitude)와 경도(Longitude)로 나타낼 수 있다.\
형상의 가장 위쪽 선분은 구의 북극, 가장 아래쪽 선분은 구의 남극을 나타낸다.

&nbsp;

**3) 2R Robot Arm**\
위상: 도넛\
예시 표현: \\([0, \ 2\pi ) \ \times \ [0, \ 2\pi )\\)

&nbsp;

2R Robot의 위상은 도넛의 2차원 표면이며 형상은 \\(0\\)에서 \\(2\pi\\) 사이의 두 좌표로 나타낼 수 있다.\
2R Robot의 형상은 도넛을 자르고 펼쳐서 만든 평면이다.\
도넛의 형상이 연속적으로 이어지더라도 표현되는 좌표는 \\(0\\)과 \\(2\pi\\) 사이에서 불연속적으로 변한다.

&nbsp;

**4) Rotating Sliding Knob**\
위상: 원통\
예시 표현: \\(\mathbb{R} ^1 \ \times \ [0, \ 2\pi )\\)

&nbsp;

회전하며 미끄러지는 손잡이의 위상은 원통이며 형상은 미끄러진 거리를 나타내는 실수 하나와 \\(0\\)에서 \\(2\pi\\) 사이의 하나의 각도로 나타낼 수 있다.\
회전하며 미끄러지는 손잡이의 형상은 원통을 자르고 펼쳐서 만든 평면이다.\
각도 좌표는 \\(0\\)과 \\(2\pi\\) 사이에서 불연속적으로 변한다.

&nbsp;

&nbsp;

&nbsp;

# 2. Configuration Space Representation
