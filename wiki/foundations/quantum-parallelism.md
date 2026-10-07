---
title: 양자 병렬성과 측정의 제약 (Quantum Parallelism)
type: concept
tags: [기초, 병렬성, 측정, 간섭]
status: seed
created: 2026-10-07
updated: 2026-10-07
related: [[superposition]], [[amplitude-and-phase]], [[takeda-first-quantum-computer-story]]
---

# 양자 병렬성과 측정의 제약

## 한 줄 요약
양자 연산은 중첩된 **모든 패턴에 한 번에 작용**한다. 그러나 측정하면 **패턴 하나만** 무작위로 얻는다. 쓸모 있는 답은 간섭으로 정답 패턴의 확률을 높여야만 얻을 수 있다.

## 직관
- 강점: 연산 한 번이 $2^n$개 패턴 전체에 적용된다(책: "중첩을 유지한 채로 동시에 실행").
- 제약: 마지막에 읽을 수 있는 것은 하나뿐이다(책: "결과는 한 가지 패턴뿐").
- 그래서 양자 알고리즘의 핵심은 "동시에 계산하기"가 아니다. **측정하기 전에 오답의 진폭은 상쇄시키고 정답의 진폭은 보강하도록 위상을 설계하는 것**이다.

## 수학적 정의
양자 연산(유니터리 $U$)은 **선형(linear)**이다.
$$U\Big(\sum_x c_x\lvert x\rangle\Big) = \sum_x c_x\, U\lvert x\rangle$$
함수 $f$를 계산하는 오라클 $U_f\lvert x\rangle\lvert0\rangle=\lvert x\rangle\lvert f(x)\rangle$에 균등 중첩을 넣으면 이렇게 된다.
$$U_f\Big(\tfrac{1}{\sqrt{2^n}}\sum_x\lvert x\rangle\lvert0\rangle\Big)=\tfrac{1}{\sqrt{2^n}}\sum_x\lvert x\rangle\lvert f(x)\rangle$$
모든 $f(x)$가 상태 안에 "들어 있다". 그러나 측정하면 무작위 $x$ 하나와 그 $f(x)$ 하나만 얻는다. 이것만으로는 고전적으로 $x$를 하나 골라 계산한 것과 다를 바 없다.

## 흔한 오해
- **"양자컴퓨터는 모든 경우를 동시에 계산해서 답을 다 알려준다"**: 위에서 본 것처럼 아니다. 책도 이 제약을 분명히 짚는다.
- **"그러니 모든 문제가 지수적으로 빨라진다"**: 아니다. 간섭으로 답을 끌어낼 수 있는 **구조**가 있는 문제(주기 찾기 → Shor, 비구조 탐색의 제곱근 가속 → Grover 등)에서만 이득이 있다.

## 열린 질문
- "전체 패턴의 **공통 성질**(예: 주기)은 측정 한 번으로 얻을 수 있다"는 아이디어가 Deutsch–Jozsa에서 구체적으로 어떻게 작동하는가? → 로드맵 3단계에서 확인

## 출처
- [[takeda-first-quantum-computer-story]]
