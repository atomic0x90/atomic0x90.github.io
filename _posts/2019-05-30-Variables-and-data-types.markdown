---
layout: post
title:  "C / C++ 변수(variables)와 자료형(data types)"
date:   2019-05-30 20:59:16
author: atomic0x90 (Yujun Han)
categories: C-Language C++
tags:  C-Language C++
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## 변수(variables)란?

컴퓨터의 메모리 안에 만들어지는 공간이다. 문자나 숫자를 저장하는 공간이다.

---

## 자료형(data types)이란?

데이터가 문자인지 정수인지 실수인지를 지정하는 것이다. 즉 데이터의 종류가 자료형이다.

---

변수
===
---

## 변수의 이름 짓는 법

변수의 이름은 **식별자(identifier)**의 일종이므로 몇 가지의 규칙을 지켜야 한다.  
* 변수는 영문자와 숫자, 밑줄 문자(`_`, underscore)로 이루어진다.
* 변수의 중간에 공백이 들어가면 안 된다.
* 대문자와 소문자는 구별된다.
* 변수의 첫 글자는 반드시 영문자 또는 밑줄 문자(`_`)이어야 한다.
* C 언어의 예약어와 똑같은 식별자는 사용하면 안 된다.

**사용 가능한 변수명 예시**
```c
Test		//영문자로 시작
_under_score	//밑줄 문자로 시작, 중간에 밑줄 문자 사용
atomic0x90	//첫 번째 글자가 아닌곳에 숫자 사용
```

**사용 불가능한 변수명 예시**
```c
0x90atomic	//숫자로 시작하면 안 된다.
C Language	//중간에 공백이 들어가면 안 된다.
temp#		//밑줄 문자 이외의 특수문자는 사용하면 안 된다.
if		//C 언어의 예약어는 사용하면 안 된다.
```

---

## 변수의 초깃값

일반적으로 변수가 생성되면 아무런 의미가 없는 값이 들어간다. 이것을 **쓰레기 값(garbage value)**라 한다.  
변수를 선언하면서 동시에 초기화할 수도 있다. 이것을 **변수의 초기화(initialization)**라고 한다.  
변수에 값을 저장하려면 다음과 같이 한다.  
```c
int value = 10;	//value라는 변수를 선언함과 동시에 값을 10으로 초기화 한 것이다.
value = 12;	//value라는 변수에 값을 12로 대입한 것이다.
```

---

자료형
===
---

## 기본형

자료형		|비트수		|범위
:------:	|:------:	|:------:
void		|\-		|\-


---

## 정수형

자료형		|비트수		|범위
:------:	|:------:	|:------:
bool		|8		|0 ~ 1
short		|16		|-32,768 ~ 32,767
int		|32		|-2,147,483,648 ~ 2,147,483,647
long		|32		|-2,147,483,648 ~ 2,147,483,647
long long	|64		|-9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807

---

## 문자형

자료형		|비트수		|범위
:------:	|:------:	|:------:
char		|8		|-128 ~ 127


---

## 실수형

자료형		|비트수		|범위
:------:	|:------:	|:------:
float		|32		|3.4E-38(-3.4\*10^38) ~ 3.4E+38(3.4\*10^38) (7digits)
double		|64		|1.79E-308(-1.79\*10^308) ~ 1.79E+308(1.79\*10^308) (15digits)

---

## unsigned 형태란?

위에서 봤듯이 자료형에는 범위가 존재한다. 이 범위는 음수, 0, 양수가 모두 존재한다. 
자료형을 사용하지만 음수는 사용하지 않을 때 unsigned를 사용하여 원래 자료형의 음수 범위만큼 양수의 범위를 늘려준다.

자료형		|비트수		|범위
:------:	|:------:	|:------:
unsigned char	|8		|0 ~ 255
unsigned short	|16		|0 ~ 65,535
unsigned int	|32		|0 ~ 4,294,967,295
unsigned long	|32		|0 ~ 4,294,967,295




---

## 변수와 자료형 사용법

`[자료형] [변수이름];`

**예시**
```c
int test;		//자료형 : int, 변수이름 : test
double _Yujun_Han;	//자료형 : double, 변수이름 : _Yujun_Han
char atomic0x90;	//자료형 : char, 변수이름 : atomic0x90
```





**감사합니다.**

---

### Related Posts

**[출력 함수와 형식 지정자(printf, format specifiers)][00]**

**[입력 함수(scanf)][01]**

**[이스케이프 시퀀스 정리(escape sequence)][02]**

---




[\<\< 이전글][0]|[홈으로 가기][1]       |[post 목록 보기][2]    |[다음글 \>\>][3]
------          |:------:               |:------:               |------:
**[ASCII 코드][0]**	|			|			|**[출력 함수와 형식 지정자][3]**



[0]: https://atomic0x90.github.io/c-language/2019/05/29/ASCII.html "ASCII 코드"
[1]: https://atomic0x90.github.io/ "home"
[2]: https://atomic0x90.github.io/posts/ "posts"
[3]: https://atomic0x90.github.io/c-language/2019/06/04/printf-format.html "출력 함수와 형식 지정자"

[00]: https://atomic0x90.github.io/c-language/2019/06/04/printf-format.html "출력 함수와 형식 지정자"
[01]: https://atomic0x90.github.io/c-language/2019/06/05/scanf-format.html "입력 함수"
[02]: https://atomic0x90.github.io/c-language/2019/05/28/C-Language-escape-sequence.html "이스케이프 시퀀스 정리"


{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}

















