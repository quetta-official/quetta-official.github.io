---
title:  "[Introduction to Robotics] Chapter 2-3. Manipulator Kinematics"
excerpt: "2. Manipulator Kinematics"

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

# 1. Derivation of Link Transformations
Frame \\(\lbrace i-1\rbrace \\)에 대한 Frame \\(\lbrace i\rbrace \\)의 표현은 \\(^{i-1}_i T\\)로 정의한다.
이 Transformation은 4개의 Link parameter에 대한 함수이다.

&nbsp;

1) Frame \\(i\\)를 \\(\hat{Z} _i\\) 방향으로 \\(d_i\\)만큼 이동\
2) Frame \\(i\\)를 \\(\hat{Z} _i\\)를 기준으로 \\(\theta _i\\)만큼 회전\
3) Frame \\(i\\)를 \\(\hat{X} _i\\) 방향으로 \\(a _{i-1}\\)만큼 이동\
4) Frame \\(i\\)를 \\(\hat{X} _i\\)를 기준으로 \\(\alpha _{i-1}\\)만큼 회전\

&nbsp;

\\(^{i-1}_i T=R_X (\alpha_{i-1}) \ D_X (a_{i-1}) \ R_Z (\theta_i) \ D_Z (d_i) =\left[ \begin{matrix} c\theta_i & -s\theta_i & 0 & a_{i-1} \cr s\theta_i \ c\alpha_{i-1} & c\theta_i \ c\alpha_{i-1} & -s\alpha_{i-1} & -s\alpha_{i-1} \ d_i \cr s\theta_i \ s\alpha_{i-1} & c\theta_i \ s\alpha_{i-1} & c\alpha_{i-1} & c\alpha_{i-1} \ d_i \cr 0 & 0 & 0 & 1 \end{matrix} \right] \\)

&nbsp;

&nbsp;

&nbsp;

# 2. Concatenating Link Transformations
정기구학(Forward Kinematics): 주어진 Link의 Parameter 값을 사용해 작용점의 위치 계산\
역기구학(Inverse Kinematics): 작용점의 위치를 통해 각 Link의 Parameter 값 계산

&nbsp;

양방향 전환을 지속적으로 주고받아야 로봇 제어 가능
