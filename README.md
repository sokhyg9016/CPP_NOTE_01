# C++ Primer Plus (6th Edition)

> C++의 특징, 인스턴스, 자료형(~C++17), 참조자와 포인터, R-value, 클래스 

> Reference: <a href="https://isocpp.org/" target="_blank">`https://isocpp.org/`</a>

> 2019.12.12


## **CONTENTS**
- C++의 첫걸음 <a href="#c의-첫걸음"><sup>[1]</sup></a>
  - C++의 특징들에 대하여 <a href="#cpp의-프로그래밍-철학"><sup>[1:2]</sup></a><a href="#이-외의-OOP의-장점"><sup>[1:4]</sup></a>
  - C++ 표준
- C++ 시작하기
  - C++ 전처리기와 `iostream` 파일
  - 헤더 파일 이름
  - 이름 공간
  - 함수
- 데이터 처리

---

This site was built using [GitHub Pages](https://pages.github.com/).

## C++의 첫걸음

- C와 C++언어의 역사와 철학 <a href="#c와-c언어의-역사와-철학"><sup>[1]</sup></a>
  - C의 프로그래밍 철학 <a href="#c의-프로그래밍-철학"><sup>[1:1]</sup></a>
  - C++의 프로그래밍 철학 <a href="#cpp의-프로그래밍-철학"><sup>[1:2]</sup></a>
  - 절차적 프로그래밍과 객체 지향 프로그래밍 <a href="#cpp의-프로그래밍-철학"><sup>[1:3]</sup></a>
  - 객체 지향 프로그래밍의 장점 <a href="#이-외의-OOP의-장점"><sup>[1:4]</sup></a>
- C++가 C언어에 추가한 일반화 지향 개념 <a href="#Cpp와-일반화-프로그래밍"><sup>[2]</sup></a>
- **`프로그래밍 언어의 표준`**
- 프로그램 작성 요령
- **`C++의 특징`**


---


C와 C++언어의 역사와 철학
---

일반적으로 컴퓨터 언어는 ***데이터***와 ***알고리즘***이라는 두가지 개념을 다룬다.

- 데이터(data): 프로그램이 사용하고 처리하는 정보
- 알고리즘(algorithm): 프로그램이 데이터를 처리하는 방법

<h4 id = "C_sec">C의 프로그래밍 철학</h4>

- `C`는 절차적(procedural)언어이다.
```   
  절차적이라는 말은 프로그래밍에서 데이터보다 알고리즘을 더 치중한다는 뜻이다. 
```
- 절차적 프로그래밍은 컴퓨터가 수행해야 할 동작들을 명확히 구분하고, 그 구분된 동작들을 프로그래밍 언어로 구현하는 것이다.
- 원하는 결과를 얻기 위해 컴퓨터가 따라야 할 절차들을 규정해 놓은 것이 `절차적 프로그램`이다.

#### 하향식(top-down)설계: 

```
- 구조적 프로그래밍이 고수하는 또 하나의 철학 
- 규모가 큰 프로그램을 작고 쉽게 다룰 수 있는 최소한의 단위로 더욱 잘게 쪼개는 것 
- 전체 프로그램이 프로그래밍하기 쉬운 작은 모듈들의 집합이 될 때까지 계속해서 쪼개 나간다. 
```

<h4 id = "Cpp_sec">Cpp의 프로그래밍 철학</h4>

- 구조적 프로그래밍 철학이 프로그램의 간결성과 신뢰성, 유지 보수의 용이성에 많은 향상을 가져온 것은 사실이나, 규모가 큰 프로그래밍은 여전히 어려운 문제로 남아 있었다. 
- 이 문제의 해결책으로 **객체 지향 프로그래밍** 철학이 등장함.

| 절차적 프로그래밍 | 객체 지향 프로그래밍 |
| --- | --- |
| `알고리즘` 강조 | `데이터` 강조 |

- 객체 지향 프로그래밍은 해결해야 할 문제를 언어의 절차적 접근 방식에 억지로 끼워 맞추지 않고, 언어 자체를 해결해야 할 문제에 맞춘다.
- **`해결해야 할 문제의 특성에 맞게 데이터형 자체를 설계한다.`**

- C++에서는 `클래스(Class)`가 그와 같은 목저그로 설계되는 새로운 데이터형이다.
- `객체(object)`는 그러한 클래스에 의해 만들어지는 특정한 데이터 구조이다.

#### 상향식(bottom-up)설계

```
- 저수준의 클래스를 먼저 설계한 후에 고수준의 프로그램 설계로 진행하는 것 
- 객체 지향적으로 프로그램을 설계하라면 프로그램이 다루는 객체를 정확하게 서술하는 클래스를 먼저 설계해야 한다. 
- 각 클래스에 해당하는 객체를 만들면서 프로그램 설계를 진행하는 것을 상향식(bottom-up)프로그래밍이라 한다.
```

<h4 id = "Oop_sec">이 외의 OOP의 장점</h4>

- OOP는 재활용이 가능한 소스 코드를 쉽게 작성할 수 있다. -> 프로그래밍 수고를 덜 수 있음.

***정보 은닉***
```
정보를 은닉할 수 있기 때문에 비인가된 접근으로부터 데이터를 안전하게 보호할 수 있음.
```

***다형성(polymorphism)***
```
다형성(polymorphism)을 이용하여 이름이 같은 연산자와 함수를 여러 벌 정의할 수 있기 때문에 상황에 따라 적당한 연산자나 함수를 프로그램이 스스로 선택하게 할 수 있다.
```

***상속(inheritance)***
```
상속을 이용하여 하나의 클래스로부터 새로운 클래스를 유도하는 등 절차적 프로그래밍과는 완전히 다른 접근 방식을 취할 수 있음.
```

---

Cpp와 일반화 프로그래밍
---

What things you need to install the software and how to install them

