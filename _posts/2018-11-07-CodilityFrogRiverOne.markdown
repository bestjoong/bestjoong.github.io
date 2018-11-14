---
layout: post
title:  "[Codility][lesson4] FrogRiverOne 문제풀이"
date:   2018-11-07 11:44:30 +0900
author: Hyunjoong Kim
categories: Algorithm
tags: Codility
---





**[문제]**

개구리가 현재 위치(위치:0)에서 강 건너편의 위치(X+1)로 이동하기 위해서 가는 위치까지의 모든 지점에 나뭇잎이 떨어지는 가장 빠른 시간을 찾아내는 문제입니다.A배열에서 1,2,3,..,X 의 값들이 모두 발견되는 제일 빠른 A배열의 인덱스를 리턴해주면 된다.X까지의 나뭇잎 길이 열리지 않는다면, -1을 리턴해주면 된다. 

```
아래 예제와 같이 A배열이 배치되어있고 X가 5라면, 6을 리턴하면 된다.
  A [0] = 1
  A [1] = 3
  A [2] = 1
  A [3] = 4
  A [4] = 2
  A [5] = 3
  A [6] = 5
  A [7] = 4

아래 예제와 같이 A배열이 배치되어있고 X가 4라면, -1을 리턴한다.
  A [0] = 1
  A [1] = 3
  A [2] = 1
  A [3] = 4
  A [4] = 3
```



[풀이]

1) A배열을 처음부터 조회하며, 1 ~ X 범위에 있는 숫자를 발견되면 발견값을 저장한다.    

   첫 발견시, 증가량을 체크하는 변수를 ++ 해준다.

2) 증가량을 체크하는 변수가 X와 같아지는 순간의 A배열의 인덱스값을 리턴해준다.

3) A배열을 다 조회시에도 조건을 만족하지 못하면 -1을 리턴한다. 



[문제](https://app.codility.com/programmers/lessons/4-counting_elements/frog_river_one/)

[풀이 Code](https://github.com/bestjoong/codility/blob/master/src/main/java/codility/lesson/lesson4/FrogRiverOne.java)

