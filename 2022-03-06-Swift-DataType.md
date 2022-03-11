---
title: "Swift의 자료형"
categories:
  - TIL
tags:
  - learning
  - 공부 기록
  - Swift
show_date: true
toc: true
toc_sticky: true
toc_label: "👷"
toc_icon: "cog"
---

### Swift의 자료형
[The Swift Programming Languae : Guide](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html)  

먼저 어떤 데이터 타입이 있는지 알아보겠습니다.
Int / Double / Float / Bool / String  
그리고 Collection Type에 Array / Set / Dictionary가 있습니다.

Constants는 변하지 않는 값, 즉 상수입니다. let 키워드를 이용해서 만듭니다.  

```swift
let myConstants = 50
```


Tuple 타입은 하나의 합쳐진 값의 형태로 여러개의 값들을 반환
Optionals 는 "값이 있다. 그리고 그것은 x와 같다." 또는 "값이 없다."를 나타냄  
(Swift의 강력한 features들과 함께 중요하게 사용됨.)

Swift는 type-safe 언어라고 소개한다. Swift는 코드가 사용할 데이터 값의 자료형을 확실히 한다. 코드의 한 부분이 String 타입의 자료형을 원한다고 할 때 Int형의 자료가 실수로 입력되지 않게 해준다. 이렇게 함으로써 개발 과정에서 최대한 빠르게 에러를 잡도록 돕는다.
