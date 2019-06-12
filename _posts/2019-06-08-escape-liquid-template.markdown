---
layout: post
title:  "jekyll에서 {{ }}, {% %}사용하기(escape liquid template)"
date:   2019-06-08 13:07:45
author: atomic0x90 (Yujun Han)
categories: Jekyll markdown
tags:  Jekyll markdown
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

jekyll를 이용해서 만든 github blog에 마크다운(markdown) 문법을 이용해서 글을 쓴다. 
글을 쓰다 보면 예시를 작성하기 위해 
`{% raw %}{{ }}{% endraw %}` 과 `{% raw %}{% %}{% endraw %}`를 사용하는 일이 생긴다
([sitemap 만들기 참고][0]). 
하지만 그대로 작성하면 예시를 실행하려고 해서 문제가 생긴다. 
그럴 경우에는 다음과 같이 liquid 문법의 raw tag를 사용한다.  

---

**작성 방법**
~~~
{{"{% raw"}} %} {{"{{ example"}} }} {{"{% endraw"}} %}
{{"{% raw"}} %} {{"{% example"}} %} {{"{% endraw"}} %}
~~~

raw tag를 이용해서 앞뒤로 감싸주면 다음과 같이 마크다운 문법에서 
`{%raw%}{{ }}{%endraw%}`, `{%raw%}{% %}{%endraw%}`이 예외 처리가 되어 실행되지 않는다.  

**결과**
~~~
{{"{{ example"}} }}
{{"{% example"}} %}
~~~




**감사합니다.**

---

### Related Posts

**[마크다운(markdown) 문법 정리][00]**

---


[\<\< 이전글][1]        |[홈으로 가기][2]       |[post 목록 보기][3]    |[다음글 \>\>][4]
------                  |:------:               |:------:               |------:
**[Github blog를 검색이 되게 설정하기][1]**   |                       |   |**[Ubuntu에서 이미지 편집기 사용하기][4]**











[0]: https://atomic0x90.github.io/jekyll/2019/06/06/Registration-github-blog-search.html "example"
[1]: https://atomic0x90.github.io/jekyll/2019/06/06/Registration-github-blog-search.html "Github blog를 검색이 되게 설정하기"
[2]: https://atomic0x90.github.io/ "home"
[3]: https://atomic0x90.github.io/posts/ "posts"
[4]: https://atomic0x90.github.io/ubuntu/2019/06/09/ubuntu-image-editor.html "Ubuntu에서 이미지 편집기 사용하기"


[00]: https://atomic0x90.github.io/markdown/2019/05/24/markdown-Grammar-theorem.html "마크다운 문법 정리"





{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}























