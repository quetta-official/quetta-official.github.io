---
title:  "[Modern Robotics] Chapter 1-2. Degrees of Freedom of a Robot"
excerpt: "1. Configuration Space"

categories:
  - Modern Robotics
tags:
  - [Robotics, Modern Robotics Degrees of Freedom]

toc: true
toc_sticky: true
 
date: 2023-08-10
last_modified_at: 2023-08-22
---

&nbsp;

# 1. Robot Joints
![image](/assets/images/Typical_Robot_Joints.png)

&nbsp;

**1) Revolute Joint (R, 회전형 관절)**
- 모든 점의 자유도 합: 6 (3차원 공간)
- 두 강체 사이의 제약 조건 수: 5
- 자유도: 6 - 5 = 1

**2) Prismatic Joint (P, 선형 관절)**
- 모든 점의 자유도 합: 6 (3차원 공간)
- 두 강체 사이의 제약 조건 수: 5
- 자유도: 6 - 5 = 1

**3) Helical Joint (H, 나선형 관절)**
- 모든 점의 자유도 합: 6 (3차원 공간)
- 두 강체 사이의 제약 조건 수: 5
- 자유도: 6 - 5 = 1

**4) Cylindrical Joint (C, 원통형 관절)**
- 모든 점의 자유도 합: 6 (3차원 공간)
- 두 강체 사이의 제약 조건 수: 4
- 자유도: 6 - 4 = 2

**5) Universal Joint (U, 유니버셜 관절)**
- 모든 점의 자유도 합: 6 (3차원 공간)
- 두 강체 사이의 제약 조건 수: 4
- 자유도: 6 - 4 = 2

**6) Spherical Joint (S, 구형 관절)**
- 모든 점의 자유도 합: 6 (3차원 공간)
- 두 강체 사이의 제약 조건 수: 3
- 자유도: 6 - 3 = 3

&nbsp;

&nbsp;

&nbsp;

# 2. Grübler's Formula
\\((자유도)=m(N-1)-\Sigma _{i=1} ^J c_i\\)\
\\(=m(N-1)-\Sigma _{i=1} ^J (m-f_i)\\)\
\\(=m(N-1-J)+\Sigma _{i=1} ^J f_i\\)
