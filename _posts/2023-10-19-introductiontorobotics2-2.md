---
title:  "[Introduction to Robotics] Chapter 2-2. Convention for Affixing Frames to Links"
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

# 1. Intermediate Links in the Chain
![image](/assets/images/IR_Figure3.5.png)

&nbsp;

Link에서 Frame을 찾는 규칙
- Frame \\(\lbrace i\rbrace\\)의 \\(\hat{Z}\\)-axis는 \\(\hat{Z} _i\\)라 쓰고 axis \\(i\\)와 일치한다.
- Frame \\(\lbrace i\rbrace\\)의 Origin은 axis \\(i\\)와 \\(a_i\\)의 교점으로 한다.
- \\(\hat{X} _i\\)는 \\(a_i\\)와 일치하며 axis \\(i+1\\)을 가리키는 방향이다.
- \\(\hat{Y} _i\\)는 Right-hand rule에 따라 자동으로 결정된다.

&nbsp;

Reference frame으로 간주되는 Frame \\(\lbrace 0\rbrace \\)는 로봇의 Base에 있으며, 움직이지 않는다.\
\\(\hat{Z} _0\\)는 axis \\(1\\)을 따라 설정하는 것이 계산하기 편하다.

&nbsp;

## 1-1. Example 3.3
![image](/assets/images/IR_Figure3.6.png)
![image](/assets/images/IR_Figure3.7.png)

&nbsp;
