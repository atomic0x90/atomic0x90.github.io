---
layout: post
title:  "출력 함수(printf)와 형식 지정자(format specifiers) ..작성중"
date:   2019-06-04 14:54:01
author: atomic0x90 (Yujun Han)
categories: C-Language
tags:  C-Language
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## 출력 함수(printf)란?

화면에 무언가를 출력하기 위한 함수이다. 
출력 함수는 프로그램 사용하는 사람이 무엇을 해야 하는지 알려주는 역할이다.
정수, 실수, 문자, 문자열 등의 데이터를 다양한 형태로 화면에 출력할 수 있다.

---

## 형식 지정자(format specifiers)란?

데이터들은 각자 다른 형태로 존재한다. 이러한 다양한 데이터들을 화면에 출력하기 위해서 각각 형식 지정자들이 있다. 
데이터에 알맞지 않는 형태의 형식 지정자를 사용하면 오류가 발생한다.

---

## 형식 지정자 문법

```
% [매개 변수] [플래그] [너비] [.정밀도] [길이] 유형
```

---

## 형식 지정자의 종류


형식 지정자	|의미				|예시				|실행 결과
:------:	|:------:			|:------:			|:------:
%d, %i		|10진 정수			|printf("%d %i",-20,12);	|-20 12
%u		|양의 10진 정수			|printf("%u",12);		|12
%o		|양의 8진 정수			|printf("%o",19);		|23
%x, %X		|양의 16진 정수(대 소문자)	|printf("%x %X",14,14);		|e E
%lu		|unsigned long			|printf("%lu",100);		|100
%ld		|signed long			|printf("%ld",1000);		|1000
%llu		|unsigned long long		|printf("%llu",144);		|144
%lld		|signed long long		|printf("%lld",169);		|169













{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}