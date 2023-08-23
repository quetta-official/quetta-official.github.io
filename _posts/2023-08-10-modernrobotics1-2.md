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
Grübler's Formula는 일반적인 경우에는 성립하지만 관절 제약조건이 독립적이지 않은 경우 성립하지 않는다.

&nbsp;

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

## 2-1. Example 1) Four-bar Linkage and Slider-crank Mechanism
![image](/assets/images/Fourbar_Linkage_and_Slidercrank_Mechanism.png)

&nbsp;

**(a) Four-bar Linkage(4절 링크)**\
\\(N=4\\) (지면 포함)\
\\(J=4\\)\
\\(m=3\\) (모든 링크가 평면 위에서 움직이도록 제한됨)\
\\(f_i =1\\) (각 관절의 자유도는 1)\
\\((자유도)=m(N-1-J)+\Sigma _{i=1} ^J f_i = 3(4-1-4)+\Sigma _{i=1} ^4 1 =-3+4=1\\)
> 자유도: \\(1\\)

&nbsp;

**(b) Slider-crank Mechanism**\
\\(N=4\\) (지면 포함)\
\\(J=4\\) (3개의 회전형 관절, 1개의 선형 관절)\
\\(m=3\\) (모든 링크가 평면 위에서 움직이도록 제한됨)\
\\(f_i =1\\) (각 관절의 자유도는 1)\
\\((자유도)=m(N-1-J)+\Sigma _{i=1} ^J f_i = 3(4-1-4)+\Sigma _{i=1} ^4 1 =-3+4=1\\)
> 자유도: \\(1\\)

&nbsp;

## 2-2. Example 2) Some Classical Planar Mechanisms
![image](/assets/images/Some_Classical_Mechanisms.png)

&nbsp;

**(a) k-Link Planar Serial Chain**\
\\(N=k+1\\) (\\(k\\)개 링크, 지면)\
\\(J=k\\)\
\\(m=3\\) (모든 링크가 평면 위에서 움직이도록 제한됨)\
\\(f_i =1\\) (각 관절의 자유도는 1)\
\\((자유도)=m(N-1-J)+\Sigma _{i=1} ^J f_i = 3((k+1)-1-k)+\Sigma _{i=1} ^k 1=0+k=k\\)
> 자유도: \\(k\\)

&nbsp;

**(b) Five-bar Planar linkage**\
\\(N=5\\) (지면은 1개로 취급)\
\\(J=5\\)\
\\(m=3\\) (모든 링크가 평면 위에서 움직이도록 제한됨)\
\\(f_i =1\\) (각 관절의 자유도는 1)\
\\((자유도)=m(N-1-J)+\Sigma _{i=1} ^J f_i = 3(5-1-5)+\Sigma _{i=1} ^5 1=-3+5=2\\)
> 자유도: \\(2\\)

&nbsp;

**(c) Stephenson Six-bar Linkage**\
\\(N=6\\) (지면은 1개로 취급)\
\\(J=7\\)\
\\(m=3\\) (모든 링크가 평면 위에서 움직이도록 제한됨)\
\\(f_i =1\\) (각 관절의 자유도는 1)\
\\((자유도)=m(N-1-J)+\Sigma _{i=1} ^J f_i = 3(6-1-7)+\Sigma _{i=1} ^7 1=-6+7=1\\)
> 자유도: \\(1\\)

&nbsp;

**(d) Watt Six-bar Linkage**\
\\(N=6\\) (지면은 1개로 취급)\
\\(J=7\\)\
\\(m=3\\) (모든 링크가 평면 위에서 움직이도록 제한됨)\
\\(f_i =1\\) (각 관절의 자유도는 1)\
\\((자유도)=m(N-1-J)+\Sigma _{i=1} ^J f_i = 3(6-1-7)+\Sigma _{i=1} ^7 1=-6+7=1\\)
> 자유도: \\(1\\)

&nbsp;

## 2-3. Example 3) A Planar Mechanism with Overlapping Joints
![image](/assets/images/MR_Figure2.6.png)

&nbsp;

이 예제는 큰 링크의 오른쪽 관절이 두 개의 링크와 동시에 연결되어 있는 경우이다.\
이러한 경우 해당 관절을 두 개의 관절이 겹쳐져 있는 것으로 해석해야 한다.

&nbsp;

\\(N=8\\) (겹쳐진 관절은 2개로 취급, 지면은 1개로 취급)\
\\(J=9\\)\
\\(m=3\\) (모든 링크가 평면 위에서 움직이도록 제한됨)\
\\(f_i =1\\) (각 관절의 자유도는 1)\
\\((자유도)=m(N-1-J)+\Sigma _{i=1} ^J f_i = 3(8-1-9)+\Sigma _{i=1} ^9 1=-6+9=3\\)
> 자유도: \\(3\\)

