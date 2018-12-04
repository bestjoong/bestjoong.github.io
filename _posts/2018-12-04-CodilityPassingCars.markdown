---
layout: post
title:  "[Codility][lesson5] PassingCars 문제풀이"
date:   2018-12-04 09:50:10 +0900
author: Hyunjoong Kim
categories: Algorithm
tags: Codility
---





**[문제]**

0 또는 1로만 이루어진 A배열이 주어진다.<br/>

0은 동쪽으로 여행하는 차를, 1은 서쪽으로 여행하는 차를 의미한다.<br/>

P가 동쪽으로 가는 여행하는 차, Q가 서쪽으로 여행하는 차일때,<br>

0 <= P < Q < N 인 한쌍의 자동차 P,Q의 짝의 수를 최종적으로 리턴하면 된다.<br>

```
A 배열이 아래와 같이 제공된다면,
A[0] = 0
A[1] = 1
A[2] = 0
A[3] = 1
A[4] = 1

P,Q의 짝은 아래와 같이 나온다.
(0, 1), (0, 3), (0, 4), (2, 3), (2, 4)

최종적으로 P,Q 짝의 수인 5를 리턴하면 된다.
```

단, 짝의 수가 1,000,000,000이 넘는다면 -1를 리턴해야한다.<br/>

<br/>

**[풀이]**

아래 두가지를 정의하니 답이 쉽게 정리가 되었는데,<br/>

```
1. 배열의 요소중 0이 먼저 나오면, 그 다음에 나오는 모든 1과 쌍을 이뤄야 한다.
2. 결국 최종적으로 짝이 되는 경우의 수만 구하면 된다.
```

<br/>

배열의 요소를 확인하면서, <br/>

1) 0이 1개 나오면, 다음 1이 나올때마다 1개씩 짝이 만들어 지는 것이고 <br/>

2) 그 다음에 0이 또 나오면 다음 1이 나올때마다 2개씩 짝이 만들어진다.<br/>

위의 과정을 반복하면 답이 나오는데, 짝의 수의 제한이 넘으면 -1을 리턴하게끔만 처리해주면 된다.<br/>

```
for (int i = 0; i < A.length ; i++){
    if (A[i]==0){
        zc++;
    }else if (A[i]==1){
        sum += zc;
    }

    if (sum > 1000000000){
        return -1;
    }
}
```



[문제](https://app.codility.com/programmers/lessons/5-prefix_sums/passing_cars/)

[풀이 Code](https://github.com/bestjoong/codility/blob/master/src/main/java/codility/lesson/lesson5/PassingCars.java)

