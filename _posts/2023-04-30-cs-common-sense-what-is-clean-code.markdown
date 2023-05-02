---
layout: post
title:  "좋은 코드란?(Clean code, 클린 코드)"
date:   2023-04-30 10:00:00
author: atomic0x90 (Yujun Han)
categories: CS Common-Sense
tags: CS Common-Sense
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

# 좋은 코드란?(Clean code, 클린 코드)

작성, 읽기, 유지 관리가 쉬운 소프트웨어를 생성하는 독자 중심 개발 스타일이다.

---

# 좋은 코드(Clean code, 클린 코드)의 3가지 원칙

1. 일에 대한 적절한 도구를 선택한다. (Choose the right tool for the job)

2. 신호와 잡음의 비율을 최적화 한다. (Optimize the signal-to-noise ratio)

3. 자체적으로 문서화 코드를 작성하려고 노력한다. (Strive to write self-documenting code)

---

# 좋은 코드(Clean code, 클린 코드) 작성법

1. 규칙을 따르기
1. 변수 범위 표시하기
1. 의미를 가지는 이름 만들기
1. 공백을 적절히 사용하기
1. 적절한 주석을 추가하기
1. 자동화를 통해 시간과 공간 절약하기
1. 일반적인 반복문 변수명 사용하기
1. 비슷한 변수들은 같이 묶어서 관리하기
1. 함수를 적극적으로 사용하기
1. 직관적이고 명확하게 만들기

---


## 1. 규칙을 따르기
### (Follow conventions)

규칙을 통해 변수명을 만들면 작업을 명확하게 유지하고 작업을 하고있는 항목을 정확히 알 수 있다.

원칙적으로 정해진 규칙은 없지만, 이미 만들어진 규칙을 따르거나 내가 규칙을 만들어서 모든 코드에 일관성 있게 적용하면 된다.

다음은 변수명에 데이터 유형을 접두사로 붙인 예시이다.

```cpp
int iMyInteger = 10;

char cMyCharacter = 'A';
```

---

## 2. 변수 범위 표시하기
### (Indicate variable scope)

변수를 어디서 사용하는지 명시적으로 지정해서 코드의 가독성과 유지 보수성을 좋게 만든다.

예를 들어 다음과 같이 변수 범위를 표시할 수 있다.

```cpp
class TestClass{
	private:
		//private 변수는 뒤에 _ 를 표시했다.
		int iPrivateVariable_;
	public:
		//public 변수는 일반적인 변수명으로 만들었다.
		int iPublicVariable;
}
```
---

## 3. 의미를 가지는 이름 만들기
### (Say what you mean)

다른 사람이 코드를 봤을 때 함수의 이름, 변수명 등을 오해의 소지가 없고 알기 쉽게 만들어야 한다.

예를 들어
```cpp
int func(int a,int b){
	return a+b;
}

int add(int firstNumber,int secondNumber){
	return firstNumber + secondNumber;
}
```

func, add 함수가 있을 때 기능적으로는 동일한 함수이다.

함수명을 봤을 때 **func**는 어떤 기능을 하는지 알기 어렵고  **add** 는 어떤 기능을 하는지 알기 쉽다.

---

## 4. 공백을 적절히 사용하기
### (Whitespace is nice space)

코드의 가독성을 높이기 위해서 공백을 적절하게 사용해야 한다.

공백을 사용하면 코드의 구조를 더 명확하게 표현할 수 있다.

예를 들어
```cpp
int a=10;
int b=20;
int c=30;지
std::cout<<"Result: "<<c<<std::endl;
```
```cpp
int a = 10;
int b = 20;
int c = 30;
std::cout << "Result: " << c << std::endl;
```

공백이 없는 위 코드보다 공백이 적절하게 있는 아래 코드가 가독성이 높다.

---

## 5. 적절한 주석을 추가하기
### (Commenting saves lives)

코드에 주석을 추가해서 코드를 이해하고 유지 보수가 쉽게 만든다.

하지만 너무 자세한 주석이나 불필요한 주석은 코드를 복잡하게 만들 수 있으므로 피해야 한다.

코드의 변경사항이 생기면 주석도 함께 변경해야 한다.

---

## 6. 자동화를 통해 시간과 공간 절약하기
### (Automate to save time and space)

반복적으로 수행되는 작업을 자동화해서 시간과 공간을 절약할 수 있다.

예를 들어
```cpp
#include <iostream>

using namespace std;

class Calculator{
	public:
		Calculator(int num1, int num2) : num1_{ num1 }, num2_{ num2 } {}

    		int add() const { return num1_ + num2_; }
    		int subtract() const { return num1_ - num2_; }
    		int multiply() const { return num1_ * num2_; }
    		double divide() const { return static_cast<double>(num1_) / num2_; }

	private:
		int num1_;
    		int num2_;
};

int main(){
    Calculator calc( 10, 3 );

    cout << "Add: " << calc.add() << endl;
    cout << "Subtract: " << calc.subtract() << endl;
    cout << "Multiply: " << calc.multiply() << endl;
    cout << "Divide: " << calc.divide() << endl;

    return 0;
}
```

간단한 사칙연산을 하는 Calculator class이다.

반복적으로 직접 사칙연산을 하지 않고 클래스를 호출해서 자동화를 했다.

사칙연산을 하는 클래스라서 굳이 이렇게 해야 하나 의문을 가질 수 있다.

하지만 복잡하고 많은 기능을 하는데 자동화를 하지 않으면 코드의 가독성이 떨어지고,
 코드의 오류 가능성을 높이고, 코드의 재사용이 불가능하다.

---

## 7. 반복문 변수명의 중요성
### (Remember the power of i)

일반적으로 반복문에서 사용하는 변수명은 다음과 같다. **i, j, k ...**

암묵적으로 반복문 변수를 나타내기 때문에 코드의 가독성이 좋아진다.

예를 들어 3차원 배열 **arr\[20\]\[20\]\[20\]**에서 **i, j, k**를 사용하면 반복문에서 **a\[i\]\[j\]\[k\]** 같이 접근하게 된다.

---

## 8. 비슷한 변수들은 같이 묶어서 관리하기
### (Birds of a feather group similar variables together)

비슷한 변수들을 각각 분리해서 작성하면 관리하기 어렵고 변수명을 일일이 관리해야 하기 때문에 코드 가독성이 떨어진다.

따라서 비슷한 변수들을 함께 묶어서 작성하면 코드의 가독성이 높아지고 유지 보수성도 높아진다.

---

## 9. 함수를 적극적으로 사용하기
### (Keep it functional)

기능별로 함수를 구현하면 코드의 가독성, 유지 보수성, 재사용성, 확장성 등을 높일 수 있다.

함수명이 의미하는 기능보다 더 많은 기능을 수행하는 건 피해야 한다.

--- 

## 10. 직관적이고 명확하게 만들기
### (Keep it classy)

코드를 명확하고 직관적이고 간결하게 작성하는 것이 중요하다.

함수나 클래스를 만들 때

1. 기능을 잘 나타내는 이름을 사용한다.
1. 주석을 작성해서 의도를 명확하게 표현한다.
1. 중복 코드를 최소화한다.
1. 구조를 명확하게 유지해야 한다.


**감사합니다.**


---


[홈으로 가기][01]	|[더 많은 CS post 보기][03]         	|[post 목록 보기][02]
:------:                |:------:                               |:------:
                        |                                       |


[01]: https://atomic0x90.github.io/ "home"
[02]: https://atomic0x90.github.io/posts/ "posts"
[03]: https://atomic0x90.github.io/posts/#Cs "CS posts"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}

