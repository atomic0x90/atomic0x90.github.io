---
layout: post
title:  "안드로이드 스튜디오 효과음 재생(android studio soundPool)"
date:   2020-03-01 10:01:00
author: atomic0x90 (Yujun Han)
categories: android-studio
tags:  android-studio
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## 버튼 클릭 시 기본 효과음 제거 방법

1. Button 을 생성한다.
2. .xml 파일에서 기본 효과음을 제거하고 싶은 버튼을 찾는다.
3.  `android:soundEffectsEnabled="false"` 를 삽입한다.

**xml code**
```
<Button
        android:id="@+id/ButtonID"
        android:layout_width="220dp"
        android:layout_height="70dp"
        android:layout_marginTop="7dp"
        android:background="background"
        android:text="Text"
        android:textAppearance="@style/TextAppearance.AppCompat.Large"

        android:textColor="@color/text"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/ButtonID"

        android:soundEffectsEnabled="false"		// 삽입 코드
	/>
```

---

## 안드로이드 soundPool 재생(실행) 방법

1. res 파일에 raw 파일을 생성한다.
1. 효과음 mp3 파일을 raw 파일에 넣는다.
1. 효과음을 실행할 .java 파일에 다음과 같이 코딩한다.

**code**
```
public class MainActivity extends AppCompatActivity {

    //Sound
    SoundPool soundPool;	//작성
    int soundID;		//작성

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);


	//Sound
        soundPool = new SoundPool(5,AudioManager.STREAM_MUSIC,0);	//작성
        soundID = soundPool.load(this,R.raw.click_sound,1);	//작성, (mp3 파일 이름이 click_sound이다.)

	//버튼 클릭시 효과음 실행
	Button button = (Button)findViewById(R.id.ButtonID)	//xml 파일에 버튼 id가 ButtonID이다.
	button.setOnClickListner(new View.OnClickListner() {
		@Override
		public void onClick(View v) {
			soundPool.play(soundID,1f,1f,0,0,1f);	//작성
		}
	});
    }
}
```

이렇게 code를 작성할 때 위의 code의 `R.raw.click_soud` 에서  `raw`가 인식이 안되는 경우가 있다.

그래도 계속 진행하자. 이대로 실행하면

`uses or overrides a deprecated API.`, `Recompile with -Xlint:deprecation for details.`

이러한 경고 메시지가 나온다. 위의 경고 메시지의 의미는 다음과 같다.

**현재 java 버전에서는 사용되지 않는 API를 사용 또는 재정의 하고 있습니다. 따라서 권장되는 API가 아닙니다.**

이 경고를 무시해도 soundPool은 실행이 된다.

~~위의 경고 해결 방법을 공유해 주세요~~


**감사합니다.**


---


[홈으로 가기][01]       |[더 많은 android post 보기][03]        |[post 목록 보기][02]
:------:                |:------:                               |:------:
                        |                                       |


[01]: https://atomic0x90.github.io/ "home"
[02]: https://atomic0x90.github.io/posts/ "posts"
[03]: https://atomic0x90.github.io/posts/#android-studio "android posts"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}


