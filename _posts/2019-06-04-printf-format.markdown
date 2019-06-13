---
layout: post
title:  "출력 함수(printf)와 형식 지정자(format specifiers)"
date:   2019-06-04 14:54:01
author: atomic0x90 (Yujun Han)
categories: C-Language
tags:  C-Language
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## 출력 함수(printf)란?

화면에 무언가를 출력하기 위한 함수이다. 
출력 함수는 프로그램 사용하는 사람이 무엇을 해야 하는지 알려주는 역할이다.
정수, 실수, 문자, 문자열 등의 데이터를 다양한 형태로 화면에 출력할 수 있다.

---

## 출력 함수(printf)의 원형

```
int printf (const char *format, ...);
```

---

## 형식 지정자(format specifiers)란?

데이터들은 각자 다른 형태로 존재한다. 이러한 다양한 데이터들을 화면에 출력하기 위해서 각각 형식 지정자들이 있다. 
데이터에 알맞지 않은 형태의 형식 지정자를 사용하면 오류가 발생한다.

---

## 형식 지정자의 종류
---

## 정수형

형식 지정자	|의미				|예시				|실행 결과
:------:	|:------:			|:------:			|:------:
%d, %i		|10진 정수			|printf("%d %i",-20,12);	|-20 12
%u		|양의 10진 정수			|printf("%u",12);		|12
%o		|양의 8진 정수			|printf("%o",19);		|23
%x		|양의 16진 정수(소문자)		|printf("%x",14);		|e
%X		|양의 16진 정수(대문자)		|printf("%X",14);		|E
%lu		|unsigned long			|printf("%lu",100);		|100
%ld		|signed long			|printf("%ld",1000);		|1000
%llu		|unsigned long long		|printf("%llu",144);		|144
%lld		|signed long long		|printf("%lld",169);		|169

---

## 실수형

형식 지정자	|의미					|예시				|실행 결과
:------:	|:------:				|:------:			|:------:
%f		|실수의 소수점 표현(소문자,float)	|printf("%f",1.2);		|1.200000
%F		|실수의 소수점 표현(대문자,float)	|printf("%f",1.2);		|1.200000
%e		|실수의 지수 표현법(소문자,float)	|printf("%e",1.2);		|1.200000e+00
%E		|실수의 지수 표현법(대문자,float)	|printf("%E",1.2);		|1.200000E+00
%g		|%f 와 %e 중에서 짧은 것을 표현(소문자)	|printf("%g",1,2);		|1.2
%G		|%F 와 %E 중에서 짧은 것을 표현(대문자)	|printf("%G",1.2);		|1.2
%a		|실수를 16진법으로 표현(소문자)		|printf("%a",1.2);		|0x1.3333333333333p+0
%A		|실수를 16진법으로 표현(대문자)		|printf("%A",1.2);		|0X1.3333333333333P+0
%lf		|실수의 소수점 표현(소문자,double)	|printf("%lf",1.2);		|1.200000
%lF		|실수의 소수점 표현(대문자,double)	|printf("%lF",1.2);		|1.200000
%le		|실수의 지수 표현법(소문자,double)	|printf("%le",1.2);		|1.200000e+00
%lE		|실수의 지수 표현법(대문자,double)	|printf("%lE",1.2);		|1.200000E+00


---

## 문자형

형식 지정자	|의미			|예시				|실행 결과
:------:	|:------:		|:-------:			|:------:
%c		|문자			|printf("%c",'A');		|A
%s		|문자열			|printf("%s","Test String");	|Test String

---

## 포인터


형식 지정자	|의미
:------:	|:------:
%p		|포인터의 메모리 주소


**예시**
```c
#include <stdio.h>
int main()
{
	int test;
	void *ptr = &test;

	printf("%p\n",ptr);

	return 0;
}

```
**결과**
```bash
0x7ffcecb336ac
```

---

## % 기호

%를 출력하고 싶을 때
```c
printf("%");
```
이렇게 하면 좋지 않은 방식이다.  
따라서 다음과 같이 사용한다.



**올바른 예시**
```c
#include <stdio.h>
int main()
{
	printf("%%\n");
	return 0;
}
```

**결과**
```bash
%
```

