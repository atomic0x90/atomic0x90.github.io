---
layout: post
title:  "안드로이드 스튜디오 텍스트 뷰 정렬(android studio textview alignment)"
date:   2020-03-04 10:01:00
author: atomic0x90 (Yujun Han)
categories: android-studio
tags:  android-studio
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## 안드로이드 텍스트 정렬(android text alignment)

안드로이드 스튜디오의 TextView에 들어있는 text를 정렬하는 방법은 다음과 같다.

1. xml 파일에 정렬하고 싶은 TextView를 찾는다.
1. 해당 TextView에 다음 코드를 삽입한다.
  + 가운데 정렬 : android:gravity="center"
  + 왼쪽 정렬   : android:gravity="left"
  + 오른쪽 정렬 : android:gravity="righr"

**예시**

```
<TextView
        android:id="@+id/TEST"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="TEST"
        android:textAppearance="@style/TextAppearance.AppCompat.Display2"
        android:textColor="@color/text" 

	//작성
        android:gravity="center"
/>
```

---

## 안드로이드 레이아웃 정렬(android layout alignment)

안드로이드 스튜디오의 레이아웃 자체를 정렬하는 방법은 다음과 같다.

1. xml 파일에 정렬하고 싶은 layout을 찾는다.
1. 해당 layout에 다음 코드를 삽입한다.
  + 가운데 정렬 : android:layout_gravity="center"
  + 왼쪽 정렬 : android:layout_gravity="left"
  + 오른쪽 정렬 : android:layout_gravity="right"



**예시**

```
<TextView
        android:id="@+id/TEST"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="TEST"
        android:textAppearance="@style/TextAppearance.AppCompat.Display2"
        android:textColor="@color/text"         

        //작성  
        android:layout_gravity="center"
/>
```


텍스트와 레이아웃을 동시에 정렬해도 된다.

**예시**

```
<TextView
        android:id="@+id/TEST"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="TEST"
        android:textAppearance="@style/TextAppearance.AppCompat.Display2"
        android:textColor="@color/text"

        //작성
	android:gravity="left"
        android:layout_gravity="center"
/>
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










