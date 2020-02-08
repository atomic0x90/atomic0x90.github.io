---
layout: post
title:	"C언어 연산자의 우선순위"
date:	2020-02-07 12:12:16
author:	atomic0x90 (Yujun Han)
categories: C-Language
tags:	C-Language
sitemap:
  changefreq : daily
  priority : 1.0
cover:	"/assets/instacode.png"
---

## 연산자의 우선순위(operator priority, precedence)란?

연산자의 우선순위란 많은 연산들 중에서 어떤 연산을 먼저 실행할지를 결정하는 순서이다.
우선순위가 1순위에 가까울수록 다른 연산들 보다 먼저 계산한다.

[연산자와 피연산자 보러가기][00]

---

## 우선순위 표

우선순위	|연산자					|우선순위가 같은 경우에 식을 계산하는 방법
:------:	|:------:				|:------:
1		|( ) [ ] -> .				|왼쪽에서 오른쪽으로(From left to right)
2		|sizeof &(주소) ++(전위) - -(전위) ~ ! \*(역참조) +(부호) -(부호) 형번환	|오른쪽에서 왼쪽으로(From right to left)
3		|\*(곱셈) / %				|왼쪽에서 오른쪽으로(From left to right)
4		|+(덧셈) -(뺄셈)			|왼쪽에서 오른쪽으로(From left to right)
5		|<< >>					|왼쪽에서 오른쪽으로(From left to right)
6		|< > <= >=				|왼쪽에서 오른쪽으로(From left to right)
7		|== !=					|왼쪽에서 오른쪽으로(From left to right)
8		|&(비트연산)				|왼쪽에서 오른쪽으로(From left to right)
9		|^					|왼쪽에서 오른쪽으로(From left to right)
10		|\|					|왼쪽에서 오른쪽으로(From left to right)
11		|&&					|왼쪽에서 오른쪽으로(From left to right)
12		|\|\|					|왼쪽에서 오른쪽으로(From left to right)
13		|?(삼 항 연산자)			|오른쪽에서 왼쪽으로(From right to left)
14		|=  +=  -=  \*=  /=  %=  &=  ^=  \|=  <<=  >>=	|오른쪽에서 왼쪽으로(From right to left)
15		|,(Comma)				|왼쪽에서 오른쪽으로(From left to right)


---

**예시**
```c
#include <stdio.h>
int main()
{
        int a,b,c,d;

        b = 12;

        a = - ++b;	// -(부호)와 ++(전위)는 우선순위가 같으므로 오른쪽에서 왼쪽으로 계산

        printf("a : %d, b : %d\n",a,b);

        b = 5,c = 10,d = 12;

        a = (b < c) ? c * b + c : c * d;
	//'(',')'가 우선순위가 빠르므로 'b < c' 계산
	//'c * b + c'에서 '*'이 '+'(덧셈) 보다 우선순위가 빠르므로 'c * b' 계산 후 '+ c' 계산
	//'c * d' 계산
	//'?'(삼 항 연산자) 우선순위가 제일 느리므로 마지막에 계산

        printf("a : %d\n",a);

	a = (b < c) ? c * (b + c) : c * d;
	//'(',')'가 우선순위가 빠르므로 'b < c' 계산
	//'c * (b + c)'에서 '(',')'가 우선순위가 빠르므로 'b + c' 계산 후 'c *' 계산
	//'c * d' 계산
	//'?'(삼 항 연산자) 우선순위가 제일 느리므로 마지막에 계산

	printf("a : %d\n",a);

	return 0;
}
```

**실행 결과**
```bash
a : -13, b : 13
a : 60
a : 150
```



**감사합니다.**

---

### Related Posts

**[산술 연산자(arithmetic operator), 연산자와 피연산자(operator, operand)][00]**

**[논리 연산자(logical operator)][1]**

**[대입 연산자(assignment operator), 복합 연산자(compound operator)][2]**

---

[\<\< 이전글][01]        |[홈으로 가기][10]       |[post 목록 보기][11]    |다음글 \>\>
------                  |:------:               |:------:               |------:
**[삼 항 연산자(ternary operator)][01]**   |                       |                          |


[00]: https://atomic0x90.github.io/c-language/2019/06/13/arithmetic-operator.html "산술 연산자, 연산자와 피연산자"
[01]: https://atomic0x90.github.io/c-language/2019/06/18/ternary-operator.html "삼 항 연산자"
[10]: https://atomic0x90.github.io/ "home"
[11]: https://atomic0x90.github.io/posts/ "posts"

[1]: https://atomic0x90.github.io/c-language/2019/06/15/logical-operator.html "논리 연산자"
[2]: https://atomic0x90.github.io/c-language/2019/06/17/assignment-operator.html "대입 연산자, 복합 연산자"









{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}
