---
layout: post
title:  "[Codility][lesson3] FrogJmp 문제풀이"
date:   2018-10-20 14:26:30
author: Hyunjoong Kim
categories: Algorithm
tags: Codility
---



X와 Y의 사이의 거리를 D의 몇배수로 지나칠수 있는지를 알아내는 문제로 파악하였다.

D의 배수로 바로 Y까지 도달할 수 있는 케이스와 지나치는 케이스가 있어서,

(Y-X)/D 가 0인 케이스와 0보다 큰 케이스로 나누어 접근하여 문제를 해결하였다. 



[GitHub Code](https://github.com/bestjoong/codility/blob/master/src/main/java/codility/lesson/lesson3/FrogJmp.java)