---

## 형식 지정자 문법

```
% [매개 변수] [플래그] [너비] [.정밀도] [길이] 형식 지정자 유형
```

---

## 형식 지정자 문법 사용하기

**사용 예시**
```c
#include <stdio.h>
int main()
{
	printf("↓ 1칸 공백\n");
	printf("%4d\n",144);	//%d의 출력 넓이를 4로 지정, 남는 공간을 공백으로 채움
	printf("%5d\n",144);	//%d의 출력 넓이를 5로 지정, 남는 공간을 공백으로 채움
	printf("↑ 2칸 공백\n\n");
	
	printf("%04d\n",144);	//%d의 출력 넓이를 4로 지정, 남는 공간에 공백이 아닌 0으로 채움
	printf("%05d\n\n",144);	//%d의 출력 넓이를 5로 지정, 남는 공간에 공백이 아닌 0으로 채움

	printf("% d\n",144);	//양수일 때는 부호를 표시하지 않고 공백으로 표시
	printf("% d\n\n",-144);	//음수일 때는 부호를 표시

	printf("%+d\n",144);	//양수일 때는 +부호를 표시
	printf("%+d\n\n",-144);	//음수일 때는 -부호를 표시

	printf("%.2f\n",1.2);	//소수 둘째 자리 까지 표시
	printf("%.2e\n\n",1.2);	//소수 둘째 자리 까지 표시, 지수도 표현

	printf("%010.3f\n",1.2);//출력 넓이 10, 소수 3째 자리까지 표시, 남는 공간을 0으로 채움
	printf("%010.3e\n\n",1.2);//출력 넓이 10, 소수 3째 자리까지 표시, 남는 공간을 0으로 채움, 지수도 표현

	printf("%#o\n",19);	//8진수면 앞에 0을 표시함
	printf("%#x\n",15);	//16진수 소문자 출력, 앞에 0x를 표시함
	printf("%#X\n\n",0xa1);	//16진수 대문자 출력, 앞에 0X를 표시함

	printf("↓ 4칸 공백\n");
	printf("%5c\n",'S');	//출력 넓이를 5로 지정, 남는 공간을 공백으로 채움
	printf("%5s\n","Test");	//출력 넓이를 5로 지정, 남는 공간을 공백으로 채움
	printf("↑ 1칸 공백\n");

	return 0;
}
```


**실행 결과**
```bash
↓ 1칸 공백
 144
  144
↑ 2칸 공백

0144
00144

 144
-144

+144
-144

1.20
1.20e+00

000001.200
01.200e+00

023
0xf
0XA1

↓ 4칸 공백
    S
 Test
↑ 1칸 공백
```



**감사합니다.**

---

### Related Posts

**[입력 함수(scanf)][00]**

**[변수와 자료형(variables, data types)][01]**

**[이스케이프 시퀀스(escape sequence)][02]**

**[ASCII 코드][03]**

**[산술 연산자(arithmetic operator)][04]**

---


[\<\< 이전글][0]	|[홈으로 가기][1]       |[post 목록 보기][2]    |[다음글 \>\>][3]
------        	  	|:------:               |:------:               |------:
**[변수와 자료형][0]** 	|                       |                       |**[scanf 함수][3]**



[0]: https://atomic0x90.github.io/c-language/2019/05/30/Variables-and-data-types.html "변수와 자료형"
[1]: https://atomic0x90.github.io/ "home"
[2]: https://atomic0x90.github.io/posts/ "posts"
[3]: https://atomic0x90.github.io/c-language/2019/06/05/scanf-format.html "입력 함수"

[00]: https://atomic0x90.github.io/c-language/2019/06/05/scanf-format.html "입력 함수"
[01]: https://atomic0x90.github.io/c-language/2019/05/30/Variables-and-data-types.html "변수와 자료형"
[02]: https://atomic0x90.github.io/c-language/2019/05/28/C-Language-escape-sequence.html "escape sequence"
[03]: https://atomic0x90.github.io/c-language/2019/05/29/ASCII.html "ASCII code"
[04]: https://atomic0x90.github.io/c-language/2019/06/13/arithmetic-operator.html "산술 연산자"



{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}
