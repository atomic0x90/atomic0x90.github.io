---
layout: post
title:  "Git push origin master 오류"
date:   2021-08-14 10:00:00
author: atomic0x90 (Yujun Han)
categories: Github
tags:  Github
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## git push origin master 오류(2021년 8월 14일 이후)

2021년 8월 14일에 평소와 같이 git push를 진행했을 때 git push가 안되길래 처음에는 어떤 이유인지 안 보고 비밀번호를 잘못 쳤구나 생각해서 몇 번이나 계속 시도를 해봤다.  
그리고 생각을 해 보니 예전부터 github에서 이메일로 나중에 git push를 할 때 user id, user pw로 안되고 **pw 대신에 token을 이용**해라고 알려줬었다. 그게 바로 2021년 8월 14일 이후이다.  
그래서 Github에 접속해서 token을 발급받고 계정 비밀번호 대신에 token을 입력해서 git push가 성공하였다. 

나의 오류 메시지
```bash
remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.
remote: Please see https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/ for more information.
fatal: unable to access 'https://github.com/atomic0x90/programmers-challenges.git/': The requested URL returned error: 403
```

![img]({{site.baseurl}}/assets/git_push/git_push.png "git push error")


---

## git push 방법(git token 생성 방법, 2021년 8월 14일 이후)

1. Github 홈페이지에 접속해서 로그인 이후 **우측 상단에 프로필**을 클릭한 뒤 **Settings**를 클릭한다.
![order1]({{site.baseurl}}/assets/git_push/order1.jpg "order1")

1. 좌측에 계정 관련 설정 리스트들이 있는데 **Developer settings**를 클릭한다.
![order2]({{site.baseurl}}/assets/git_push/order2.jpg "order2")

1. **Personal access tokens**를 클릭한 뒤, **Generate new token**을 클릭한다.
![order3]({{site.baseurl}}/assets/git_push/order3.jpg "order3")

1. 그러면 token에 관하여 설정을 진행하는데 **token의 이름**, **token의 유지 기한**, **token의 권한**을 체크한 뒤 **Generate token**을 클릭하여 token을 만든다.
![order4]({{site.baseurl}}/assets/git_push/order4.jpg "order4")

1. 이제 token이 만들어졌고 token을 사용하기 위해서는 **token을 저장**해야 한다.
![order5]({{site.baseurl}}/assets/git_push/order5.jpg "order5")

1. 이제 git push 이후에 계정 이름, token을 작성하면 git push가 정상적으로 될 것이다.


**감사합니다.**


---


[홈으로 가기][01]       	|[더 많은 github post 보기][03]       	|[post 목록 보기][02]
:------:                |:------:                               |:------:
                        |                                       |

[img]: {{site.baseurl}}/assets/git_push/git_push.png
[order1]: {{site.baseurl}}/assets/git_push/order1.jpg

[01]: https://atomic0x90.github.io/ "home"
[02]: https://atomic0x90.github.io/posts/ "posts"
[03]: https://atomic0x90.github.io/posts/#Github "github posts"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}



