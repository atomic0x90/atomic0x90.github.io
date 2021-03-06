---
layout: post
title:  "C언어의 특징과 기본 구조"
date:   2019-05-23 17:15:20
author: atomic0x90 (Yujun Han)
categories: C-Language
tags:  C-Language
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## C언어란?
C언어는 [유닉스(UNIX)][0]라고 하는 운영체제를 개발하기 위한 목적으로 
[데니스 리치(Dennis Ritchie)][1]에 의하여 1972년 개발되었다.
이후의 많은 컴퓨터 언어들이 C언어의 문법적인 부분을 이어받았다.
C++, C#, Java, JavaScript, PHP, Python 등의 언어들은 C언어의 제어구조와 수식 형태를 사용하고 있다.

---

## C언어의 특징

* <strong>효율적이다.</strong>

C언어로 작성한 프로그램이 다른 언어로 작성한 프로그램에 비해서 실행 속도가 빠르고 메모리를 효과적으로 사용할 수 있다.

* <strong>하드웨어 제어가 가능하다.</strong>

C언어는 운영체제를 개발하기 위해서 만들었던 언어이다.
따라서 기계어 수준의 구체적인 하드웨어 제어가 가능하다.
그래서 [임베디드 시스템(embedded system)][2]은 대부분 C언어로 개발한다.

* <strong>이식성이 좋다.</strong>

[이식성(portability)][3]이란 작성된 프로그램을 다른 CPU를 가지는 하드웨어로 얼마나 쉽게 이식할 수 있는가를 나타낸다.
즉 이식성이 좋다는 것은 하드웨어의 의존도가 낮다는 것이다.

* <strong>간결하다.</strong>

C언어는 모든 표기법이 간결하다. 그래서 처음 C언어를 접하는 사람은 대부분 한 번에 이해하기 어렵다.
하지만 표기법이 익숙해지면 표기법이 매우 간결하게 느껴진다.

---

## C언어의 기본 구조

C프로그램은 반드시 main 함수가 하나 있어야 한다.
C프로그램은 main 함수로 시작해서 main 함수로 끝이 난다.
<strong> { </strong> 는 함수의 시작 <strong> } </strong> 는 함수의 끝을 나타낸다.
함수에 대해 자세한 것은 나중에 알아보도록 하자.
함수의 실행 방향은 위에서부터 밑으로 간다.

{% highlight C %}

#include <stdio.h>
int main()
{ //시작
	printf("반가워요!\n");
	return 0;
} //끝

{% endhighlight %}

[헤더 파일(header file)][4]은 특정 파일을 읽어서 소스 파일에 포함해준다.
즉 필요한 라이브러리 함수에 대한 정보를 가지고 있는 헤더 파일을 [컴파일러(compiler)][5]에 불러오라고 지시해야 한다.
헤더 파일은 확장자가 <strong> .h </strong> 로 끝나는 파일이다.

{% highlight C %}

#include <stdio.h> //예시

{% endhighlight %}

[주석(comment)][6]은 소스 코드에 붙이는 설명글이다.
주석은 프로그램의 실행 결과에 영향을 끼치지 않는다.
프로그램 사용자의 이해를 돕기 위해서 주석을 많이 사용한다.

* 한 줄 주석 사용법 (<strong> // </strong>)

{% highlight C %}

#include <stdio.h>
int main() // 주석
{
	printf("반가워요!\n"); // 주석
	return 0;
} // 주석

{% endhighlight %}

* 여러 줄 주석 사용법 (<strong> /* */ </strong>)

{% highlight C %}

#include <stdio.h>
/* 주석
	주석
주석*/
int main()
{
	printf("반가워요!\n");
	return 0;
/*
	주석
	주석
*/
}

{% endhighlight %}

<strong>;</strong>[ 세미콜론(semicolon)][7]은 선언문을 구분하는 역할이다.
C언어에서 세미콜론은 종결 부호이므로 반드시 모든 선언문 뒤에 사용해야 한다.
일반적으로 세미콜론은 한 줄에 하나씩 사용된다.
하지만 세미콜론은 선언문을 구분하는 역할이므로 같은 줄에 여러 번 선언문을 사용하고 세미콜론을 사용해도 무방하다.

{% highlight C %}

#include <stdio.h>
int main()
{
	printf("안녕하세요!\n");
	printf("반가워요!\n"); printf("한 번 더 반가워요!\n"); // 오류가 아님
	return 0;
}

{% endhighlight %}

<strong>return</strong>은 함수를 호출한 곳으로 값을 반환하는 [예약어(reserved word)][8]이다.
즉 값을 반환 후 함수는 종료된다.

{% highlight C %}

#include <stdio.h>
int main()
{
	return 0; // main 이라는 함수를 값(0)을 반환 후 종료한다.
}


{% endhighlight %}

소스 코드에서는 공백, 띄어쓰기나 줄바꿈이 있어도 실행 결과는 동일하다.
일반적으로 소스 코드의 가독성을 높이기 위해 공백이나 줄바꿈을 한다.

{% highlight C %}

#include <stdio.h>
int main(){
	printf("반가워요!");
	return 0;
}

{% endhighlight %}

{% highlight C %}

#include <stdio.h>

int main()

{
	printf("반가워요!")    ;


return 0;

}

{% endhighlight %}

<strong>감사합니다.</strong>

---

### Related Posts

**[이스케이프 시퀀스 정리(escape sequence)][00]**

**[ASCII 코드(ASCII code)][01]**

**[변수와 자료형(variables, data types)][02]**

---

&nbsp;	|[홈으로 가기][9]	|[post 목록 보기][10]	|[다음글 \>\>][11]
------	|:------:		|:------:		|------:
	|			|			|**[markdown 문법 정리][11]**



[0]: https://ko.wikipedia.org/wiki/유닉스 "wikipedia"
[1]: https://ko.wikipedia.org/wiki/데니스_리치 "wikipedia"
[2]: https://ko.wikipedia.org/wiki/임베디드_시스템 "wikipedia"
[3]: https://en.wikipedia.org/wiki/Software_portability "wikipedia"
[4]: https://ko.wikipedia.org/wiki/헤더_파일 "wikipedia"
[5]: https://ko.wikipedia.org/wiki/컴파일러 "wikipedia"
[6]: https://ko.wikipedia.org/wiki/주석_(프로그래밍) "wikipedia"
[7]: https://ko.wikipedia.org/wiki/쌍반점#컴퓨터에서의_사용 "wikipedia"
[8]: https://ko.wikipedia.org/wiki/예약어 "wikipedia"
[9]: https://atomic0x90.github.io/ "home"
[10]: https://atomic0x90.github.io/posts/ "posts"
[11]: https://atomic0x90.github.io/markdown/2019/05/24/markdown-Grammar-theorem.html "markdown 문법 정리"

[00]: https://atomic0x90.github.io/c-language/2019/05/28/C-Language-escape-sequence.html "escape sequence"
[01]: https://atomic0x90.github.io/c-language/2019/05/29/ASCII.html "ASCII code"
[02]: https://atomic0x90.github.io/c-language/c++/2019/05/30/Variables-and-data-types.html "변수와 자료형"



{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}














