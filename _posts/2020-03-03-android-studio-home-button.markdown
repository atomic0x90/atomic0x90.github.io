---
layout: post
title:  "안드로이드 스튜디오 홈 버튼(android studio home button)"
date:   2020-03-03 10:01:00
author: atomic0x90 (Yujun Han)
categories: android-studio
tags:  android-studio
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## 안드로이드 홈 버튼 리스너 (android home button listener)

안드로이드 기종의 홈 버튼을 누를 때 이벤트를 발생하고 싶으면 다음과 같이 작성한다.

```
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    
	/*
		...
	*/

    }


    // 작성
    @Override
    protected void onUserLeaveHint() {		// 홈 버튼 감지
        super.onUserLeaveHint();

	/*
		이벤트 작성
	*/
    }
}
```


---

## 안드로이드 홈 버튼 앱 종료 방법 (android home button shot down app)

다음과 같은 이벤트를 작성하면 앱이 종료된다.

1. System.exit(0);
1. android.os.Process.killProcess(android.os.Process.myPid());

**예시**

```
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        /*
                ...
        */

    }   


    // 작성
    @Override
    protected void onUserLeaveHint() {          // 홈 버튼 감지
        super.onUserLeaveHint();

        //이벤트 작성
	System.exit(0);

	/*
		System.exit(0);	또는
	android.os.Process.killProcess(android.os.Process.myPid());
	*/
    }
}
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

