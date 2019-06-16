---
layout: post
title:  "C언어 논리 연산자(logical operator)"
date:   2019-06-15 02:09:33
author: atomic0x90 (Yujun Han)
categories: C-Language
tags:  C-Language
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---


## 논리 연산자(logical operator)란?

연산자는 특정한 작업을 수행하기 위해서 사용하는 기호이다.  
그러므로 논리 연산자는 조건식이 논리 조건에 맞는지 확인하는 기호이다.

---

**[연산자와 피연산자(operator and operand)][0]** 의미 보러가기

---

## 논리 연산자

이 표에서 a, b는 유효한 변수값이다.

연산자 이름	|연산자		|사용법		|의미
:------:	|:------:	|:------:	|:-------:
논리적 부정(NOT)|!		|!a		|a가 참이면 거짓, 거짓이면 참
논리적 AND	|&&		|a && b		|a, b 모두 참이어야 참
논리적 OR	|\|\|		|a \|\| b	|a, b 하나라도 참이면 참

---

## 논리 회로

C 언어에서의 &&는 AND 게이트, \|\|는 OR 게이트, !은 NOT 게이트에 해당한다. 
이처럼 논리 연산자의 기본이 되는 논리 회로의 **AND 게이트**, **OR 게이트**, **NOT 게이트**의 
작동 원리(진리표)를 알면 논리 연산자가 이해가 된다.

* AND 게이트 진리표 

명제 P		|명제 Q		|P && Q
:------:	|:-------:	|:------:
참(1)		|참(1)		|참(1)
참(1)		|거짓(0)	|거짓(0)
거짓(0)		|참(1)		|거짓(0)
거짓(0)		|거짓(0)	|거짓(0)

AND 게이트는 명제가 모두 참이어야만 결과가 참이다. 
즉 AND 게이트는 명제 중에 한 가지라도 거짓이 있으면 결과가 거짓이다.

* OR 게이트 진리표

명제 P		|명제 Q		|P \|\| Q
:------:	|:------:	|:------:
참(1)		|참(1)		|참(1)
참(1)		|거짓(0)	|참(1)
거짓(0)		|참(1)		|참(1)
거짓(0)		|거짓(0)	|거짓(0)

OR 게이트는 명제가 한 가지라도 참이면 결과가 참이다. 
즉 OR 게이트는 명제가 모두 거짓이어야만 결과가 거짓이다.

* NOT 게이트 진리표

명제 P		|!P
:------:	|:------:
참(1)		|거짓(0)
거짓(0)		|참(1)

NOT 게이트의 결과는 명제의 반대 값이다.

---

**예시**

```c
#include <stdio.h>
int main()
{
        int a = 1, b = 0;

        printf("a = 1, b = 0\n\n");

        printf("a && a : %d\n",a && a);
        printf("a && b : %d\n",a && b);
        printf("b && a : %d\n",b && a);
        printf("b && b : %d\n\n",b && b);

        printf("a || a : %d\n",a || a);
        printf("a || b : %d\n",a || b);
        printf("b || a : %d\n",b || a);
        printf("b || b : %d\n\n",b || b);

        printf("!a : %d\n",!a);
        printf("!b : %d\n",!b);
        return 0;
}
```

**실행 결과**

```bash
a = 1, b = 0

a && a : 1
a && b : 0
b && a : 0
b && b : 0

a || a : 1
a || b : 1
b || a : 1
b || b : 0

!a : 0
!b : 1
```










[0]: https://atomic0x90.github.io/c-language/2019/06/13/arithmetic-operator.html "operator and operand"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}
