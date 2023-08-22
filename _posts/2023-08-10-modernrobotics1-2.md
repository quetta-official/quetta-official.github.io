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

&nbsp;

\\(N\\): 링크의 개수 (지면도 링크로 간주함)\
\\(J\\): 관절의 개수\
\\(m\\): 강체의 자유도 (평면에서 \\(m=3\\), 공간에서 \\(m=6\\))\
\\(c_i\\): 관절 \\(i\\)가 제공하는 제약조건\
\\(f_i\\): 관절 \\(i\\)가 제공하는 자유도

&nbsp;

> \\(f_i +c_i =m\\)이 항상 성립

&nbsp;

## 2-1. Example) Four-bar Linkage and Slider-crank Mechanism
![image](/assets/images/Fourbar_Linkage_and_Slidercrank_Mechanism.png)

&nbsp;

**(a) Four-bar Linkage(4절 링크)**\
\\(N=4\\) (지면 포함)\
\\(J=4\\)\
\\(m=3\\) (모든 링크가 평면 위에서 움직이도록 제한됨)\
\\(f_i =1\\) (각 링크의 자유도는 1)\
\\(i=1, \ ... \ , \ 4\\)
\\((자유도)=m(N-1-J)+\Sigma _{i=1} ^J f_i = 3(4-1-4)+\Sigma _{i=1} ^4 1 =-3+4=1\\)

&nbsp;

**(b) Slider-crank Mechanism**\
\\(N=4\\) (지면 포함)\
\\(J=4\\) (3개의 회전형 관절, 1개의 선형 관절)\
\\(m=3\\) (모든 링크가 평면 위에서 움직이도록 제한됨)\
\\(f_i =1\\) (각 링크의 자유도는 1)\
\\(i=1, \ ... \ , \ 4\\)
\\((자유도)=m(N-1-J)+\Sigma _{i=1} ^J f_i = 3(4-1-4)+\Sigma _{i=1} ^4 1 =-3+4=1\\)

&nbsp;

## 2-2. Example) Some Classical Planar Mechanisms
![image](/assets/images/Some_Classical_Mechanisms.png)
