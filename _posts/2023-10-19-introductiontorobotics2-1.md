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

Link는 Base를 0, Base에 가까운 것부터 1~n으로 이름 붙여진다.\
