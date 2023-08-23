---
title:  "[Modern Robotics] Chapter 1-1. Degrees of Freedom of a Rigid Body"
excerpt: "1. Configuration Space"

categories:
  - Modern Robotics
tags:
  - [Robotics, Modern Robotics, Degrees of Freedom]

toc: true
toc_sticky: true
 
date: 2023-08-09
last_modified_at: 2023-08-10
---

&nbsp;

# 1. Configuration Space Overview
로봇은 Link(링크)라고 부르는 물체를 Joint(관절)을 사용해 연결한다.\
로봇을 제어할 때 가장 중요한 것은 '로봇이 어디에 있는가'이다.\
Configuration을 사용하면 로봇의 모든 점의 위치를 명시할 수 있다.

&nbsp;

> **Configuration**: 로봇의 모든 점들의 위치를 구체적으로 명시하는 개념

&nbsp;

> **Configuration Space(C-Space)**: 모든 Configuration의 공간

&nbsp;

이 카테고리에서는 모든 로봇이 Rigid Body(강체)로 이루어져 있다고 가정한다.

&nbsp;

> **Rigid Body**: 힘이 가해져도 모양이 변하지 않는 물체

&nbsp;

&nbsp;

&nbsp;

# 2. Degrees of Freedom of a Rigid Body
> **Digree of Freedom(dof)**: Configuration을 표현하기 위해 필요한 가장 적은 수의 실수 좌표

&nbsp;

> **Definition 2.1**\
> 로봇의 **Configuration** 은 로봇의 모든 점의 위치를 완벽하게 명시하는 것이다.\
> Configuration을 표현하기 위해 필요한 최소한의 실수 좌표 수 \\(n\\)을 로봇의 **자유도** 라고 한다.\
> 로봇의 모든 가능한 Configuration을 포함하는 \\(n\\)차원 공간을 **Configuration Space(C-Space)** 라고 한다.
> 로봇의 Configuration은 그 로봇의 C-Space상의 점으로 표현한다.

&nbsp;

> **시스템의 자유도**\
> \\(자유도=(모든 \ 점의 \ 자유도의 \ 합)-(독립적인 \ 제약조건의 \ 개수)\\)\
> 또는
> \\(자유도=(변수의 \ 개수)-(독립적인 \ 식의 \ 개수)\\)

&nbsp;

## 2-1. 예1) 2차원 평면에서의 자유도
2차원 평면 위에 동전이 1개 있다고 가정한다.\
동전 위의 세 점 \\(A\\), \\(B\\), \\(C\\)를 정한다.\
평면에 \\(\hat{x} -\hat{y}\\)가 있을 때 각 점들의 위치는 \\((x_A, \ y_A)\\), \\((x_B, \ y_B)\\), \\((x_C, \ y_C)\\)로 나타낼 수 있다.

&nbsp;

**점 \\(A\\)의 자유도**\
\\(x_A\\), \\(y_A\\) 2개의 자유도가 있다.

&nbsp;

**점 \\(B\\)의 자유도**\
동전은 강체이므로 모양이 변하지 않는다고 가정한다.\
즉 점 \\(A\\)와 점 \\(B\\) 사이의 거리는 일정하다.\
이는 점 \\(B\\)가 점 \\(A\\)에 의해 위치가 제한됨을 의미한다.

&nbsp;

점 \\(B\\)는 점 \\(A\\)를 중심으로 하고 반지름이 \\(d(A, \ B)\\)인 원 위에 존재해야 한다.\
(\\(d(A, \ B)=\sqrt{(x_A -x_B)^2 +(y_A -y_B)^2}\\))\
즉 점 \\(B\\)는 \\(2-1=1\\)개의 자유도를 가진다.

&nbsp;

**점 \\(C\\)의 자유도**\
점 \\(A\\)와 점 \\(B\\)의 위치가 결정되면 점 \\(C\\)의 위치도 결정된다.\
즉 점 \\(C\\)는 0개의 자유도를 가진다.

&nbsp;

따라서 동전은 세 점의 자유도를 모두 합친 3개의 자유도를 가지고 다음과 같이 나타낼 수 있다.\
\\((x_A, \ y_A, \ \phi _{AB})\\)

&nbsp;

> **2차원에서의 강체의 자유도**\
> 3 자유도

&nbsp;

## 2-2. 예2) 3차원 공간에서의 자유도
[예1)](https://shine-loi.github.io/modern%20robotics/modernrobotics1-1/#2-1-%EC%98%881-2%EC%B0%A8%EC%9B%90-%ED%8F%89%EB%A9%B4%EC%97%90%EC%84%9C%EC%9D%98-%EC%9E%90%EC%9C%A0%EB%8F%84)에서의 동전이 3차원 공간에 존재한다고 가정한다.\
세 점 \\(A\\), \\(B\\), \\(C\\)의 좌표는 \\((x_A, \ y_A, \ z_A)\\), \\((x_B, \ y_B, \ z_B)\\), \\((x_C, \ y_C, \ z_C)\\)로 나타낼 수 있다.

&nbsp;

**점 \\(A\\)의 자유도**\
\\(x_A\\), \\(y_A\\), \\(z_A\\) 3개의 자유도가 있다.

&nbsp;

**점 \\(B\\)의 자유도**\
점 \\(B\\)는 중심이 점 \\(x_A\\)이고 반지름이 \\(d(A, \ B)\\)인 구 위에 있어야 한다.\
즉 구 위의 점을 위도와 경도로 표현할 수 있고 \\(3-1=2\\)개의 자유도를 가진다.

&nbsp;

**점 \\(C\\)의 자유도**\
점 \\(C\\)는 점 \\(A\\)를 중심으로 하고 반지름이 \\(d(A, \ C)\\)인 구와 점 \\(B\\)를 중심으로 하고 반지름이 \\(d(B, \ C)\\)인 구의 교선 위에 위치해야 한다.\
따라서 점 \\(C\\)는 \\(3-2=1\\)개의 자유도를 가진다.

&nbsp;

이와같이 3차원상의 강체는 6개의 자유도를 가진다.

&nbsp;

> **3차원에서의 강체의 자유도**\
> 6 자유도
