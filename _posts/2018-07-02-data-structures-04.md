---
layout: post
published: true
title: Data Structures 04
date: '2018-07-02'
subtitle: Linear List based on Array
---
## A New Post

```c
#include <stdio.h>
#include "ArrayList.h"

int main(void)
{
  List list;
  int data;
  ListInit(&list);
  
  LInsert(&list, 11);
  LInsert(&list, 11);
  LInsert(&list, 22);
  LInsert(&list, 22);
  LInsert(&list, 33);
  
  printf("Current Data : %d \n", LCount(&list));
  
  if(LFirst(&list, &data))
  {
    printf("%d ", data);
    
    while(LNext(&list, &data))
      printf("%d " data);
  }
  printf("\n\n");
  
  if(LFirst(&list, &data)
  {
    if(data == 22)
    {
    	LRemove(&list);
    }
    
    while(LNext(&list, &data))
    {
      if(data == 22)
      {
        LRemove(&list);
      }
    }
  }
  
  if(LFirst(&list, &data))
  {
    printf("%d ", data);
    
    while(LNext(&list, &data))
    {
      printf("%d", data);
    }
  }
     
  printf("\n\n");
  return 0;
}
```     



Enter text in [Markdown](http://daringfireball.net/projects/markdown/). Use the toolbar above, or click the **?** button for formatting help.
