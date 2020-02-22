---
layout: post
title:  "C / C++ 함수 실행 시간 확인하는 방법"
date:   2020-02-11 10:10:00
author: atomic0x90 (Yujun Han)
categories: C-Language C++
tags:   C++
sitemap:
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## C / C++ 함수 실행 시간 확인하는 방법

1. `time.h`를 include 한다.
1. `clock_t` 자료형 변수(start_time)와 `double` 자료형 변수(end_time)를 생성한다.
1. 실행 시간 측정을 시작할 위치에서 clock_t 자료형 변수에 `clock()` 을 대입한다.
1. 실행 시간 측정을 종료할 위치에서 double 자료형 변수에 `clock()` 을 대입한다.
1. `(double)( (end_time - start_time) / (CLOCKS_PER_SEC) )` 을 출력한다.

**C 예시**
```c
#include <stdio.h>

#include <time.h>

clock_t start_t;
double end_t;

int main()
{
	start_t = clock();

	/*
		시간을 측정할 함수 또는 알고리즘
	*/

	end_t = clock();

	printf("%f\n",(double)((end_t - start_t) / CLOCKS_PER_SEC));

	return 0;
}
```


**C++ 예시**
```cpp
#include <iostream>

#include <time.h>

using namespace std;

clock_t start_t;
double end_t;

int main()
{
	start_t = clock();
	
	/*
		시간을 측정할 함수 또는 알고리즘
	*/

	end_t = clock();

	cout<<(double)((end_t - start_t) / CLOCKS_PER_SEC)<<endl;

	return 0;
}

```


**감사합니다.**

---


[홈으로 가기][01]       |[더 많은 C++ post 보기][03]            |[post 목록 보기][02]
:------:                |:------:                               |:------:
                        |                                       |


[01]: https://atomic0x90.github.io/ "home"
[02]: https://atomic0x90.github.io/posts/ "posts"
[03]: https://atomic0x90.github.io/posts/#C++ "C++ post"




{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}
                                                                                               




