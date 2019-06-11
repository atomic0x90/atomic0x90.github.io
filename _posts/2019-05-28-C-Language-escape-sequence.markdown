---
layout: post
title: "이스케이프 시퀀스(escape sequence) 정리"
date: 2019-05-28 23:06:57
author: atomic0x90 (Yujun Han)
categories: C-Language
tags: C-Language
sitemap :
  changefreq : daily
  priority : 1.0
cover: "/assets/instacode.png"
---

## 이스케이프 시퀀스란?

프로그래밍 언어 특성상 표현할 수 없는 기능, 문자를 표현해준다.  
컴퓨터를 제어하는 목적으로 사용되는 특수한 문자이다.  
제어 시퀀스(control sequence), 이스케이프 문자, 확장 비트열 이라고도 한다.  
`\`와 `₩`는 같은 의미이다.

---

이스케이프 시퀀스 | 의미
:------:|:------:
\a	|경고(alert)
\n	|줄바꿈(new line)
\t	|수평 탭(horizontal tab)
\v	|수직 탭(vertical tab)
\b	|백스페이스(backspace)
\f	|폼 피드(form feed)
\r	|캐리지 리턴(carriage return)
\\\	|백슬래시( \\, backslash)
\\'	|작음따옴표( ', single quotes)
\\"	|큰따옴표( ", double quotes)
\\ooo	|8진수 숫자를 사용하여 ASCII 코드의 문자 표현
\\xhh	|16진수 숫자를 사용하여 ASCII 코드의 문자 표현

## 이스케이프 시퀀스 설명

* `\a` (경고 문자)  
\a는 기본적으로 들을 수 있는 경보 소리를 낸다. 일부 시스템에서는 아무런 효과를 내지 않는다.

* `\n`, `\t`, `\v`, `\b`, `\f`, `\r` (출력 장치 제어 문자)
  * \n : 현재 활성 위치를 다음 줄의 시작 위치로 옮김(키보드의 enter 기능과 동일)
  * \t : 현재 활성 위치를 수평 탭의 다음 위치로 옮김(키보드의 tab 기능과 동일)
  * \v : 현재 활성 위치를 수직 탭의 다음 위치로 옮김
  * \b : 현재 활성 위치의 라인에서 활성 위치를 한 스페이스 뒤로 옮김(키보드의 backspace 기능과 동일)
  * \f : 현재 활성 위치를 다음 페이지의 시작 위치로 옮김
  * \r : 현재 활성 위치를 현재 라인의 시작 위치로 옮김
* `\\`, `\'`, `\"`
  * \, ', " 를 문자 상수로 사용하게 된다.
* `\ooo`, `\xhh`
  * 어떤 문자를 8진수, 16진수를 이용하여 ASCII 코드로 표현 하려면 `'`(작은따옴표)로 감싸야 한다.


## 이스케이프 시퀀스 사용 예시

```c
#include <stdioh>
int main()
{
	char test_octal_number = '\141';		// \ooo
	char test_hexadecimal_number = '\x41';		// \xhh

	printf("%c \n",test_octal_number);		// \n
	printf("%c \n",test_hexadecimal_number);

	printf("AB\bC\n");		// \b

	printf("T\tA\tB\n");		// \t

	printf("123456\r789\n");	// \r

	return 0;
}
```

**결과**  
```bash
a 
A 
AC
T	A	B
789456
```




**감사합니다.**

---

### Related Posts

**[출력 함수와 형식 지정자(printf, format specifiers)][00]**

**[입력 함수(scanf)][01]**

**[변수와 자료형(variables, data types)][02]**

---

[\<\< 이전글][0]	|[홈으로 가기][1]	|[post 목록 보기][2]	|[다음글 \>\>][3]
------			|:------:		|:------:		|------:
**[markdown 문법 정리][0]**	|			|			|**[ASCII 코드][3]**



[0]: https://atomic0x90.github.io/markdown/2019/05/24/markdown-Grammar-theorem.html "markdown 문법 정리"
[1]: https://atomic0x90.github.io/ "home"
[2]: https://atomic0x90.github.io/posts/ "posts"
[3]: https://atomic0x90.github.io/c-language/2019/05/29/ASCII.html "ASCII 코드"

[00]: https://atomic0x90.github.io/c-language/2019/06/04/printf-format.html "출력 함수와 형식 지정자"
[01]: https://atomic0x90.github.io/c-language/2019/06/05/scanf-format.html "입력 함수"
[02]: https://atomic0x90.github.io/c-language/2019/05/30/Variables-and-data-types.html "변수와 자료형"


{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}





