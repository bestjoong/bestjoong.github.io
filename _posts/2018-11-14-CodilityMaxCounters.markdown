---
layout: post
title:  "[Codility][lesson4] MaxCounters 문제풀이"
date:   2018-11-14 09:34:30 +0900
author: Hyunjoong Kim
categories: Algorithm
tags: Codility
---





**[문제]**

1~N의 숫자요소를 가진 A[K]배열의 값을 순차적으로 추출하여,

0으로 채워진 N크기의 배열에 아래 두가지의 케이스를 적용한 N크기의 배열 리턴 

* 1 <= A[K] <= N 일 경우, N크기 배열의 A[K]의 위치 값 1 증가
* A[K] = N + 1 일 경우, N크기 배열의 최대값으로 모든 배열요소값 변경 

```
A 배열이 아래와 같이 제공되고, N = 5 일 경우,
A[0] = 3
A[1] = 4
A[2] = 4
A[3] = 6
A[4] = 1
A[5] = 4
A[6] = 4

아래와 같은 과정을 거쳐 배열의 최종 값을 리턴한다.
(0, 0, 1, 0, 0)
(0, 0, 1, 1, 0)
(0, 0, 1, 2, 0)
(2, 2, 2, 2, 2)
(3, 2, 2, 2, 2)
(3, 2, 2, 3, 2)
(3, 2, 2, 4, 2) << return!!
```



[풀이]

N크기의 배열을 counter[]로 정의1 <= A[K] <= N 인 경우,  

counter[A[K]]을 1증가시킨다.A[K] = N + 1 인 경우, counter[] 의 모든값을 최대값으로 변경해야하는데,

이때마다 전체값을 모두 변경하면 성능이 현저히 떨어진다. 

<br/>

그래서 아래와 같은 방법으로 문제를 해결하였다. 

<br/>

A[K] = N + 1 인 경우, 추가로 counter의 최대값을 저장만 한 후,

다음 A[K] 요소를 추출할때 counter[A[K]] 와 max값을 비교하여,

max값이 더 크면, counter[A[K]]에 max + 1을 저장,

counter[A[K]]값이 더 크면, counter[A[K]]++ 수행한다. 

마지막으로, max값으로 max값보다 작은 counter[]값들을 후처리해주면 된다.





[문제](https://app.codility.com/programmers/lessons/4-counting_elements/max_counters/)

[풀이 Code](https://github.com/bestjoong/codility/blob/master/src/main/java/codility/lesson/lesson4/MaxCounters.java)

