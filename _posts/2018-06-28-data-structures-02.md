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

해당 재귀함수가 어떻게 동작하는지 편하게 이해하기 위해서는 아래의 설명을 따르면 된다. 윤성우님의 자료구조 도서에 등장하는 내용으로 "Recursive 함수를 실행하는 중간에 다시 Recursive 함수가 호출되면, **Recursive 함수의 복사본**을 하나 더 만들어 복사본을 시행하게 된다" 이런 식으로 이해하는게 제일 쉬웠던 것 같다.

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

### Factorial

```c
#include <stdio.h>

int Factorial(int num)
{
  if(num == 0) // num의 값으로 0이 들어오면
  {
    return 1; // 함수 종료 지점
  }
  else
  {
    return num * Factorial(num - 1) // 현재 num * Factorial(num - 1) 재귀 실행
  }
}

int main(void)
{
  prinf("9! = %d", Factorial(9)); // 9에 대한 Factorial 함수 실행
}
```

Factorial 함수의 Return 부분에 Factorail(num - 1)을 호출하고, (num == 0) 이라는 조건을 걸어 num이 1이 될때까지 재귀적으로 함수를 호출하게 된다.

### Fibonacci Sequence

```c
#include <stdio.h>

int Fibona(int num)
{
  if(num == 1) // 첫번째 값에 대한 정의
  {
    return 0;
  }
  else if(num == 2) // 두번째 값에 대한 정의
  {
    return 1;
  }
  else // 나머지 값은 이전의 값 2개를 기반으로 생성
  {
    return Fibona(n-1) + Fibona(n-2);
  }
}

int main(void)
{
  printf("%d", Fibona(5)); // 9번째 Fibonacci 수열
  return 0;
}
```
값을 Fibonacci 수열의 방식으로는 구할 수 없는 첫번째, 두번째 값에 대해서 사전적으로 정의를 해놓고 나머지 값에 대해서 첫번째, 두번째 값이 나올때까지 재귀 함수로 순회하는 방식이다. 해당 재귀 함수의 실행 과정은 다음과 같다.

Fibo(5) -> Fibo(4) + Fibo(3) -> Fibo(3) + Fibo(2) + Fibo(2) + Fibo(1) -> Fibo(2) + Fibo(1) + Fibo(2) + Fibo(2) + Fibo(1)

1 + 0 + 1 + 1 + 0 = 3 -> 0, 1, 1, 2, 3 = Correct!

### Binary Search Algorithm (Recursion Version)

```c
#include <stdio.h>

int BSearchRecur(int ar[], int first, int,second, int target) // 대상 배열, 시작 지점, 끝 지점, 대상
{
  int mid;
  if(first > last) // 탐색 실패 Case
  {
    return -1;
  }
  mid = (first + last) / 2; // 중간 값 찾기
  
  if(ar[mid] == target) // 중간 값과 대상 이리
  {
    return mid;
  }
  else if(target < ar[mid]) // 중간 값이 더 클 시
  {
    return BSearchRecur(ar, fisrt, mid - 1, target) // 중간 값 기준의 왼쪽 배열 대상으로 진행
  }
  else // 중간 값이 더 작을 시
  {
    return BSearchRecur(ar, fisrt, mid + 1, target) // 중간 값 기준의 오른쪽 배열 대상으로 진행
  }
}

int main(void)
{
  int arr[] = {1,3,5,7,9};
  int idx; // BSearchRecur 함수 실행 후 Return 값을 저장할 Index 변수
  
  idx = BSearchRecur(arr, sizeof(arr)/sizeof(int), 7);
  if(idx == -1)
  {
    printf("Failed!\n");
  }
  else
  {
    printf("타켓 저장 Index : %d \n", idx);
  }
  
  idx = BSearchRecur(arr, sizeof(arr)/sizeof(int), 4);
  if(idx == -1)
  {
    printf("Failed!\n");
  }
  else
  {
    printf("타겟 저장 Index : %d \n", idx);
  }
  
  return 0;
}
```
   
이전에 학습한 Binary Search Algorithm은 While을 통해서 구현이 되어 있었다. 그러나 Binary Search Algorithm 역시 **반복적인 Pattern의 행동이 포함**되어 있고 이에 대해 Recursion화 가능하였던 기존의 코드와 같이 구현이 가능하다. 기본적인 원리는 동일하지만 중간 값에 대한 판별 후 함수를 Recursion하게 Return 한다는 점에서 차이가 존재한다.
   

### The Tower of Hanoi




