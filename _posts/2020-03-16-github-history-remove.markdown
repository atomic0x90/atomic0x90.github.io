---
layout: post
title:  "Github 커밋 히스토리 삭제 방법"
date:   2020-03-16 10:00:00
author: atomic0x90 (Yujun Han)
categories: Github
tags:  Github
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## github 커밋 히스토리 삭제 방법(github commit history remove)

github를 사용하다 보면 특정 파일을 삭제해야 하는 경우가 생긴다.

하지만 특정 파일을 삭제해도 history에 남게 된다.

history를 삭제하려면 다음 명령어를 입력하면 된다.


```bash
git filter-branch --force --index-filter "git rm --cached --ignore-unmatch 'file_path/file_name'" --prune-empty --tag-name-filter cat -- --all
```

`file_name`에는 history를 지우고 싶은 파일 이름과 확장자를 작성하면 된다.

`file_path`에는 history를 지우고 싶은 파일의 경로를 작성하면 된다. 경로는 root부터 전부 다 작성하도록 한다.

명령어를 입력하면 해당 파일의 history가 지워지게 된다.

다음 명령어를 입력하여 새로 만들어진 history를 강제로 적용하면 된다.

```bash
git push origin master --force
```
---

같은 실수를 반복하지 않으려면 `.gitignore`에 push되면 안 되는 파일을 저장하고 push 한다.

1. .gitignore 파일에 push되면 안 되는 파일을 저장한다.
1. 다음과 같은 명령어로 .gitignore를 적용시킨다.

```bash
git add .gitignore
git commit -m "Update .gitignore (file_name)"
git push orign master
```


**감사합니다.**


---


[홈으로 가기][01]       |        |[post 목록 보기][02]
:------:                |:------:                               |:------:
                        |                                       |


[01]: https://atomic0x90.github.io/ "home"
[02]: https://atomic0x90.github.io/posts/ "posts"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}



