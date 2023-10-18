---
title:  "[Introduction to Robotics] Chapter 1-6. More on Representatino of Orientation"
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

# 1. Introduction
문제에 대해 어떤 Orientation을 사용할지 명시해야 한다.

&nbsp;

&nbsp;

&nbsp;

# 2. X-Y-Z Fixed Angles
Frame \\(\lbrace A\rbrace \\)에 대해 Frame \\(\lbrace B\rbrace \\)를 \\(X_A\\)에 대해 \\(\gamma\\), \\(Y_A\\)에 대해 \\(\beta\\), \\(Z_A\\)에 대해 \\(\alpha\\)만큼 차례대로 회전시킨다.

&nbsp;

![image](/assets/images/IR_Figure2.17.png)

&nbsp;

\\(^A_B R_{XYZ} (\gamma, \ \beta, \ \alpha )=R_Z (\alpha) \ R_Y (\beta) \ R_X (\gamma) =\left[ \begin{matrix} c\alpha & -s\alpha & 0 \cr s\alpha & c\alpha & 0 \cr 0 & 0 & 1 \end{matrix} \right] \left[ \begin{matrix} c\beta & 0 & s\beta \cr 0 & 1 & 0 \cr -s\beta & 0 & c\beta \end{matrix} \right] \left[ \begin{matrix} 1 & 0 & 0 \cr 0 & c\gamma & -s\gamma \cr 0 & s\gamma & c\gamma \end{matrix} \right] \\)

\\(^A_B R_{XYZ} (\gamma, \ \beta, \ \alpha )=\left[ \begin{matrix} c\alpha \ c\beta & c\alpha \ s\beta \ s\gamma -s\alpha \ c\gamma & c\alpha \ s\beta \ c\gamma +s\alpha \ s\gamma \cr s\alpha \ c\beta & s\alpha \ s\beta \ s\gamma +c\alpha \ c\gamma & s\alpha \ s\beta \ c\gamma -c\alpha \ s\gamma \cr -s\beta & c\beta \ s\gamma & c\beta \ c\gamma \end{matrix} \right] \\)

\\(^A_B R_{XYZ} (\gamma, \ \beta, \ \alpha )=\left[ \begin{matrix} r_{11} & r_{12} & r_{13} \cr r_{21} & r_{22} & r_{23} \cr r_{31} & r_{32} & r_{33} \end{matrix} \right] \\)

&nbsp;

\\(\beta =Atan2(-r_{31}, \ \sqrt{r_{11} ^2 +r_{21} ^2}) \\), where \\(-90^\circ <\beta <90^\circ \\)

\\(\alpha =Atan2(\dfrac{r_{21}}{c\beta} , \ \dfrac{r_{11}}{c\beta}) \\)

\\(\gamma =Atan2(\dfrac{r_{32}}{c\beta} , \ \dfrac{r_{33}}{c\beta}) \\)

- \\(\beta\\)를 먼저 구해야 \\(\alpha\\), \\(\gamma\\)를 구할 수 있다.
- \\(cos\beta =0\\)이면 \\(\alpha\\), \\(\gamma\\)가 정의되지 않는다.

&nbsp;

## 2-1. \\(\beta =\pm 90.0^\circ \\)인 경우
다음과 같이 경우를 나누어 계산할 수 있다.\
1) \\(\beta =90.0^\circ \\)인 경우\
   \\(\beta =90.0^\circ \\)

   \\(\alpha =0.0\\)

   \\(\gamma =Atan2(r_{12} , \ r_{22}) \\)
   
2) \\(\beta =-90.0^\circ \\)인 경우\
   \\(\beta =-90.0^\circ \\)

   \\(\alpha =0.0\\)

   \\(\gamma =-Atan2(r_{12} , \ r_{22}) \\)

&nbsp;

## 2-2. \\(Atan2(y, \ x)\\) 함수를 사용하는 이유
\\(x=1\\), \\(y=1\\)인 경우와 \\(x=-1\\), \\(y=-1\\)인 경우가 있다.\
\\(Atan(\dfrac yx )\\)를 사용하면 두 경우에 대해 같은 값을 반환한다.\
이러한 문제를 해결하기 위해 \\(Atan2(y, \ x)\\) 함수를 사용한다.

&nbsp;

&nbsp;

&nbsp;

# 3. Equivalent Angle-axis Representation
\\(^A_B R_K (\theta)=\left[ \begin{matrix} r_{11} & r_{12} & r_{13} \cr r_{21} & r_{22} & r_{23} \cr r_{31} & r_{32} & r_{33} \end{matrix} \right] \\)라면 다음을 만족한다.

\\(\theta =Acos(\dfrac{r_{11} +r_{12}+r_{33} -1}2)

\\(\hat{K} =\dfrac 1{2sin\theta} \left[ \begin{matrix} r_{32} -r_{23} \cr r_{13} -r_{31} \cr r_{21} -r_{12} \end{matrix} \right] \\)
