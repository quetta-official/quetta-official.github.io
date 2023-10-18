---
title:  "[Introduction to Robotics] Chapter 1-5. Transform Equations"
excerpt: "1. Spatial Descriptions and Transformations"

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

# 1. Transform Equation
![image](/assets/images/IR_Figure2.14.png)

&nbsp;

\\(^U_D T\\)는 두 가지 방법으로 정의할 수 있다.

\\(^U_D T=^U_B T \ ^B_C T \ ^C_D T\\)

\\(^U_D T=^U_A T \ ^A_D T\\)

&nbsp;

위 식에서 \\(^B_C T\\)를 모른다고 가정하면 다음 식의 양변에 역행렬을 곱해 계산할 수 있다.

\\(^U_B T \ ^B_C T \ ^C_D T = ^U_A T \ ^A_D T\\)

\\(^B_C T = ^U_B T^{-1} \ ^U_A T \ ^A_D T \ ^C_D T^{-1} \\)

&nbsp;

## 1-1 Example 2.6
![image](/assets/images/IR_Figure2.16.png)

&nbsp;

