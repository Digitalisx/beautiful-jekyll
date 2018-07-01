---
layout: post
published: true
title: Data Structures 03
subtitle: ADT (Abstract Data Type)
date: '2018-07-01'
---
## What is Abstract Data Type?

**Abstract**라는 단어가 붙은 여러 용어들을 설명함에 있어 많은 난해함이 존재한다. "추상"이라는 것이 모호하고 정확하게 표현할 수 없는 것이 일반적이기 때문이다. 대표적으로 학부 과정 중에서 Object Oriented Programming (OOP)를 수강할 때 등장한 JAVA의 Abstract Class, Method 같은 경우에는 필자를 혼란스럽게 하기에 충분하였다.

그런데 Data Structure에서도 Abstract라는 Keyword가 포함된 개념이 등장한다. 바로 Abstract Data Type이다. 한국어로는 "추상 자료형"으로 의미는 다음과 같다.

> 기능의 구체적인 구현 과정 을 보여주지 않고 기능에 대해서만 순수하게 나열한 것

의미를 읽어봐도 무언가 부족함을 느낄 것이다. 의미를 하나씩 분석 해보자.

먼저 일반적으로 알고 있는 자료형 (Data Type) 이라면 Integer, Double, Float, Char과 같이 어떠한 유형의 데이터인지를 식별하는 분류 방식/체계이다. 그런데 기능을 나열한다는 것이 자료형이라고 할 수 있을까?

C를 사용하면서 구조체를 통해서 사용자가 원하는 자료형을 정의 해본적이 있을 것이다. 그러나 Computer Engineering 측면에서는 단순히 구조체의 Member들을 정의 하는 것만으로 자료형을 정의했다고 할 수 없다. **Member에 대한 정의와 더불어 정의하고자 하는 자료형을 기반으로 하는 연산에 대해서도 내부에 정의가 되어야 비로소 자료형이 정의되었다고 할 수 있는 것이다.**

예를 들어 만약에 Wallet이라는 자료형을 정의하고자 하는데 내부에 Cost라는 Member만 정의 해서는 Wallet이라는 자료형을 목적에 맞게 사용할 수 없게 된다. 그러므로 활용을 위한 입금이나 출금 같이 여러 기능 (연산) 또한 정의해줘야 한다.

Object Oriented Programming를 수강했던 학생으로써 생각해본다면 OOP가 지향하는 Concept 중에서 **EnCapsulation** (캡슐화) 와 상당히 유사한 것으로 생각되고, 이러한 개념들에 대해서 미리 익숙해져 있어 ADT 역시 쉽게 이해 한 것 같다.

ADT로 많은 도움을 얻었던 사례 중 Python의 List가 존재하는데, append, remove, reverse 등의 List에 대한 ADT가 충분히 제공되었고, 그로 인해 List라는 Data Type을 비교적 쉽게 이용해왔던 것이라 생각된다.

## Why learn ADT in Data Structures?

잘 알려진 자료구조와 관련된 ADT를 숙지해야 실제로 자료구조를 효율적으로 적용하고 활용할 수 있기 때문이다. 이렇게 자료구조를 잘 활용할 수 있게 되면 그와 관련된 Algorithm 또한 효율적으로 활용할 수 있게 된다.
