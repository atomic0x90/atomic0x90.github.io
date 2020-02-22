---
layout: post
title: "C++ 이스케이프 시퀀스(escape sequence) 정리"
date: 2020-02-17 10:01:00
author: atomic0x90 (Yujun Han)
categories: C++
tags: C++
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
\a      |경고(alert)
\n      |줄바꿈(new line)
\t      |수평 탭(horizontal tab)
\v      |수직 탭(vertical tab)
\b      |백스페이스(backspace)
\f      |폼 피드(form feed)
\r      |캐리지 리턴(carriage return)
\\\     |백슬래시( \\, backslash)
\\'     |작음따옴표( ', single quotes)
\\"     |큰따옴표( ", double quotes)
\\ooo   |8진수 숫자를 사용하여 ASCII 코드의 문자 표현
\\xhh   |16진수 숫자를 사용하여 ASCII 코드의 문자 표현

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

```cpp
#include <iostream>

using namespace std;

int main()
{
        char test_octal_number = '\141';                // \ooo
        char test_hexadecimal_number = '\x41';          // \xhh

        cout<<test_octal_number<<"\n";          // \n
        cout<<test_hexadecimal_number<<"\n";

        cout<<"AB\bC\n";                // \b

        cout<<"T\tA\tB\n";              // \t

        cout<<"123456\r789\n";          // \r

        cout<<"\\ \' \" \n";            // \\ \' \"

        return 0;
}
```


**실행 결과**
```bash
a
A
AC
T	A	B
789456
\ ' " 
```


**감사합니다.**

---



[홈으로 가기][01]       |&nbsp;                                 |[post 목록 보기][02]
:------:                |:------:                               |:------:
                        |                                       |


[01]: https://atomic0x90.github.io/ "home"
[02]: https://atomic0x90.github.io/posts/ "posts"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}



