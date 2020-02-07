---
layout: post
title:  "C언어 대입 연산자(assignment operator), 복합 연산자(compound operator)"
date:   2020-02-06 20:01:16
author: atomic0x90 (Yujun Han)
categories: C-Language
tags:  C-Language
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## 대입 연산자(assignment operator)란?

대입 연산자는 변수에 값을 저장하는 연산자이다. `=` 기호가 바로 대입 연산자 이다.
`=`의 왼쪽은 반드시 변수이어야 하고 등호의 오른쪽은 모든 수식이 가능하다.

**예시**
```c
x = 10 + 20;
```
변수 x에 10 + 20 의 값이 대입 된다.


**잘못된 예시**
```c
10 = x;
```
`=`기호 왼쪽이 변수가 아니라서 오류가 발생한다.

---

## 복합 연산자(compound operator)란?

복합 연산자는 대입 연산자인 `=` 기호에 다른 연산자를 합쳐 놓은 연산자이다.

---

## 복합 연산자

이 표에서 a, b는 유효한 변수값이다.

복합 연산자	|의미
:------:	|:------:
a += b		|a = a + b
a -= b		|a = a - b
a \*= b		|a = a \* b
a /= b		|a = a / b
a %= b		|a = a % b

**예시**
```c
#include <stdio.h>
int main()
{
	int a = 10,b = 3;

	printf("a += b : %d\n",a += b);

	a = 10,b = 3;

	printf("a -= b : %d\n",a -= b);

	a = 10,b = 3;

	printf("a *= b : %d\n",a *= b);

	a = 10,b = 3;

	printf("a /= b : %d\n",a /= b);

	a = 10,b = 3;

	printf("a %= b : %d\n",a %= b);

	return 0;
}
```

**실행 결과**
```bash
a += b : 13
a -= b : 7
a *= b : 30
a /= b : 3
a %= b : 1
```


**감사합니다.**

---

### Related Posts

**[출력 함수와 형식 지정자(printf, format specifiers)][1]**

**[산술 연산자(arithmetic operator)][3]**

**[비교 연산자(comparative operator)][4]**

---

[\<\< 이전글][8]        |[홈으로 가기][6]       |[post 목록 보기][7]    |다음글 \>\>
------                  |:------:               |:------:               |------:
**[비트 연산자(bit operator)][8]**   |                       |                      	|


[1]: https://atomic0x90.github.io/c-language/2019/06/04/printf-format.html "출력 함수와 형식 지정자"
[3]: https://atomic0x90.github.io/c-language/2019/06/13/arithmetic-operator.html "산술 연산자"
[4]: https://atomic0x90.github.io/c-language/2019/06/14/comparative-operator.html "비교 연산자"
[6]: https://atomic0x90.github.io/ "home"
[7]: https://atomic0x90.github.io/posts/ "posts"
[8]: https://atomic0x90.github.io/c-language/2019/06/16/bit-operator.html "비트 연산자"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}