&nbsp;

## 2-4. Example 4) Redundant Constraints and Singularities
![image](/assets/images/MR_Figure2.7.png)

&nbsp;

**(a) A Parallelogram Linkage**\
\\(N=5\\) (지면은 1개로 취급)\
\\(J=6\\)\
\\(m=3\\) (모든 링크가 평면 위에서 움직이도록 제한됨)\
\\(f_i =1\\) (각 관절의 자유도는 1)\
\\((자유도)=m(N-1-J)+\Sigma _{i=1} ^J f_i = 3(5-1-6)+\Sigma _{i=1} ^6 1=-6+6=0\\)
> 자유도: \\(0\\)
 
&nbsp;

그러나 해당 메커니즘은 실제로 1 자유도를 가지고 있다.\
세 개의 평행한 링크 중 어떠한 링크를 제외해도 원래의 메커니즘의 운동에 영향을 끼치지 않는다.\
즉 해당 메커니즘의 제약조건이 독립적이지 않다.\
Grübler's Formula는 제약조건이 독립적이지 않을 때 성립하지 않아 이러한 문제가 발생한다.\
해당 메커니즘은 하나의 링크가 없다고 가정할 때 다음과 같이 분석될 수 있다.

&nbsp;

\\(N=4\\) (링크 1개 제외, 지면은 1개로 취급)\
\\(J=4\\) (링크 1개가 제외되어 해당 링크의 관절 2개가 제외됨)\
\\(m=3\\) (모든 링크가 평면 위에서 움직이도록 제한됨)\
\\(f_i =1\\) (각 관절의 자유도는 1)\
\\((자유도)=m(N-1-J)+\Sigma _{i=1} ^J f_i = 3(4-1-4)+\Sigma _{i=1} ^4 1=-3+4=1\\)
> 자유도: \\(1\\)

&nbsp;

**(b) The Five-bar Linkage in a Regular and Singular Configuration**\
\\(N=5\\) (지면은 1개로 취급)\
\\(J=5\\)\
\\(m=3\\) (모든 링크가 평면 위에서 움직이도록 제한됨)\
\\(f_i =1\\) (각 관절의 자유도는 1)\
\\((자유도)=m(N-1-J)+\Sigma _{i=1} ^J f_i = 3(5-1-5)+\Sigma _{i=1} ^5 1=-3+5=2\\)
> 자유도: \\(2\\)

&nbsp;

그러나 가운데 두 개의 링크의 길이가 같고, 서로 겹쳐질 수 있다면 이 링크들은 겹쳐진 관절에 대해 자유롭게 회전할 수 있다.\
즉 링크의 길이 조건에 따라 제약조건이 독립적이지 못하게 될 수도 있다.

&nbsp;

## 2-5. Delta Robot
![image](/assets/images/MR_Figure2.8.png)

&nbsp;

\\(N=17\\) (각 팔마다 5개의 링크, 위아래 2개의 삼각형 링크)\
\\(J=21\\) (Revolute Joint 9개, Spherical Joint 12개)\
\\(m=6\\) (모든 링크가 공간 위에서 움직임)\
\\(f_i =1\\) (Revolute Joint의 자유도는 1)\
\\(f_i =3\\) (Spherical Joint의 자유도는 3)\
\\((자유도)=m(N-1-J)+\Sigma _{i=1} ^J f_i = 6(17-1-21)+\Sigma _{i=1} ^9 1+\Sigma _{i=1} ^12 3=-30+9+36=15\\)
> 자유도: \\(15\\)

&nbsp;

## 2-6. Stewart-Gough Platform
![image](/assets/images/MR_Figure1.1.png)

&nbsp;

\\(N=14\\) (각 팔마다 2개의 링크, 위아래 2개의 원형 링크)\
\\(J=18\\) (Spherical Joint 6개, Prismatic Joint 6개, Universal Joint 6개)\
\\(m=6\\) (모든 링크가 공간 위에서 움직임)\
\\(f_i =1\\) (Prismatic Joint의 자유도는 1)\
\\(f_i =2\\) (Universal Joint의 자유도는 1)\
\\(f_i =3\\) (Spherical Joint의 자유도는 1)\
\\((자유도)=m(N-1-J)+\Sigma _{i=1} ^J f_i = 6(14-1-18)+\Sigma _{i=1} ^6 1+\Sigma _{i=1} ^6 2+\Sigma _{i=1} ^6 3=-30+6+12+18=6\\)
> 자유도: \\(6\\)
