---
layout: post
title:  "C언어 산술 연산자(arithmetic operator), 연산자와 피연산자(operator, operand)"
date:   2019-06-13 19:00:01
author: atomic0x90 (Yujun Han)
categories: C-Language
tags:  C-Language
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## 산술 연산자(arithmetic operator)란?

연산자는 특정한 작업을 수행하기 위해서 사용하는 기호이다.  
그러므로 산술 연산자는 산술 작업을 수행하기 위한 기호이다.

---

## 연산자와 피연산자(operator and operand)란?

**예시**  
```c
sum = x + y;
```
변수 x에 들어있는 값과 변수 y에 들어있는 값을 더해서 변수 sum에 대입한다는 의미이다.  
여기서 `+`가 **연산자(operator)**이고 `x`, `y`는 **피연산자(operand)**이다.


---

## 산술 연산자

이 표에서 a, b는 유효한 변수값이다.

연산자 이름	|연산자		|사용법		|의미
:------:	|:------:	|:------:	|:-------:
대입 연산	|=		|a = b		|b의 값을 a에 대입
덧셈		|+		|a + b		|a와 b를 더함
뺄셈		|-		|a - b		|a에 b를 뺌
부호 표시	|+,-		|+a, -a		|a의 부호 표시
곱셈		|\*		|a \* b		|a와 b를 곱함
나눗셈		|/		|a / b		|a에 b를 나눈 몫
나머지		|%		|a % b		|a에 b를 나눈 나머지 값
단항 증가(전위)	|++		|++a		|▼아래에 설명▼
단항 증가(후위)	|++		|a++		|▼아래에 설명▼
단항 감소(전위)	|- -		|- -a		|▼아래에 설명▼
단항 감소(후위)	|- -		|a- -		|▼아래에 설명▼

**예시**
```c
#include <stdio.h>
int main()
{
	int a = 10,b = 3;
	
	printf("덧셈 : %d\n",a+b);	//덧셈

	printf("뺄셈 : %d\n",a-b);	//뺄셈

	printf("곱셈 : %d\n",a*b);	//곱셈

	printf("나눗셈 : %d\n",a/b);	//나눗셈

	printf("나머지 : %d\n",a%b);	//나머지

	a = b;		//대입

	printf("대입 : %d\n",a);

	printf("부호 표시 : %d\n",+a);	//부호 표시

	printf("부호 표시 : %d\n",-a);	//부호 표시
	return 0;
}
```

**실행 결과**
```bash
덧셈 : 13
뺄셈 : 7
곱셈 : 30
나눗셈 : 3
나머지 : 1
대입 : 3
부호 표시 : 3
부호 표시 : -3
```
---

## 단항 연산자

단항 연산자에는 전위와 후위가 있다. 사용법은 매우 비슷하지만 의미는 전혀 다르다.  
* **전위 단항 연산자의 의미**  
먼저 피연산자의 값을 증가하거나 감소하고 다른 연산에 사용한다.
* **후위 단항 연산자의 의미**  
먼저 피연산자의 값을 다른 연산에 사용하고 값을 증가하거나 감소한다.

**예시**
```c
#include <stdio.h>
int main()
{
	int a = 10;
	
	printf("%d\n",a);

	printf("%d\n",++a);		//전위 증가 연산자

	printf("%d\n",a++);		//후위 증가 연산자

	printf("현재 a의 값 : %d\n",a);

	printf("%d\n",a--);		//후위 감소 연산자

	printf("%d\n",--a);		//전위 감소 연산자

	printf("현재 a의 값 : %d\n",a);

	return 0;
}
```

**실행 결과**
```bash
10
11
11
현재 a의 값 : 12
12
10
현재 a의 값 : 10
```



**감사합니다.**

---

### Related Posts

**[연산자의 우선순위(operator priority, precedence)][00]**

**[출력 함수와 형식 지정자(printf, format specifiers)][3]**

**[입력 함수(scanf)][4]**

**[비교 연산자(comparative operator)][5]**

**[논리 연산자(logical operator)][6]**

---


[\<\< 이전글][0]        |[홈으로 가기][1]       |[post 목록 보기][2]    |[다음글 \>\>][5]
------                  |:------:               |:------:               |------:
**[Ubuntu image editor][0]**   |                       |                       |**[비교 연산자(comparative operator)][5]**


[0]: https://atomic0x90.github.io/ubuntu/2019/06/09/ubuntu-image-editor.html "Ubuntu에서 이미지 편집기 사용하기"
[1]: https://atomic0x90.github.io/ "home"
[2]: https://atomic0x90.github.io/posts/ "posts"
[3]: https://atomic0x90.github.io/c-language/2019/06/04/printf-format.html "출력 함수와 형식 지정자"
[4]: https://atomic0x90.github.io/c-language/2019/06/05/scanf-format.html "입력 함수"
[5]: https://atomic0x90.github.io/c-language/2019/06/14/comparative-operator.html "비교 연산자"
[6]: https://atomic0x90.github.io/c-language/2019/06/15/logical-operator.html "논리 연산자"

[00]: https://atomic0x90.github.io/c-language/2020/02/07/operator-priority.html "연산자의 우선순위"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}





