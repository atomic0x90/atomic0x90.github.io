---
layout: post
title:  "입력 함수(scanf)"
date:   2019-06-05 20:54:40
author: atomic0x90 (Yujun Han)
categories: C-Language
tags:  C-Language
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## 입력 함수(scanf)란?

프로그램 사용자로부터 입력을 받기 위한 함수이다.  
입력 함수는 키보드로부터 입력된 데이터를 지정된 형식으로 변환하여 변수에 저장하는 역할이다.

---

## 입력 함수(scanf)의 원형

```
int scanf (const char *format, ...);
```

---

## 입력 함수(scanf) 사용법

scanf도 printf와 마찬가지로 형식 지정자를 사용한다. 
형식 지정자를 모르거나 자세하게 알고 싶으면 [이곳][0]을 눌러 확인하자. 
**scanf와 printf의 형식 지정자가 다른 경우가 있다.** 바로 `%d` 와 `%i`이다.  
* `%d` : singed 10진수를 입력받음
* `%i` : 10진수/8진수/16진수를 입력받음


scanf와 printf의 사용법은 크게 다르지 않다.
**예시**를 통해 알아보자.

**첫 번째 예시**
```c
#include <stdio.h>
int main()
{
	int test1,test2,test3;

	printf("test1을 입력하세요 ! :");

	scanf("%i",&test1);		//17을 16진수로 표현하면 0x11이다.
	
	printf("test2를 입력하세요 ! :");

	scanf("%i",&test2);		//9를 8진수로 표현하면 011이다.

	printf("test3을 입력하세요 ! :");
	
	scanf("%d",&test3);

	printf("\ntest1의 값 : %d\n",test1);
	printf("test2의 값 : %d\n",test2);
	printf("test3의 값 : %d\n",test3);
	return 0;
}
```

**결과**

```bash
test1을 입력하세요 ! :0x11
test2를 입력하세요 ! :011
test3을 입력하세요 ! :011

test1의 값 : 17
test2의 값 : 9
test3의 값 : 11
```
첫 번째 인수인 **%i**는 형식 지정자로서 16진수, 8진수, 10진수의 데이터를 받을 것임을 알려준다.  
두 번째 인수인 **&test1**, **&test2**는 입력을 받을 변수의 주소를 나타낸다.  
첫 번째 인수인 **%d**는 형식 지정자로서 10진 정수형의 데이터를 받을 것임을 알려준다.  
두 번째 인수인 **&test3**은 입력을 받을 변수의 주소를 나타낸다.  
**%i**는 16진수, 8진수도 입력이 된다는 것을 알 수 있다.


**두 번째 예시**
```c
#include <stdio.h>
int main()
{
	int test;

	printf("정수를 입력하세요 ! :");

	scanf("%d", &test);

	printf("입력하신 정수는 %d입니다.\n",test);
	return 0;
}
```

**결과**

```bash
정수를 입력하세요 ! :144
입력하신 정수는 144입니다.
```
첫 번째 인수인 **%d**는 형식 지정자로서 10진 정수형의 데이터를 받을 것임을 알려준다.  
두 번째 인수인 **&test**는 입력을 받을 변수의 주소를 나타낸다.



scanf는 변수 앞에 `&`[앰퍼샌드(ampersand)][1] 기호가 있다. 
변수는 메모리에 생성된다. 따라서 변수는 주소를 가지고 있다. 
변수 앞에 `&`를 붙이면 변수의 주소를 의미한다.

---

## 입력 함수(scanf)에 &(ampersand)를 사용하는 이유

scanf에 &를 사용하는 이유를 알기 위해서는 메모리의 주소에 대해서 알아야 한다.  
예를 들어 **A**라는 변수를 생성해서 **A**의 주소가 **101**이라고 생각하자. 
그리고 **A**에 **10**이라는 값을 넣으면 다음과 같다.  

**주소 &nbsp;&nbsp;&nbsp;값**  
100 &nbsp;&nbsp;&nbsp;123  
**101 &nbsp;&nbsp;&nbsp;(쓰레기 값에서 ▶ 10으로 바뀜) ◀(변수 A의 주소)**  
102 &nbsp;&nbsp;&nbsp;2342  
103 &nbsp;&nbsp;&nbsp;9237  

이때 **A**의 값은 **10**이고 **&A**의 값은 **101**이다. 즉 `&[변수]`는 변수가 저장되어 있는 위치를 뜻한다.


다음으로 **scanf의 작동원리**를 알아보자. 

1. **사용자로부터 데이터를 입력받는다.**
1. **입력받은 값을 \*`레지스터`에 저장한다.**
1. **변수의 주소에 찾아간다.**
1. **변수의 주소가 가리키는 메모리에 레지스터의 값을 저장한다.**
1. **레지스터에 저장된 값을 삭제한다.**

\*[레지스터(register)][2] : 컴퓨터의 프로세서 내에서 데이터를 보관하는 기억 장소이다.

즉 scanf를 사용하기 위해서는 변수의 주소가 필요하다. 그러므로 변수 앞에 `&`를 사용해야 한다.


**감사합니다.**

---

### Related Posts

**[출력 함수와 형식 지정자(printf, format specifiers)][00]**

**[이스케이프 시퀀스(escape sequence)][01]**

**[변수와 자료형(variables, data types)][02]**

**[산술 연산자(arithmetic operator)][03]**

---


[\<\< 이전글][3]		|[홈으로 가기][4]	|[post 목록 보기][5]	|[다음글 \>\>][6]
------				|:------:		|:------:		|------:
**[printf 함수와 형식 지정자][3]**	|			|			|**[Github blog를 검색이 되게 설정하기][6]**



[0]: https://atomic0x90.github.io/c-language/2019/06/04/printf-format.html "형식 지정자"
[1]: https://ko.wikipedia.org/wiki/앰퍼샌드 "wikipedia"
[2]: https://ko.wikipedia.org/wiki/프로세서_레지스터 "wikipedia"
[3]: https://atomic0x90.github.io/c-language/2019/06/04/printf-format.html "출력 함수와 형식 지정자"
[4]: https://atomic0x90.github.io/ "home"
[5]: https://atomic0x90.github.io/posts/ "posts"
[6]: https://atomic0x90.github.io/jekyll/2019/06/06/Registration-github-blog-search.html "Github blog를 검색이 되게 설정하기"

[00]: https://atomic0x90.github.io/c-language/2019/06/04/printf-format.html "출력 함수와 형식 지정자"
[01]: https://atomic0x90.github.io/c-language/2019/05/28/C-Language-escape-sequence.html "escape sequence"
[02]: https://atomic0x90.github.io/c-language/2019/05/30/Variables-and-data-types.html "변수와 자료형"
[03]: https://atomic0x90.github.io/c-language/2019/06/13/arithmetic-operator.html "산술 연산자"



{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}










