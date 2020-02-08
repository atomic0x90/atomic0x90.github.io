---
layout: post
title:  "C언어 삼 항 연산자(ternary operator)"
date:   2019-06-18 13:04:44
author: atomic0x90 (Yujun Han)
categories: C-Language
tags:  C-Language
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## 삼 항 연산자(ternary operator)란?

삼 항 연산자는 세 개의 피연산자를 이용하여 계산하는 연산자이다. `?` 기호가 삼 항 연산자이다.

**예시**
```c
a = b ? c : d;
```
`b`의 조건이 `참(true)`이면 `a`에 `c`가 대입되고 `b`의 조건이 `거짓(false)`이면 `a`에 `d`가 대입된다.

**예시**
```c
#include <stdio.h>
int main()
{
	int a,b;

	b = 12;

	a = b == 12 ? 10 : 20;	//(b == 12)의 조건이 참이면 10 대입, 거짓이면 20 대입

	printf("a : %d\n",a);

	a = b > 12 ? 10 : 20;	//(b > 12)의 조건이 참이면 10 대입, 거짓이면 20 대입

	printf("a : %d\n",a);

	return 0;
}
```

**실행 결과**
```bash
a : 10
a : 20
```

**갑사합니다.**

---

### Related Posts

**[대입 연산자(assignment operator), 복합 연산자(compound operator)][2]**

**[논리 연산자(logical operator)][3]**

**[비교 연산자(comparative operator)][4]**

---

[\<\< 이전글][2]        |[홈으로 가기][6]       |[post 목록 보기][7]    |[다음글 \>\>][8]
------                  |:------:               |:------:               |------:
**[대입 연산자(assignment operator), 복합 연산자(compound operator)][2]**   |                       |			|**[연산자의 우선순위(operator priority, precedence)][8]**



[2]: https://atomic0x90.github.io/c-language/2019/06/17/assignment-operator.html "대입 연산자, 복합 연산자"
[3]: https://atomic0x90.github.io/c-language/2019/06/15/logical-operator.html "논리 연산자"
[4]: https://atomic0x90.github.io/c-language/2019/06/14/comparative-operator.html "비교 연산자"
[6]: https://atomic0x90.github.io/ "home"
[7]: https://atomic0x90.github.io/posts/ "posts"
[8]: https://atomic0x90.github.io/c-language/2020/02/07/operator-priority.html "연산자의 우선순위"





{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}
