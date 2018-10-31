---
layout: post
title:  "[Codility][lesson4] PermCheck 문제풀이"
date:   2018-10-31 11:26:30 +0900
author: Hyunjoong Kim
categories: Algorithm
tags: Codility
---





**[문제]**

크기가 N인 A 배열안에 1-N 까지의 순열이 무작위로 배치되어있고, 이 A 배열안에 순열의 요소들이 제대로 배치되어있는지 확인하는 문제이다. 

```
아래 예제와 같이 순열의 요소가 제대로 배치되어있으면, 1을 리턴하면 된다.
    A[0] = 4
    A[1] = 1
    A[2] = 3
    A[3] = 2

아래 예제와 같이 순열의 요소가 제대로 구성되어있지 않을 경우, 0을 리턴하면 된다.
    A[0] = 4
    A[1] = 1
    A[2] = 3
```



**[풀이]**

1) A배열의 크기에 따라 순열 마지막 수가 정해진다는 것을 이용하여, B배열을 만들어 순열의 구성요소 위치에 발견 여부를 저장하였다.    

​    ex) A[3] = 4 => B[4-1] = 1 (수 발견시, 해당 위치 -1의 배열 위치에 1을 저장)

2) A배열에서 숫자 추출시, 이미 발견된 숫자가 발견되거나 배열의 크기보다 큰 숫자 발견시 0을 리턴하였다.

3) A배열의 모든 숫자 추출하고 2)의 케이스에 해당되지 않는 경우, 1을 리턴하였다. 



**[삽질..]**

A배열의 크기만큼의 순열의 합과 A배열 구성요소의 합을 비교하여 같으면 1을 리턴하면 되지 않을까?   

- 합은 같으나, 구성요소 중 중복된 숫자의 조합으로 합만 같은 경우가 생길 수 있었음 => FAIL        

  ex) A[5] = {1,1,4,4,5} => 15 = 15  



[문제](https://app.codility.com/programmers/lessons/4-counting_elements/perm_check/)

[풀이 Code](https://github.com/bestjoong/codility/blob/master/src/main/java/codility/lesson/lesson4/PermCheck.java)

