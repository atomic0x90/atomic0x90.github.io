---
layout: post
title:  "Ubuntu에서 이미지 편집기 사용하기"
date:   2019-06-07 22:32:23
author: atomic0x90 (Yujun Han)
categories: ubuntu
tags:  ubuntu
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

Ubuntu를 사용하면서 이미지를 편집해야 할 때가 있다. windows에서는 그림판을 이용해 간단하게 편집한다. 
그림판과 매우 비슷한 이미지 편집기를 Ubuntu에서 사용하도록 해보자.

---

설치 방법은 다음과 같다.

```bash
sudo apt-get install kolourpaint4
```

그러면 /usr/bin 경로에 실행파일로 설치가 된다. 터미널에서 실행하려면 다음과 같이 입력한다. 

```bash
kolourpaint
```

Ubuntu 검색창에 kolourpaint를 검색하고 실행해도 된다.

**실행 화면**

![kolourpaint img][0]






**감사합니다.**


[\<\< 이전글][1]        |[홈으로 가기][2]       |[post 목록 보기][3]    |다음글 \>\>
------                  |:------:               |:------:               |------:
[escape liquid template][1]   |                       |                       |








[0]: {{site.baseurl}}/assets/post_img/ubuntu-image-editor01.png "kolourpaint img"
[1]: https://atomic0x90.github.io/jekyll/markdown/2019/06/08/escape-liquid-template.html "escape liquid template"
[2]: https://atomic0x90.github.io/ "home"
[3]: https://atomic0x90.github.io/posts/ "posts"



{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}










