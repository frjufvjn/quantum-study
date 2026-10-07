---
title: 중첩 (Superposition)
type: concept
tags: [기초, 큐비트, 중첩]
status: seed
created: 2026-10-07
updated: 2026-10-07
related: [[amplitude-and-phase]], [[quantum-parallelism]], [[takeda-first-quantum-computer-story]]
---

# 중첩 (Superposition)

## 한 줄 요약
양자비트(qubit)는 0이나 1 중 하나만 갖는 것이 아니라, $\lvert0\rangle$과 $\lvert1\rangle$을 **일정한 비율과 위상으로 섞은 상태**를 가질 수 있다.

## 직관
- 고전 비트는 스위치처럼 항상 0 또는 1 가운데 하나다.
- 큐비트는 두 기저 상태(basis state)를 "얼마만큼씩, 어떤 위상으로" 섞을지까지 상태로 갖는다. 책에서는 이것을 **두 파동의 합성**으로 그린다.
- 큐비트가 n개이면 $00\cdots0$부터 $11\cdots1$까지 $2^n$개 패턴이 전부 중첩될 수 있다.

## 수학적 정의
큐비트 1개:
$$\lvert\psi\rangle = \alpha\lvert0\rangle + \beta\lvert1\rangle,\qquad \alpha,\beta\in\mathbb{C},\quad |\alpha|^2+|\beta|^2=1$$

큐비트 n개:
$$\lvert\psi\rangle = \sum_{x\in\{0,1\}^n} c_x\lvert x\rangle,\qquad \sum_x |c_x|^2 = 1$$

이 상태를 고전적으로 기록하려면 복소수 $2^n$개가 필요하다. 큐비트가 50개만 되어도 약 $10^{15}$개다.

## 예시
- $\lvert+\rangle = \tfrac{1}{\sqrt2}(\lvert0\rangle+\lvert1\rangle)$: 측정하면 0과 1이 각각 50% 확률로 나온다.
- 큐비트 2개를 균등하게 중첩하면 $\tfrac12(\lvert00\rangle+\lvert01\rangle+\lvert10\rangle+\lvert11\rangle)$이다. 4개 패턴이 각각 25% 확률로 나온다.

## 흔한 오해
- **"중첩 = 0인지 1인지 아직 모를 뿐이다(확률적 혼합)"**: 아니다. 동전 던지기처럼 단순히 "모르는" 상태라면 간섭이 일어나지 않는다. 중첩에는 **위상**이 있어서 간섭을 일으킨다. → [[amplitude-and-phase]]
- **"$2^n$개 정보를 저장했으니 $2^n$개를 꺼낼 수 있다"**: 아니다. 측정하면 하나의 패턴만 얻는다. → [[quantum-parallelism]]

## 열린 질문
- 측정할 때 중첩이 하나의 결과로 "붕괴"하는 것을 물리적으로 어떻게 이해해야 하나? (해석 문제 → [[open-questions]])

## 출처
- [[takeda-first-quantum-computer-story]]
