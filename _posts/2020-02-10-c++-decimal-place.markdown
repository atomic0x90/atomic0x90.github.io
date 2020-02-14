---
layout: post
title:  "C++ 소수점 개수 조절하기"
date:   2020-02-10 10:12:16
author: atomic0x90 (Yujun Han)
categories: C++
tags:   C++
sitemap:
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## C++ (cout) 소수점 개수 조절하기

`cout`을 사용하여 실수를 출력하면 전체 자리수(정수 부분 + 소수점 부분)가 6자리로 고정되어 출력된다.

전체 자리수를 수정하는 방법은 다음과 같다.
```cpp
cout<<fixed;
cout.precision(number);
```

cout.precision(number); 여기서 `number` 자리에 출력하고 싶은 소수점의 자리수를 작성하면 된다.

---

cout 기본 출력

**예시**
```cpp
#include <iostream>

using namespace std;

int main()
{
        double a = 12345.123456789;

        cout<<a<<endl;

        return 0;
}
```

**실행 결과**
```bash
12345.1
```

또한 cout 기본 출력은 정수 부분이 6자리가 넘어가면 소수점 부분은 출력이 안된다.

**예시**
```cpp
#include <iostream>

using namespace std;

int main()
{
        double a = 123456.123456789;

        cout<<a<<endl;

        return 0;
}
```

**실행 결과**
```bash
123456
```

**소수점 자리 고정 예시**
```cpp
#include <iostream>

using namespace std;

int main()
{
        double a = 123456.123456789;

        cout<<fixed;
        cout.precision(7);
 
        cout<<a<<endl;

        return 0;
}
```

**실행 결과**
```bash
123456.1234568
```

실행 결과에서 알 수 있듯이 소수점 자리가 7자리가 출력된다.

또한 123456.1234567 이 출력되는 게 아니라 123456.1234568 이 출력된다.

그 이유는 자신이 설정한 소수점 자리수의 범위 밖의 수를 반올림하여 출력하기 때문이다.



**갑사합니다**

---


[홈으로 가기][01]       |&nbsp;				        |[post 목록 보기][02]
:------:                |:------:                               |:------:
                        |                                       |


[01]: https://atomic0x90.github.io/ "home"
[02]: https://atomic0x90.github.io/posts/ "posts"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}
