---
layout: post
title:  "C언어 비트 연산자(bit operator)"
date:   2019-06-16 23:40:01
author: atomic0x90 (Yujun Han)
categories: C-Language
tags:  C-Language
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## 비트 연산자(bit operator)란?

연산자는 특정한 작업을 수행하기 위해서 사용하는 기호이다. 
그러므로 비트 연산자는 이진수에 대해 비트 단위로 적용되는 연산이다.

---

**[연산자와 피연산자(operator and operand)][0]** 의미 보러가기

---

## 비트 연산자

이 표에서 a, b는 유효한 변수값이다.

연산자 이름	|연산자		|사용법		|의미
:------:	|:---:		|:---:		|:---:
NOT		|~		|~a
AND		|&		|a & b
OR		|\|		|a \| b
XOR		|^		|a ^ b
왼쪽 시프트	|<<		|a << b
오른쪽 시프트	|>>		|a >> b



**감사합니다.**


---

### Related Posts

**[산술 연산자(arithmetic operator)][4]**

**[비교 연산자(comparative operator)][5]**

**[논리 연산자(logical operator)][1]**

---



[\<\< 이전글][1]        |[홈으로 가기][2]       |[post 목록 보기][3]    |[다음글 \>\>][6]
------                  |:------:               |:------:               |------:
**[논리 연산자(logical operator)][1]**   |                       |                       |**[대입, 복합 연산자(assignment, compound operator)][6]**




[0]: https://atomic0x90.github.io/c-language/2019/06/13/arithmetic-operator.html "operator and operand"
[1]: https://atomic0x90.github.io/c-language/2019/06/15/logical-operator.html "논리 연산자"
[2]: https://atomic0x90.github.io/ "home"
[3]: https://atomic0x90.github.io/posts/ "posts"
[4]: https://atomic0x90.github.io/c-language/2019/06/13/arithmetic-operator.html "산술 연산자"
[5]: https://atomic0x90.github.io/c-language/2019/06/14/comparative-operator.html "비교 연산자"
[6]: https://atomic0x90.github.io/c-language/2019/06/17/assignment-operator.html "대입, 복합 연산자"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}






