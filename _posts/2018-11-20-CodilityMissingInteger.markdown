---
layout: post
title:  "[Codility][lesson4] MissingInteger 문제풀이"
date:   2018-11-20 09:15:10 +0900
author: Hyunjoong Kim
categories: Algorithm
tags: Codility
---





**[문제]**

N개의 정수를 가진 A배열이 주어진다.</br>

이 A배열에서 발생하지 앟는 가장 작은 양의 정수(0보다 큼)를 반환한다. 

```
A 배열이 아래와 같이 제공될 경우, 5를 리턴한다.
A[0] = 1
A[1] = 3
A[2] = 6
A[3] = 4
A[4] = 1
A[5] = 2

A 배열이 아래와 같이 제공될 경우, 1을 리턴한다.
A[0] = -1
A[1] = -3
```



**[풀이]**

A배열이 모두 양수일 경우에, </br>

최소 1 ~ N 의 숫자 중에 가장 작은 양수값을 가지고 있을거라고 생각했다.</br>



0) 그래서 count를 할수 있는 N크기의 배열 B 를 만들었다. </br>

1) A배열의 요소가 1보다 작을 경우 카운트를 세지 않고, </br>

​    1 ~ N 범위의 양의 수를 가질때만 배열B 에 체크하였다.</br>

2) 배열B의 가장 작은 위치부터 값이 비어있는지 체크하여 결과값을 리턴하였다. </br>



[문제](https://app.codility.com/programmers/lessons/4-counting_elements/missing_integer/)

[풀이 Code](https://github.com/bestjoong/codility/blob/master/src/main/java/codility/lesson/lesson4/MissingInteger.java)

