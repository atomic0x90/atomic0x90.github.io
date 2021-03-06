---
layout: post
title:  "마크다운(MarkDown) 문법 정리"
date:   2019-05-24 23:01:52
author: atomic0x90 (Yujun Han)
categories: markdown
tags:  markdown
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## 마크다운(markdown)이란?

[마크다운(markdown)][0]은 일반 텍스트 문서의 양식을 편집하는 문법이다.
마크다운의 확장자는 <strong>.md </strong> 또는 <strong>.markdown</strong> 이다.
HTML등 다른 문서로 변환이 가능하다.

---

## 마크다운을 사용하게 된 계기

저는 GitHub를 사용하면서 <strong>README.md</strong>를 통해 처음 접한 문법입니다.
저는 지금 post를 마크다운을 사용하여 작성하고 있습니다.
문법이 간단해서 금방 익힐 수 있었습니다.
마크다운이 비교적 빠르게 post를 작성할 수 있다고 느껴졌고
무엇보다도 GitHub에서도 지원하는 문법인 것 같아서 사용하게 됐습니다.

---

마크다운 문법(syntax)
===

---
## 줄 바꾸기(change line)

마크다운으로 작성할 때 줄을 밑으로 내리는 방법은 두 가지가 있다.

2. 문단을 나누고 싶으면 <strong>엔터 키를 두 번</strong> 누른다.
2. 한 줄을 내리고 싶으면 <strong>스페이스바를 두 번</strong> 누른다.

```md
첫 번째.
두 번째.	<!--엔터키를 한번만 누르면 같은 줄에 나열 된다.-->
```
**결과**  
첫 번째.
두 번째.

```md
첫 번째.	<!--스페이스바를 두번 누르고 엔터키를 누르면 줄이 바뀐다.-->
두 번째.
```
**결과**  
첫 번째.  
두 번째.

```md
첫 번째.	<!--엔터를 두번 누르면 문단이 나뉜다. -->

두 번째.
```

**결과**  
첫 번째.

두 번째.

---
## 제목 크기(head size)

`#` 를 입력한 뒤 제목을 입력한다.
`#` 을 많이 입력할수록(최대 6개) 제목 크기가 작아진다.

`<h1>`부터`<h6>`까지 표현이 가능하다.

**작성법**  
```
# 제목(h1)
## 제목(h2)
### 제목(h3)
#### 제목(h4)
##### 제목(h5)
###### 제목(h6)
```

**결과**  
# 제목(h1)
## 제목(h2)
### 제목(h3)
#### 제목(h4)
##### 제목(h5)
###### 제목(h6)

또 다른 표현으로는
`<h1>`과 `<h2>`를 표현할 수 있다.

**작성법**  
```
제목(h1)
===

제목(h2)
---
```

**결과**  

제목(h1)
===

제목(h2)
---

---
## 글꼴(font)

* 이탤릭체(italic font) : 글자 양 옆에 `*` 또는 `_` 를 표시한다.
* 볼드체(bold font) : 글자 양 옆에 `**` 또는 `__`를 표시한다.
* 취소선 : 글자 양 옆에 `~~`를 표시한다.
* 밑줄 : 글자 앞에 `<u>` 를 표시하고 글자 뒤에 `</u>` 를 표시한다.

**작성법** 
```markdown
*italic font*  
_이탤릭체_
  
**bold font**  
__볼드체__

***test*** <!-- 이탤릭체와 볼드체를 같이 사용할 수도 있다. -->

*__test__*

~~취소선~~

<u>밑줄</u>
```

**결과** 
 
*italic font*  
_이탤릭체_  

**bold font**  
__볼드체__

***test***

*__test__*

~~취소선~~

<u>밑줄</u>

---
## 강조(emphasis)

\<code\>, \<pre\> tag로 변환된다.

