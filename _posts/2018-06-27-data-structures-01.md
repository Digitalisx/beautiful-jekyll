---
layout: post
published: true
title: Data Structures 01
date: '2018-06-27'
subtitle: Data Structures and Algorithm
---
## A New Post

Data Structure & Algorithm

Data Structure -> 데이터의 표현과 저장 방식
Algorithm -> 저장된 데이터를 대상으로 하는 문제 해결 방식

Data Structure에 따라 사용 Algorithm이 달라지므로 상호 의존적임


Algorithm 성능 분석법

Time Complexity (시간 복잡도) - 수행 시간

Space Complexity (공간 복잡도) - 메모리 사용량

일반적으로는 Time Complexity를 통해서 우위를 비교한다.

데이터량 (n) -> 연산 횟수 T(n)

항상 좋은 알고리즘은 존재하지 않는다.
데이터의 수, 성능에 대한 민감성에 따라 적절히 사용해야한다.

Linear Search 예제

```C
#include <stdio.h> // 표준 입출력 헤더

int LSearch(int ar[], int len, int target) // LSearch 함수 Parameter 및 Return 값 설정
{
	int i;
	
	for(i = 0; i< len; i++) // 배열의 길이만큼 순회
	{
		if(ar[i] == target) // Target에 해당하는 원소 발견
		{
			return i; // 해당 위치 값 Return
		}
	}
	return -1; // 존재하지 않을 시, -1 Return
}

int main(void)
{
	int arr[] = {3,5,2,4,9}; // int형 배열 선언
	int idx;
	
	idx = LSearch(arr, sizeof(arr)/sizeof(int), 4);
  
  	// [int형 Array (4 Byte) * 5] / 4 Byte = 5
  	// 찾고자 하는 원소는 4
	
	if(idx == -1) // 함수 실행 결과 -1 Return시 Error
	{
		printf("탐색 실패!");
	}
	else
	{
		printf("타겟 저장 인덱스 : %d \n", idx);
      	// -1이 아니라면 Return 받은 위치 값 출력
	} 
	
	idx = LSearch(arr, sizeof(arr)/sizeof(int), 7);
  
  	// 위의 코드와 동일
	
	if(idx == -1)
	{
		printf("탐색 실패!");
	}
	else
	{
		printf("타켓 저장 인덱스 : %d \n", idx);
	}
	
	return 0;
  	// Main 함수 종료
}
```

Binary Search Algorithm

Condition - 사용 이전에 데이터들이 정렬되어 있어야 한다.


이전에 살펴본 Linear Search에 비해서 점점 탐색 범위를 줄여나가므로 좋은 성능을 보인다.

Worst Case -> T(n) = Log2^N (Logartihmetic)

![]({{site.baseurl}}/http://arturmeyster.com/content/images/2015/02/binary-search-1.jpeg)

```C
#include <stdio.h>

int BSearch(int ar[], int len, int target)
{
	int first = 0; // 배열의 초기 값 
	int last = len - 1; // 배열의 마지막 값
	int mid; // 배열의 중간 값
	
	while(first <= last) // Last가 First보다 크거나 같으면 반복
	{
		mid = (first + last) / 2; // 중간 값 구하기 (몫)
		
      	// 중간 값에 대한 3가지 조건 제시 - 일치, 대, 소
      
		if(target == ar[mid]) // 배열의 중간 값이 목표와 일치
		{
			return mid; // 위치 값 Return
		}
		else // 목표와 일치하지 않을 시
		{
			if(target < ar[mid]) // 중간 값이 목표보다 크게 되면
			{
				last = mid - 1; // 범위 줄이기 (중간보다 작은 값들을 대상, 왼쪽)
			}
			else // 중간 값이 목표보다 작게 되면
			{
				first = mid + 1; // 범위 줄이기 (중간보다 큰 값들을 대상, 오른쪽)
			}
        }
	}
  
  	// 순회 결과 Find 하지 못했다면 -1 값 Return
  	return -1;
}
```


Best Case - 
Worst Case -

Algorithm의 성능을 파악함에 있어 가장 중요한 것은 Worst Case이다.

Calculate Worst Case

맨 마지막에 있는 경우가 Worst Case가 될 수 있음 -> 데이터 7개에 7번 비교를 해야하므로
사실상 n

Calculate Average Case

Why use Worst Case?

일반적으로 Average Case는 구하는 과정이 어렵고, 정확한 결과를 구하기 어려움


Big O Notation

가장 영향력이 큰 부분만을 따지는 표기 법 (Approximation)

Question 아래의 Big O 들을 비교하라

3n + 2
7n^3 + 3n^2 + 2
2^n + n^2
n + logn
n + nlogn
2^n + n^3

축약해보면 아래와 같다.

3n, n^3, 2^n, logn, nlogn, 2^n

이를 비교하게 되면 다음과 같다.

2^n + n^3 = 2^n + n^2 > 7n^3 + 3n^2 + 2 > n + nlogn > n + logn > 3n + 2



Enter text in [Markdown](http://daringfireball.net/projects/markdown/). Use the toolbar above, or click the **?** button for formatting help.
