---
layout: post
title:  "C++ 출력(cout) 속도 향상하는 방법"
date:   2020-02-12 10:01:00
author: atomic0x90 (Yujun Han)
categories: C++
tags:   C++
sitemap:
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## cout\<\<endl 와 cout\<\<"\n" 속도 비교

`cout<<endl`의 속도가 `cout<<"\n"`의 속도보다 느리다.

따라서 속도 문제에 민감한 경우 `endl` 사용보다 `"\n"` 사용을 권장한다.


---

## ios::sync_with_stdio(false) 사용 방법

일반적으로 C++ 표준 stream 들은 C 표준 stream 과 동기화가 되어있다. 

그래서 우리가 C(printf, scanf) 와 C++(cout, cin) 입출력 방식을 같이 사용할 수 있다. 

하지만 ios::sync_with_stdio(false)를 사용하면 C++ 입출력 stream 들은 `독립적인 공간(buffer)`을 가지게 된다. 
즉, `ios::sync_with_stdio(false)`의 의미는 `C 와 C++의 동기화를 끊겠다`는 것이다. 

동기화를 끊으면 실행되는 공간(buffer)이 줄어들게 되어 `실행 시간이 향상`되게 된다.

**주의할 점** 

ios::sync_with_stdio(false)를 사용하면 `C 입출력 방식을 같이 사용하면 안 된다`.

**예시**
```cpp
#include <iostream>

using namespace std;

int main()
{
        ios::sync_with_stdio(false);

	cout<<"Test"<<end;

        return 0;
}
```

---

## cin.tie(NULL)

일반적으로 cin 과 cout 은 tie 되어있다.

그래서
```cpp
cout<<"ABCD"<<endl;
cin>>a;
```

cin 과 cout이 tie 되어있으면 입력(input) 이 실행되기 전에 출력(output)이 flush(비움) 된다.

하지만 `cin.tie(NULL)`을 사용하면 출력(output)이 flush(비움) 되지 않은 채로 입력(input)이 실행된다.

그래서 "ABCD" 가 출력되지 않는다.

그러므로 `cin.tie(NULL)`을 사용하고 입력을 받기 전에 출력을 하고 싶으면 수동으로 cout을 flush 해야 한다.

**예시**
```cpp
#include <iostream>

using namespace std;

int main()
{
        cin.tie(NULL);

	cout<<"ABCD"<<endl;

        return 0;
}
```


**감사합니다.**

---

[홈으로 가기][01]       |&nbsp;                                 |[post 목록 보기][02]
:------:                |:------:                               |:------:
                        |                                       |


[01]: https://atomic0x90.github.io/ "home"
[02]: https://atomic0x90.github.io/posts/ "posts"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}
















































