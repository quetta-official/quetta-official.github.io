---
title:  "[Introduction to Robotics] Chapter 3-1. Solvability"
excerpt: "3. Inverse Manipulator Kinematics"

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

# 1. Existence of Solutions
역기구학 계산 과정에서는 해가 존재하지 않는 경우도 있다.\
즉 해 존재 여부를 먼저 판별해야 한다.

&nbsp;

Workspace: Manipulator의 End-effector가 도달할 수 있는 공간\
Dextrous Workspace: Manipulator의 End-effector가 모든 방향에서 도달할 수 있는 공간\
Reachable Workspace: Manipulator의 End-effector가 적어도 한 방향으로 도달할 수 있는 공간

&nbsp;

![image](/assets/images/IR_Figure4.1.png)

&nbsp;

\\(L_1 =L_2\\)인 경우\
Dextrous Workspace: 원점\
Reachable Workspace: 반지름이 \\(2L_1\\)인 원

&nbsp;

\\(L_1 \neq L_2\\)인 경우\
Dextrous Workspace: 존재하지 않음\
Reachable Workspace: 반지름이 \\(L_1 +L_2\\)인 원의 내부와 반지름이 \\(|L_1 -L_2 |\\)인 원의 외부

&nbsp;

&nbsp;

&nbsp;

# 2. Multiple Solutions
![image](/assets/images/IR_Figure4.2.png)

&nbsp;

한 위치에 도달하게 하는 여러 해 존재 가능\
에너지 소비 최소화를 위해 이동 거리를 최소화하는 것이 가장 효율적이다.
