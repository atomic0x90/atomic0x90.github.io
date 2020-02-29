---
layout: post
title:  "안드로이드 스튜디오 뒤로가기 버튼(android studio back button)"
date:   2020-02-28 10:01:00
author: atomic0x90 (Yujun Han)
categories: android-studio
tags:  android-studio
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## 뒤로 가기 막기

Activity 화면 전환 시 뒤로 가기 버튼을 누르면 이전 화면으로 돌아간다.

이것을 방지하기 위해서는 다음 코드를 .java 코드에 삽입한다.

**code**
```
@Override
public void onBackPressed() {
    //super.onBackPressed();
}
```

뒤로 가기 버튼의 기능을 막기 위해 `super.onBackPressed();`를 주석 처리했다. 해당 코드를 삭제해도 무방하다.

---

## 뒤로 가기 버튼 2번 입력 후 앱 종료

기본 상태에서 앱을 개발하면 뒤로 가기 버튼 한 번에 앱이 종료된다.

이것은 의도된 게 아니라면 사용자가 불편을 느낄 수 있다.

그래서 뒤로 가기 버튼을 한번 눌렀을 때 한 번 더 뒤로 가기 버튼을 누르면 앱이 종료된다는 메시지를 띄어준다.

다음 코드를 .java 코드에 삽입한다.

**code**
```
// 마지막으로 뒤로 가기 버튼을 눌렀던 시간 저장
private long backKeyPressedTime = 0;
// 첫 번째 뒤로 가기 버튼을 누를 때 표시
private Toast toast;

@Override
public void onBackPressed() {
    //super.onBackPressed();
    // 기존 뒤로 가기 버튼의 기능을 막기 위해 주석 처리 또는 삭제

    // 마지막으로 뒤로 가기 버튼을 눌렀던 시간에 2.5초를 더해 현재 시간과 비교 후
    // 마지막으로 뒤로 가기 버튼을 눌렀던 시간이 2.5초가 지났으면 Toast 출력
    // 2500 milliseconds = 2.5 seconds
    if (System.currentTimeMillis() > backKeyPressedTime + 2500) {
        backKeyPressedTime = System.currentTimeMillis();
        toast = Toast.makeText(this, "뒤로 버튼을 한번 더 누르시면 종료됩니다.", Toast.LENGTH_LONG);
        toast.show();
        return;
    }
    // 마지막으로 뒤로가기 버튼을 눌렀던 시간에 2.5초를 더해 현재시간과 비교 후
    // 마지막으로 뒤로가기 버튼을 눌렀던 시간이 2.5초가 지나지 않았으면 종료
    if (System.currentTimeMillis() <= backKeyPressedTime + 2500) {
        finish();
        toast.cancel();
        toast = Toast.makeText(this,"이용해 주셔서 감사합니다.",Toast.LENGTH_LONG);
        toast.show();
    }
}
```

**감사합니다.**


---


[홈으로 가기][01]       |[더 많은 android post 보기][03]	|[post 목록 보기][02]
:------:                |:------:                               |:------:
                        |                                       |


[01]: https://atomic0x90.github.io/ "home"
[02]: https://atomic0x90.github.io/posts/ "posts"
[03]: https://atomic0x90.github.io/posts/#android-studio "android posts"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}


