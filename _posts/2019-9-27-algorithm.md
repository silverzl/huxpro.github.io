---
layout:     post
title:      "算法记录1"
subtitle:   "算法分析"
date:       2019-09-23 10:00:00
author:     "zl"
header-img: "img/post-bg-2019.jpg"
tags:
    - Life
---

## 1 循环设计要点 例题2-1

编写算法找出1000以内的所有完数。    
如：28的因子为1，2，4，7，14，而28=1+2+4+7+14.因此28是“完数“。编写算法找出1000以内的所有完数，并按下面格式输入出其因子:
>28 it’s factors are 1,2,4,7,14.

问题分析：  
1，这里不是要质因数。   
2，每个因数只记一次。

```
#include <stdio.h>

int main(){
	int sum;
	int a[100];             //首先通过循环分解因子
	for(int n=1;n<=1000;n++){   //1到100每个数进行判断
		sum=0;
		for(int i=1;i<=n/2;i++){		
			if(n%i==0){				
					sum=sum+i; 	//  将每个因数进行累加	
                    }
		}		

		if(n==sum){		
		printf("\n%d是完数",n);
		for(int i=1;i<=n/2;i++){			
			if(n%i==0){
				printf("%d,",i);					
			}			
		}		
		}
	} 
}
```
 

## 例题2-2

对于不太熟悉的问题，其不变不易抽象；
例如，编写算法，根据参数n打印具有下面规律的图形，例：当n=4时，图形如下：

1   
5 2     
8 6 3       
10 9 7 4



> 分析：    
> 11 22 33 44 nn  
> 21 32 43 n(n-1)   
> 31 42 n(n-2)

>按此规律数字一次累加
 
```
#include<stdio.h>

int main(){
	int i,j,a[100][100],n,k;
	scanf("%d",&n);
	k=1;
	for(i=1;i<=n;i++)       //写入数组
	for(j=1;j<=n+1-i;j++){
		a[i-1+j][j]=k;
		k++;

	}
	for(i=1;i<=n;i++){      //将数组打印
		printf("\n");
		for(j=1;j<=i;j++)
		printf("%d ",a[i][j]);
	}
	printf("\n");
}
```

