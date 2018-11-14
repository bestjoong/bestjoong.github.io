---
layout: post
title:  "[Codility][lesson3] TapeEqulibrium 문제풀이"
date:   2018-10-23 16:26:30 +0900
author: Hyunjoong Kim
categories: Algorithm
tags: Codility
---





**[문제]**

크기가 N인 A 배열의 P번째 순서까지의 합과 나머지 합 사이의 차이가 제일 작은 숫자를 찾아내는 문제이다. 아래 예시에서는 두 합 사이의 차이가 제일 작은 숫자인 1이 정답이다.

```
For example, consider array A such that:  //N = 5   
A[0] = 3  
A[1] = 1  
A[2] = 2  
A[3] = 4 
A[4] = 3 

We can split this tape in four places:
P = 1, difference = |3 − 10| = 7
P = 2, difference = |4 − 9| = 5
P = 3, difference = |6 − 7| = 1
P = 4, difference = |10 − 3| = 7  
```

<br/>

**[풀이]**

1) P까지의 합과 P이후의 값을 계산하기 위해 SUM 값을 먼저 구하였다.

2) 배열 2개를 만들어 B배열에는 P까지의 합, C배열에는 sum - B[i]으로 P이후의 값을 계산하여 setting 하였다.

3) 2)의 연산을 수행하면서, C[i] - B[i]를 계산하여 temp값을 세팅하고 이전의 minimum값과 비교하여 최소값을 계산하였다. 

<br/>

**[삽질..]**

2)의 개념을 코드로 구현하며 minimun값을 계산할때 P의 경계를 N-1까지 증가시키며 비교했어야했는데

N번째까지 루프를 돌며 계산하는 바람에

sum값이 P=N-1일때의 차이값보다 적을 경우

sum값이 minimum값으로 세팅되어 잘못된 값이 나왔었다.

<br/>

[문제](https://app.codility.com/programmers/lessons/3-time_complexity/tape_equilibrium/)

[풀이 Code](https://github.com/bestjoong/codility/blob/master/src/main/java/codility/lesson/lesson3/TapeEquilibrium.java)

