---
layout: post
title:  "안드로이드 스튜디오 Activity 이동할 때 onUserLeaveHint 호출 문제"
date:   2020-08-12 10:01:00
author: atomic0x90 (Yujun Han)
categories: android-studio
tags:  android-studio
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## 안드로이드 스튜디오 Activity 이동할 때 onUserLeaveHint 호출 문제

우리는 안드로이드 홈 버튼(Home key)을 감지하여 이벤트를 제어하기 위해서 onUserLeaveHint 함수에 의존하게 된다.

하지만 Activity를 이동할 때 의도하지 않게 onUserLeaveHint가 호출이 된다.

만약에 service를 이용한 이벤트를 onUserLeaveHint 함수를 통해 제어(중지)를 하고 있는 상황이 있다고 하자.

그리고 Activity를 이동해도 service가 계속 작동하도록 하고 싶은데 아무런 조치 없이 Activity를 이동하면 

의도하지 않은 service가 제어(중지)가 된다. 

이러한 것을 방지하기 위해서 intent를 넘겨줄 때 다음과 같은 flag를 추가하여 준다.

`FLAG_ACTIVITY_NO_USER_ACTION`

이것을 intent flag에 추가하면 Activity를 이동할 때에는 onUserLeaveHint 함수가 호출되지 않고 

홈 버튼(Home key)를 누르면 onUserLeaveHint 함수가 호출이 된다.

**예시**

```
Intent intent = new Intent(MainActivity.this, SubActivity.class);

intent.addFlags(FLAG_ACTIVITY_NO_USER_ACTION);	// 플래그를 추가한다.

startActivity(intent);
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

