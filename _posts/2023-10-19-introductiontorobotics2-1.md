---
title:  "[Introduction to Robotics] Chapter 2-1. Link Description"
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

# 1. Introduction
Manipulator는 관절들로 연결이 된 Link로 구성되어 있다.\
DOF(Degree of Freedom): 자세 결정에 필요한 최소 관절 개수
- 3차원 공간에서는 일반적으로 6 자유도를 가진다.
대부분의 Manipulator는 Revolute joint와 Prismatic joint로 구성되어 있다.

&nbsp;

![image](/assets/images/IR_Figure3.2.png)

&nbsp;

Link: Base를 \\(0\\), Base에 가까운 것부터 \\(1~n\\)으로 이름 붙여진다.\
Joint axis: Link \\(i\\)의 왼쪽(Base와 가까워지는 쪽)이 \\(i\\), 오른쪽이 \\(i+1\\)로 이름 붙여진다.\
Link length, \\(a_{i-1} \\): axis \\(i-1\\), \\(i\\)에 동시에 수직인 선의 길이
- 두 axis에 동시에 수직인 직선은 항상 존재한다.

Link twist, \\(\alpha_{i-1} \\): axis \\(i-1\\), \\(i\\)의 각도\
Link offset, \\(d_i \\): axis \\(i\\)에서 \\(a_{i-1}\\)와의 교차점과 \\(a_i\\)와의 교차점 사이의 부호를 고려한 거리
- Prismatic joint에서는 이 값이 변수로서 사용된다.

Joint angle, \\(\theta_i\\): \\(a_{i-1}\\)와 \\(a_i\\) 사이의 각도
- Revolute joint에서는 이 값이 변수로서 사용된다.

&nbsp;

&nbsp;

&nbsp;

# 2. Link Parameters
모든 로봇은 각 Link에 대해 4개의 parameter만 사용해서 역학적으로 분석할 수 있다.
- Link 표현: 2개
- Link의 연결 표현: 2개

&nbsp;

일반적으로 이러한 표현법을 Denavit-Hartenberg(D-H) Notation이라 부른다.
