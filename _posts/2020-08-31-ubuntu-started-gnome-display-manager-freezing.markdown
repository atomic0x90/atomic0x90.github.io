---
layout: post
title:  "Started Gnome display manager 멈춤 해결 방법"
date:   2020-08-31 10:00:00
author: atomic0x90 (Yujun Han)
categories: ubuntu
tags:  ubuntu
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## Started Gnome Dispaly Maneger 멈춤 해결 방법

---

Ubuntu를 듀얼 부팅으로 사용하던 도중에 다음 사진과 같이 갑자기 Ubuntu가 켜지지 않고 

**[ OK ] Started GNOME Display Manager.**

라는 메시지가 나온 상태로 작동이 멈춰있었다.

![Started Gnome Display Manager img][10]

내가 해결했던 방법은 다음과 같다.

1. 듀얼 부팅 화면(GNU GRUB, 보라색 화면, windows 와 ubuntu 부팅을 선택하는 화면)에서 
Ubuntu에 진입하기 전에 **e** 키를 누른다.
1. 'Ubuntu'의 설정 창에 들어오게 된다. 여기서 **linux	/...  quiet splash ...** 라인을 찾는다.
1. **quiet splash** 문구 뒤에 **nomodeset**을 추가해 준다.
 (**quiet splash \-\-\-** 라고 되어있다면 **\-\-\-**를 지우고 **nomodeset**을 추가한다.)
```bash
linux		/... 	quiet splash nomodeset ...
```
1. **F10** 키를 눌러 저장한 뒤 설정 창을 빠져나온다.

여기까지 따라 했다면 Ubuntu가 정상적으로 실행이 되었을 것이다.

Ubuntu를 실행할 때마다 위의 과정을 반복하고 싶지 않으면 다음과 같이 한다.


1. Terminal을 켠다.
1. **su** 를 입력해 관리자 권한을 얻는다.
1. **gedit /etc/default/grub** 을 입력해 파일을 연다.
1. **GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"** 라인을 찾는다.
1. **GRUB_CMDLINE_LINUX_DEFAULT="quiet splash nomodeset"** 으로 수정한 뒤 파일을 저장한다.
1. **update-grub** 을 입력해 grub를 업데이트를 해준다.

여기까지 했다면 Ubuntu를 재부팅하여 정상적으로 작동이 되는지 확인하면 된다.

```bash
//1 터미널 열기

//2 관리자 권한 얻기
su

//3
gedit /etc/default/grub

//4,5 파일에서 nomodeset 추가

//6 grub 업데이트를 꼭 해주기
update-grub

```


**감사합니다.**


---


[홈으로 가기][01]       |[더 많은 ubuntu post 보기][03]        |[post 목록 보기][02]
:------:                |:------:                               |:------:
                        |                                       |

[10]: {{site.baseurl}}/assets/post_img/Started_Gnome_Display_Manager.png "Started Gnome Display Manager img"


[01]: https://atomic0x90.github.io/ "home"
[02]: https://atomic0x90.github.io/posts/ "posts"
[03]: https://atomic0x90.github.io/posts/#ubuntu "ubuntu posts"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}





