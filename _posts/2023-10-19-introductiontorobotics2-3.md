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

1) Frame \\(i\\)를 \\(\hat{Z}_i\\) 방향으로 \\(d_i\\)만큼 이동\
2) Frame \\(i\\)를 \\(\hat{Z}_i\\)를 기준으로 \\(\theta_i\\)만큼 회전\
3) Frame \\(i\\)를 \\(\hat{X}_i\\) 방향으로 \\(a_{i-1}\\)만큼 이동\
4) Frame \\(i\\)를 \\(\hat{X}_i\\)를 기준으로 \\(\alpha_{i-1}\\)만큼 회전\

&nbsp;

\\(^{i-1}_i T=R_X (\alpha_{i-1}) \ D_X (a_{i-1}) \ R_Z (\theta_i) \ D_Z (d_i) \\)
