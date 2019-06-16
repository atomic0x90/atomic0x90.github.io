---
layout: post
title:  "C언어 비교 연산자(comparative operator)"
date:   2019-06-14 20:37:16
author: atomic0x90 (Yujun Han)
categories: C-Language
tags:  C-Language
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## 비교 연산자(comparative operator)란?

연산자는 특정한 작업을 수행하기 위해서 사용하는 기호이다.  
그러므로 비교 연산자는 값을 비교하는 작업을 수행하기 위한 기호이다.

---

**[연산자와 피연산자(operator and operand)][0]** 의미 보러가기

---

## 비교 연산자

이 표에서 a, b는 유효한 변수값이다.

연산자 이름	|연산자		|사용법		|의미
:------:	|:------:	|:------:	|:------:
같음		|==		|a == b		|a와 b가 같음
다름		|!=		|a != b		|a와 b가 다름
큼		|>		|a > b		|a가 b보다 큼
작음		|<		|a < b		|a가 b보다 작음
크거나 같음	|>=		|a >= b		|a가 b보다 크거나 같음
작거나 같음	|<=		|a <= b		|a가 b보다 작거나 같음

**예시**

```c
#include <stdio.h>
int main()
{
        int a = 10, b = 10, c = 12;

        printf("a = 10, b = 10, c = 12\n");
        printf("a == b : %d\n",a == b);
        printf("a != b : %d\n",a != b);
        printf("a > b  : %d\n",a > b);
        printf("a < b  : %d\n",a < b);

        printf("a >= b : %d\n",a >= b);
        printf("a <= b : %d\n",a <= b);
        printf("a == c : %d\n",a == c);
        printf("a != c : %d\n",a != c);

        return 0;
}
```


**실행 결과**

논리식이 참일 경우에는 1이고 논리식이 거짓일 경우에는 0이다.

```bash
a = 10, b = 10, c = 12
a == b : 1
a != b : 0
a > b  : 0
a < b  : 0
a >= b : 1
a <= b : 1
a == c : 0
a != c : 1
```


**감사합니다.**

---

### Related Posts

**[출력 함수와 형식 지정자(printf, format specifiers)][4]**

**[입력 함수(scanf)][5]**

**[산술 연산자(arithmetic operator)][1]**

---



[\<\< 이전글][1]        |[홈으로 가기][2]       |[post 목록 보기][3]    |[다음글 \>\>][6]
------                  |:------:               |:------:               |------:
**[산술 연산자(arithmetic operator)][1]**   |                       |                       |**[논리 연산자(logical operator)][6]**



[0]: https://atomic0x90.github.io/c-language/2019/06/13/arithmetic-operator.html "operator and operand"
[1]: https://atomic0x90.github.io/c-language/2019/06/13/arithmetic-operator.html "산술 연산자"
[2]: https://atomic0x90.github.io/ "home"
[3]: https://atomic0x90.github.io/posts/ "posts"
[4]: https://atomic0x90.github.io/c-language/2019/06/04/printf-format.html "출력 함수와 형식 지정자"
[5]: https://atomic0x90.github.io/c-language/2019/06/05/scanf-format.html "입력 함수"
[6]: https://atomic0x90.github.io/c-language/2019/06/15/logical-operator.html "논리 연산자"







{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}










