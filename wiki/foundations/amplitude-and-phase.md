---
title: 진폭의 비와 위상의 차이 (Amplitude & Phase)
type: concept
tags: [기초, 큐비트, 진폭, 위상, 간섭, 블로흐구]
status: seed
created: 2026-10-07
updated: 2026-10-07
related: [[superposition]], [[quantum-parallelism]], [[takeda-first-quantum-computer-story]]
---

# 진폭의 비와 위상의 차이

## 한 줄 요약
큐비트 1개의 중첩은 **두 실수 매개변수**로 완전히 정해진다. 하나는 **진폭의 비**로 측정 확률을 정하고, 다른 하나는 **상대 위상(relative phase)**으로 간섭의 방향을 정한다.

## 직관
책의 그림처럼 $\lvert0\rangle$과 $\lvert1\rangle$을 두 파동이라고 생각하면 이렇다.
- **진폭의 비**: 두 파동의 크기 비율. 측정했을 때 0과 1이 각각 얼마나 자주 나오는지를 정한다.
- **위상의 차이**: 두 파동의 마루가 서로 얼마나 어긋나 있는지. 이 값만으로는 측정 확률이 달라지지 않는다. 하지만 이후 게이트를 거쳐 경로들이 합쳐질 때 **보강 간섭할지 상쇄 간섭할지**를 정한다.

## 수학적 정의
상태 전체에 곱해지는 위상(전역 위상, global phase)은 관측할 수 없으므로 빼고 쓰면 이렇다.
$$\lvert\psi\rangle = \cos\tfrac{\theta}{2}\lvert0\rangle + e^{i\varphi}\sin\tfrac{\theta}{2}\lvert1\rangle$$
- $\theta$: 진폭의 비를 나타낸다. $P(0)=\cos^2\tfrac{\theta}{2}$, $P(1)=\sin^2\tfrac{\theta}{2}$이다. 측정 확률은 **진폭의 절댓값 제곱**(본 규칙, Born rule)이다.
- $\varphi$: 상대 위상, 곧 위상의 차이다.
- $(\theta,\varphi)$는 **블로흐 구(Bloch sphere)의 표면** 위 한 점에 대응한다. 책이 말하는 "진폭의 비와 위상의 차이로 중첩이 결정된다"는 바로 이 두 매개변수를 가리킨다.

## 예시: 위상만 다른 두 상태
$$\lvert+\rangle=\tfrac{1}{\sqrt2}(\lvert0\rangle+\lvert1\rangle),\qquad \lvert-\rangle=\tfrac{1}{\sqrt2}(\lvert0\rangle-\lvert1\rangle)$$
- 바로 측정하면 두 상태 모두 0과 1이 50%씩 나온다. 위상 차이는 측정 확률에 보이지 않는다.
- 하다마드(Hadamard) 게이트 $H$를 먼저 적용하면 결과가 갈린다.
$$H\lvert+\rangle = \tfrac12\big[(\lvert0\rangle+\lvert1\rangle) + (\lvert0\rangle-\lvert1\rangle)\big] = \lvert0\rangle$$
$$H\lvert-\rangle = \tfrac12\big[(\lvert0\rangle+\lvert1\rangle) - (\lvert0\rangle-\lvert1\rangle)\big] = \lvert1\rangle$$
  $\lvert+\rangle$에서는 $\lvert1\rangle$로 가는 두 경로가 상쇄되고 $\lvert0\rangle$으로 가는 경로가 보강된다. $\lvert-\rangle$에서는 그 반대다. **이것이 간섭(interference)이다.**

## 흔한 오해 (외부 AI 설명을 검토하며 바로잡은 것)
처음 메모할 때 참고한 AI 설명에는 대체로 맞는 내용이 많았지만, 다음 부분은 부정확했다.
1. **"위상이 같으면 보강 간섭, 반대면 상쇄 간섭" 하고 끝나는 설명**: 한 큐비트 안의 $\lvert0\rangle$ 성분과 $\lvert1\rangle$ 성분은 측정할 때 서로 간섭하지 않는다. 간섭은 **서로 다른 계산 경로가 같은 기저 상태로 모일 때** 그 기저 상태의 진폭끼리 일어난다(위 예시의 $H$).
2. **"블로흐 구라는 3차원 공간의 모든 점을 정보 단위로 활용"**: 순수 상태는 블로흐 구의 **표면**에만 있다. 구의 내부는 혼합 상태(mixed state)다.
3. **"그래서 고전 컴퓨터와 비교할 수 없는 병렬 처리 능력을 갖는다"**: 과장이다. 큐비트 1개에서 측정으로 얻을 수 있는 고전 정보는 최대 1비트다(홀레보 한계, Holevo bound). 성능은 간섭을 설계한 알고리즘이 있을 때만 나온다. → [[quantum-parallelism]]
4. **"위상 차 = 주기의 차이"**: 아니다. 주기(진동수)는 같고 **시작점이 어긋난 정도**가 위상 차다.

## 열린 질문
- 큐비트 n개에서는 상대 위상이 $2^n-1$개다. 이 위상들을 실제 알고리즘에서는 어떻게 "설계"하는가? (QFT, Grover에서 다시 보기)

## 출처
- [[takeda-first-quantum-computer-story]]
- Nielsen & Chuang, *Quantum Computation and Quantum Information* §1.2 (블로흐 구 표기)
