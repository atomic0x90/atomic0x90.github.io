---
layout: post
title:  "C++ max_element, min_element 사용법(최댓값,최솟값)"
date:   2021-07-31 10:00:00
author: atomic0x90 (Yujun Han)
categories: C++
tags:  C++
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## max_element, min_element는 언제 사용할까?

어떤 값을 가지는 배열, 벡터, 리스트 등이 있을 때 최댓값(max\_element), 최솟값(min\_element)을 찾을 때 사용한다.

배열, 벡터, 리스트 등에 있는 데이터가 순서가 유의미한 값이라면 값에 대한 정렬을 함부로 하면 안 된다.

이때 최댓값, 최솟값을 찾기 위해 max\_element, min\_element를 사용하게 된다.

물론 정렬을 해도 되는 데이터는 정렬을 통해서 최댓값, 최솟값을 찾는 게 효율적이다.

---

## max_element, min_element header

C++ max\_element, min\_element 함수를 사용하기 위해서는 `algorithm` 을 include 해야 한다.

**예시**
```cpp
#include <algorithm>
```

---

## C++ max_element, min_element 기본 형태

max\_element, min\_element 함수의 기본 형태는 다음과 같다.

1. **max_element(start, end)**를 이용하면 **\[start, end) 범위 중**에 **가장 큰 값**의 **iterator를 반환**한다.
1. **\*max_element(start, end)**를 이용하면 **\[start, end) 범위 중**에 **가장 큰 값**의 **value를 반환**한다.
1. **min_element(start, end)**를 이용하면 **\[start, end) 범위 중**에 **가장 작은 값**의 **iterator를 반환**한다.
1. **\*min_element(start, end)**를 이용하면 **\[start, end) 범위 중**에 **가장 작은 값**의 **value를 반환**한다.


---

## max_element, min_element 기본 형태 예제

**예시**
```cpp
#include <iostream>
#include <array>
#include <vector>
#include <list>
#include <algorithm>

using namespace std;

//array, vector, list 값 설정
array<int,6> ar = {3,4,1,2,6,5};
vector<int> v = {4,5,6,1,2,3,9,8,7};
list<int> li = {2,4,6,8,1,3,5,7};

int main(){
	cout<<"array ar의 값:\t";
	for(int i = 0;i < ar.size();i++)
		cout<<ar[i]<<" ";
	cout<<endl<<endl;

	cout<<"array ar의 최댓값(*max_element) :\t"<<*max_element(ar.begin(),ar.end())<<endl;
        cout<<"array ar의 최솟값(*min_element) :\t"<<*min_element(ar.begin(),ar.end())<<endl;
	cout<<"----------------------------------------"<<endl;


	cout<<"vector v의 값 :\t";
	for(int i = 0;i < v.size();i++)
		cout<<v[i]<<" ";
	cout<<endl<<endl;

	cout<<"vector v의 최댓값(*max_element) :\t"<<*max_element(v.begin(),v.end())<<endl;
        cout<<"vector v의 최솟값(*min_element) :\t"<<*min_element(v.begin(),v.end())<<endl;
	cout<<"----------------------------------------"<<endl;

	cout<<"list li의 값 :\t";
        for(auto iter = li.begin();iter != li.end();iter++)
                cout<<*iter<<" ";
        cout<<endl<<endl;

        cout<<"list li의 최댓값(*max_element) :\t"<<*max_element(li.begin(),li.end())<<endl;
        cout<<"list li의 최솟값(*min_element) :\t"<<*min_element(li.begin(),li.end())<<endl;

	return 0;
}
```

**실행 결과**
```bash
array ar의 값:	3 4 1 2 6 5 

array ar의 최댓값(*max_element) :	6
array ar의 최솟값(*min_element) :	1
----------------------------------------
vector v의 값 :	4 5 6 1 2 3 9 8 7 

vector v의 최댓값(*max_element) :	9
vector v의 최솟값(*min_element) :	1
----------------------------------------
list li의 값 :	2 4 6 8 1 3 5 7 

list li의 최댓값(*max_element) :	8
list li의 최솟값(*min_element) :	1
```

실행 결과에서 알 수 있듯이 max\_element, min\_element 함수에 시작 위치, 끝 위치를 설정하면 최댓값, 최솟값을 얻을 수 있다.

---

## 2차원 vector max_element, min_element 예제

**예시**

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

//vector 값 설정
vector<vector<int>> v = {%raw%}{{1,2},{3,4},{5}}{%endraw%};

int main(){
	cout<<"vector v의 값 :"<<endl;
	for(int i = 0;i < v.size();i++){
		for(int j = 0;j < v[i].size();j++)
			cout<<v[i][j]<<" ";
		cout<<endl;
	}
	cout<<endl;

	for(int i = 0;i < v.size();i++){
		cout<<"vector v ["<<i<<"] 의 최댓값(*max_element) :\t";
		cout<<*max_element(v[i].begin(),v[i].end())<<endl;
		cout<<"vector v ["<<i<<"] 의 최솟값(*min_element) :\t";
		cout<<*min_element(v[i].begin(),v[i].end())<<endl<<endl;
	}

	return 0;
}
```

**실행 결과**
```bash
vector v의 값 :
1 2 
3 4 
5 

vector v [0] 의 최댓값(*max_element) :	2
vector v [0] 의 최솟값(*min_element) :	1

vector v [1] 의 최댓값(*max_element) :	4
vector v [1] 의 최솟값(*min_element) :	3

vector v [2] 의 최댓값(*max_element) :	5
vector v [2] 의 최솟값(*min_element) :	5

```

실행 결과에서 알 수 있듯이 n 차원 vector 값도 범위만 설정하면 최댓값, 최솟값을 구할 수 있다.  
또한 범위가 1일 경우에는 당연히 최댓값, 최솟값이 같다.

**감사합니다.**


---


[홈으로 가기][01]        |[더 많은 C++ post 보기][03]             |[post 목록 보기][02]
:------:                |:------:                               |:------:
                        |                                       |


[01]: https://atomic0x90.github.io/ "home"
[02]: https://atomic0x90.github.io/posts/ "posts"
[03]: https://atomic0x90.github.io/posts/#C++ "C++ post"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}