* 인라인 코드 강조(inline code emphasis) : 글자 양 옆에  **`** (숫자 1번 왼쪽 버튼,[grave accent][1])를 표시한다.  

**작성법**  
```md
`강조`
```  

**결과**  
`강조`

그리고 인라인 강조를 사용하여 HTML로 변환시 \<code\> tag 로 wrapping 된다.  
따라서  
```css
code
{
	color : red;
	//etc.
}
```
와 같이 CSS를 적용하면 원하는 형태로 수정이 가능하다.  
~~밑에 계속해서 나오는 tag의 CSS code는 생략함.~~



* 블록 코드 강조(block code emphasis) : **\`** 를 3번 이상 입력하고 코드의 종류를 적는다.
내용을 입력하고 **\`** 를 3번 이상 입력하여 닫아준다.

* Syntax Highlighting이 지원되는 언어 종류 (괄호 안에 적힌 것으로 사용한다.)
  * Bash (bash)
  * C (c)
  * C++ (cpp)
  * C# (cs)
  * CSS (css)
  * Markdown (md)
  * HTML, XML (html)
  * HTTP (http)
  * Java (java)
  * JavaScript (javascript)
  * PHP (php)
  * Python (python)
  * SQL (sql)
  * Ruby (ruby)
  * etc.

**작성법**  
~~~
```
No language indicated, so no syntax highlighting.
```

```bash
gcc test.c -o test
```

```c
#include <stdio.h>
int main()
{
	printf("test\n");
	return 0;
}
```

```html
<h2>test</h2> <p>
<img src="test.jpg" width="200" height="200" alt="test..." title="test..!">
```
~~~

**결과**  

코드의 종류를 적지 않으면 자동으로 tag로 넘겨진다. 

```
No language indicated, so no syntax highlighting. 
```

```bash
gcc test.c -o test
```

```c
#include <stdio.h>
int main()
{
	printf("test\n");
	return 0;
}
```

```html
<h2>test</h2> <p>
<img src="test.jpg" width="200" height="200" alt="test..." title="test..!">
```
* 위의 작성법처럼 마크다운 소스코드 작성법  
`~`를 3번 이상 입력하고 소스코드 작성 후 다시 `~`를 3번 이상 입력하여 닫아준다.

---
## 수평선(horizontal line)

`-`(Hyphens) 또는 `*`(Asterisk) 또는 `_`(Underscore) 를 3번 이상 입력한다.

**작성법**  
~~~
---
***
___
~~~

**결과**  

---  
***  
___  



---
## 인용문(a quotation)

`>` 를 입력하고 인용문을 작성한다.

\<blockquote\> tag로 변환된다.  

**작성법**  
```md
> 인용문  
```

**결과**  
> 인용문  


---
## 목록(list)

순서가 필요한 목록 : `(숫자).` 을 입력한다.  
순서가 필요하지 않은 목록 : `*` (asterisks),`-` (hyphen),`+` (plus sign) 을 입력한다.  
\<ol\>, \<ul\> tag로 변환된다.

**작성법**  
```md
1. 순서가 필요한 목록  

1. 순서가 필요한 목록  
  1. 순서가 필요한 목록  
  1. 순서가 필요한 목록  

1. 순서가 필요한 목록  
  * 순서가 필요하지 않은 목록
  * 순서가 필요하지 않은 목록  

+ 순서가 필요하지 않은 목록
* 순서가 필요하지 않은 목록
  - 순서가 필요하지 않은 목록
     + 순서가 필요하지 않은 목록
```

**결과**  
1. 순서가 필요한 목록

1. 순서가 필요한 목록
   1. 순서가 필요한 목록
   1. 순서가 필요한 목록

1. 순서가 필요한 목록
   * 순서가 필요하지 않은 목록
   * 순서가 필요하지 않은 목록

+ 순서가 필요하지 않은 목록
* 순서가 필요하지 않은 목록
   - 순서가 필요하지 않은 목록
      + 순서가 필요하지 않은 목록





---
## 표(table)

`|` ([Vertical bar][2]) 를 이용하여 구역을 나눈다.  
표(table) 안에 `|` 를 입력하고 싶으면 `&#124;` 를 입력한다.  
표(table) 안에 공백을 넣고 싶으면 `&nbsp;` 를 입력한다.  
표(table) 안에 위치를 정렬하고 싶으면 `:`([colon][00]) 을 이용한다.  

**작성법**  
```md
table1		| table2			|table3
:------:	|:-------			|------:
Center alignment| &#124; Left alignment &#124;	|**Right alignment**
가운데 정렬	|왼쪽 정렬			|오른쪽 정렬
Yujun Han	| _**atomic0x90**_		|&nbsp;
```

