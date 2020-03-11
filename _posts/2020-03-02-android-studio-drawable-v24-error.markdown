---
layout: post
title:  "안드로이드 스튜디오 drawable 오류(android studio drawable error)"
date:   2020-03-02 10:01:00
author: atomic0x90 (Yujun Han)
categories: android-studio
tags:  android-studio
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## drawable 과 drawable-v24 차이

drawable-v24는 비교적 최근에 나온 android version을 사용하는 기기에 호환하기 위한 folder이다.

drawable 은 비교적 오래된 android version을 사용하는 기기에 호환하기 위한 folder이다.

따라서 drawable, drawable-v24 가 나누어진 이유는 기기 호환성 및 
android version마다 다른 화면 밀도(크기)에 맞춰서 프로그램을 제공하기 위함이다.

---

## Error inflating class ImageView

이러한 오류가 발생하는 원인은 다음과 같다.

+ drawable-v24가 호환이 안되는 기기

drawable-v24가 호환이 안되기 때문에 drawable folder를 생성하고

drawable-v24에 있는 파일을 복사하여 drawable에 넣는다.

**drawable, drawable-v24 경로**

```bash
~/app/src/main/res
```

res 폴더 밑에 drawable을 생성한다.

```bash
~/app/src/main/res/drawable
~/app/src/main/res/drawable-v24
```

**감사합니다.**


---


[홈으로 가기][01]       |[더 많은 android post 보기][03]        |[post 목록 보기][02]
:------:                |:------:                               |:------:
                        |                                       |


[01]: https://atomic0x90.github.io/ "home"
[02]: https://atomic0x90.github.io/posts/ "posts"
[03]: https://atomic0x90.github.io/posts/#android-studio "android posts"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}


