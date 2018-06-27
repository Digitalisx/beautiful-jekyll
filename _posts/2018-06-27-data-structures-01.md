---
layout: post
published: true
title: Data Structures 01
date: '2018-06-27'
subtitle: Data Structures and Algorithm
---
## Data Structure & Algorithm

**Data Structure** : 데이터의 표현과 저장 방식  
**Algorithm** : 저장된 데이터를 대상으로 하는 문제 해결 방식

수 많은 데이터를 더 타당하고 합리적으로 저장하고 처리하기 위해서 알아야 하는 학문  
Data Structure에 따라 사용 Algorithm이 달라지므로 둘은 상호 의존적임  

  
## Algorithm 성능 분석법

**Time Complexity (시간 복잡도)** - 수행 시간 
**Space Complexity (공간 복잡도)** - 메모리 사용량  

일반적으로는 **Time Complexity**를 통해서 우위를 비교한다. (대게 속도에 관심이 많기 때문이다.)

데이터량 (n)과 연산 횟수 T(n) 를 통해서 각 Algorithm의 수행 속도를 비교할 수 있다.  

항상 좋거나 절대적인 알고리즘은 존재하지 않는다. 데이터의 수, 성능에 대한 민감성에 따라 적절히 사용해야한다.


## Linear Search

일반적으로 가장 많이 사용해왔던 원소 탐색 방법으로 배열의 처음부터 끝까지 값을 비교한다.  
필자는 대부분 많은 데이터들을 List에 넣어서 처리해왔고, 원하는 값을 찾거나 List 원소의 검증을 시행할 때 해당 방법을 많이 사용했던 것으로 기억한다.  

## Linear Search 예제

```c
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

  
## Binary Search

위에서 설명한 Linear Search랑 동일한 용도로 원소를 찾기 위해 만들어진 Algorithm이다.  
다만 해당 Algorithm을 사용하기 이전에 대상 데이터들이 **오름차순으로 정렬**되어 있어야 한다.  

배열의 양 끝 위치 값을 통해서 중간 값을 찾고, 이를 기준으로 범위를 줄여나가며 값을 탐색하는 Algorithm이다.
이전에 살펴본 Linear Search에 비해서 점점 탐색 범위를 줄여나가므로 **비교적 좋은 성능**을 보인다.

```c
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

## Best Case & Worst Case

**Best Case** - 해당 Algorithm에서 Time Complexity가 가장 효율적인 경우   
**Best Case** - 해당 Algorithm에서 Time Complexity가 가장 비효율적인 경우  

Algorithm의 성능을 파악함에 있어 가장 중요한 것은 **Worst Case**이다.


## Why use Worst Case?

일반적으로 생각하기에는 Average Case가 해당 Algorithm을 표현하고 비교하기에 가장 적절하다고 생각된다.
그러나 Average Case는 구하는 과정이 어렵고, 다양한 데이터와 시나리오가 적용되어야 하므로 정확한 결과를 구하기 어려움

## Calculate Worst Case

Linear Search의 Worst Case, Linear한 Data Structure에서 마지막에 목표 값이 존재할 때 (배열의 Length만큼 다 순회해야함)

**T(n) = n**

Binary Search의 Worst Case, 검색 범위를 줄여나감에 있어 결국 마지막 하나가 남을 때까지 범위를 줄이게 되는 경우

**T(n) = log 2^n**

실제로 이를 비교한 Graph는 아래의 그림과 같다.




## Big O Notation

가장 영향력이 큰 부분만을 따지는 표기 법 (Approximation)  

T(n) = n^2 + 2n + 9라고 주어졌을 때 Big O of n^2이라 할 수 있다.

## Question

아래의 Big O 들을 비교하라

- 3n + 2
- 7n^3 + 3n^2 + 2
- 2^n + n^2
- n + logn
- n + nlogn
- 2^n + n^3

축약해보면 아래와 같다.

3n, n^3, 2^n, logn, nlogn, 2^n

이를 비교하게 되면 다음과 같다.

2^n + n^3 = 2^n + n^2 > 7n^3 + 3n^2 + 2 > n + nlogn > n + logn > 3n + 2
