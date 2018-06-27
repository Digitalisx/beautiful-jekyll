---
layout: post
published: true
title: Data Structures 02
subtitle: Recursion
date: '2018-06-28'
---
## Recursion

공부를 하다보면 자주 접하는 형태이지만, 본인은 실제 사용하는 코드에서는 잘 구현 해본적은 없는 형태가 "Recursion" 이다. 흔히들 "재귀함수"라고 하는데 **함수 내부에서 자기 자신을 다시 호출하는 경우**를 "재귀 함수"라고 한다.

논리적으로 함수가 완벽하게 정의되지 않은 상태에서 자기 자신을 호출한다는게 말이 안되 보일 수 있지만 Computer Architecture와 같은 과목들을 공부하다보면 그것이 어떻게 가능하게 되는지 알 수 있다. (BSA와 같은 명령어들)

하지만 해당 글에서는 Recursion을 구현하고 응용하는 것에 초점을 두기 때문에 추가적으로 설명하지는 않겠다.

## Recursion Example

```c
void Recursive(void)
{
  printf("Recursive Call!\n");
  Recursive();
}
```

해당 재귀함수가 어떻게 동작하는지 편하게 이해하기 위해서는 아래의 설명을 따르면 된다.
윤성우님의 자료구조 도서에 등장하는 내용으로
"Recursive 함수를 실행하는 중간에 다시 Recursive 함수가 호출되면, **Recursive 함수의 복사본**을 하나 더 만들어 복사본을 시행하게 된다"

이런 식으로 이해하는게 제일 쉬웠던 것 같다.

## Recursion Example 2

```c
#include <stdio.h>

void Recursive(int num)
{
  if(num <= 0) // num으로 0 이하의 값이 들어오면 멈춘다.
    return; // 함수의 종료
  printf("Recursive Call! : %d\n", num); // Argument 값 출력
  Recursive(num-1); // Argument의 1 감소한 값을 Recursive Function의 Argument 값으로 준다.
}

int main(void)
{
  Recursive(3); // Recursive 함수의 Argument 값으로 3을 부여한다.
  return 0; // 위 함수 실행이 끝나면 Main 함수를 종료한다.
}
```

앞서 설계한 코드와 달리 해당 예제에서는 조건문이 포함된다. 그 이유는 별다른 조건이 존재하지 않는 한 재귀함수는 그 특성상 무한히 자신을 호출하게 되고 결국 프로그램은 무한 루프 상태에 빠지게 된다.

해당 코드에서는 처음에 전달된 값 3이 재귀 함수를 통해 1씩 감소하며 전달되고, 전달된 값이 0에 다다르면 끝이 난다.

## Recursion Design Case

Factorial

Fibonacci Sequence

Binary Search Algorithm

The Tower of Hanoi