**결과**  

table1		| table2			| table3
:------:	|:-------			|------:
Center alignment| &#124; Left alignment &#124;	| **Right alignment**
가운데 정렬	|왼쪽 정렬			|오른쪽 정렬
Yujun Han 	| _**atomic0x90**_ 		|&nbsp;

---
## 링크(link)

\<a\> tag로 변환된다.  

**작성법**  
```
[GOOGLE](https://www.google.com)

[MY GitHub](https://github.com/atomic0x90 "링크 설명(title)")

[GitHub][variable]

[NAVER][100]

< > 안의 URL이나 일반 URL은 자동으로 링크로 사용된다.
Github home page : <https://github.com>

GOOGLE home page : https://www.google.com

[variable]: https://github.com
[100]: https://www.naver.com/ "naver로 이동 합니다."
```

**결과**  

[GOOGLE](https://www.google.com)  

[MY GitHub](https://github.com/atomic0x90 "링크 설명(title)")

[GitHub][variable]

[NAVER][100]

< > 안의 URL 이나 일반 URL은 자동으로 링크로 사용된다.  
GitHub home page : <https://github.com>

GOOGLE home page : https://www.google.com

[variable]: https://github.com
[100]: https://www.naver.com/ "naver로 이동 합니다."




---
## 사진(image)

링크 사용법에서 앞에 `!`를 붙인다. 사진에 링크를 추가할 수 있다.  
\<img\> tag로 변환된다.

**작성법**  
```md
![alt text]({{site.baseurl}}/assets/instacode.png "링크 설명(title)")

![test..][header]

[![atomic0x90][img link]][test link] 		//사진에 링크를 추가하는 방법

[header]: {{site.baseurl}}/assets/header_image.jpg "My page header img"
[img link]: {{site.baseurl}}/assets/logo.png "My page home img"
[test link]: https://github.com/atomic0x90/atomic0x90.github.io/tree/master/assets
```

**결과**  
![alt text]({{site.baseurl}}/assets/instacode.png "링크 설명(title)")

![test..][header]

[![atomic0x90][img link]][test link]



[header]: {{site.baseurl}}/assets/header_image.jpg "My page header img"
[img link]: {{site.baseurl}}/assets/logo.png "My github page with pictures"
[test link]: https://github.com/atomic0x90/atomic0x90.github.io/tree/master/assets



---
## 원시 HTML

마크다운 문법이 아닌 HTML 문법이 사용 가능하다.

**예시**  
```html
<img src="{{site.baseurl}}/assets/logo.png" width="140" height="200" alt="home img" title="home">
```

**결과**  
<img src="{{site.baseurl}}/assets/logo.png" width="140" height="200" alt="home img" title="home">


**감사합니다.**

---

### Related Posts

**[jekyll 에서 {%raw%}{{ }}{%endraw%}, {%raw%}{% %}{%endraw%}사용하기(escape liquid template)][03]**

---

[\<\< 이전글][01]		|[홈으로 가기][3]	|[post 목록 보기][4]	|[다음글 \>\>][02]
------				|:------:		|:------:		|------:
**[C언어의 특징과 기본 구조][01]**	|			|			|**[C언어 이스케이프 시퀀스][02]**




[0]: https://ko.wikipedia.org/wiki/마크다운 "wikipedia"
[1]: https://ko.wikipedia.org/wiki/억음_부호 "wikipedia"
[2]: https://en.wikipedia.org/wiki/Vertical_bar#Computing "wikipedia"
[3]: https://atomic0x90.github.io/ "home"
[4]: https://atomic0x90.github.io/posts/ "posts"

[00]: https://ko.wikipedia.org/wiki/쌍점#컴퓨터에서의_사용 "wikipedia"
[01]: https://atomic0x90.github.io/c-language/2019/05/23/Characteristics-and-structure-of-language-C.html "C언어의 특징과 기본 구조"
[02]: https://atomic0x90.github.io/c-language/2019/05/28/C-Language-escape-sequence.html "C언어 이스케이프 시퀀스(escape sequence)"
[03]: https://atomic0x90.github.io/jekyll/markdown/2019/06/08/escape-liquid-template.html "escape liquid template"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}
