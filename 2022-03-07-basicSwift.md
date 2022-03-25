---
title: "Swift"
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

### 💭 ..  
<div class="notice">
  <h4>Swift를 배워보자.</h4>
  <p>유투브 튜토리얼, 애플 개발자 페이지의 튜토리얼, 구글링을 통해 Swift를 공부해보려고 합니다.<br>    
  그 과정에서 기록이 필요한 것들을 정리해봅니다.</p>
</div>


### View에 대해 조사해보자.  
애플 공식 문서 중 [Declaring a Custom View](https://developer.apple.com/documentation/swiftui/declaring-a-custom-view) 를 보며 알아봅니다.  

컴퓨터 프로그래밍 분야에서 'Declare'는 어떤 의미로 사용될까요?
a declaration은 변수와 같은 요소들의 이름과 데이터 타입을 결정하여 컴파일러에게 알려주는 것을 의미합니다. Declaring a Custom View는 Custom View의 이름을 정의하고 데이터 타입을 정하는 것이겠네요. Definition은 변수나 요소가 어디에 저장될지를 정하는 것입니다. (그 어디는 메모리일 가능성이 높겠죠?)

views를 선언(declaring)하는 방법으로 간단하게 user interface를 묘사할 수 있습니다.  
a hirarchy에 Text, Image, Button과 같은 뷰들을 선언하므로서 간단하게 user interface를 묘사할 수 있습니다. hirarchy는 계층인데요. VStack 아래에 views들이 있고 view들에는 적용된 modifier들이 있죠 그것들을 하나의 hirarchy라고 하는 것 같습니다. <s>(추론을 통한 뇌피셜;)</s>
이제 SwiftUI가 사용자로부터 받은 input이나 데이터의 변화등에 응답할 view들을 화면에 그리고 업데이트합니다.

SwiftUI가 제공하는 built-in view와 다른 view들을 함께 혼합해서 사용할 수 있습니다. modifier를 이용해서 뷰를 배치하고 data 모델에 연결할 수 있습니다. 그리고 custom view들을 화면에 보여지는 앱 뷰에 놓으면 됩니다.

```swift
struct MyView: View { // <- View Protocol 입니다.

}
```
View Protocol을 따르는 structure를 정의 했습니다.  
View protocol은 기능의 청사진을 제공합니다. 이 경우에는 SwiftUI가 화면에 그릴 각 요소들의 작동하는 방식을 제공합니다.

custom view를 view hirarchy에 포함되게 하려면 View protocol이 요구하는 몇가지 사항들을 충족시켜야 합니다.

View protocol의 주요구사항은 body computed property를 꼭 정의해주어야 한다는 것입니다.


미완성 포스팅..계속됩니다.












<!-- Protocol인 View와 Text, Image, Button 같은 SwiftUI built-in View, SwiftUI built-in view가 아닌 다른 framework의 view.  


아래는 두번째 의미의 View중 하나인 Text를 나타내는 코드입니다. foregroundColor라는 modifier에 파라미터로 .red를 주어 글씨색이 빨간색으로 보이게 해주었습니다.
```swift
Text("Hello, World!")
    .foregroundColor(.red) //Hello, World의 글자색이 빨간색으로 보여지게 하는 modifier 메서드

### Text element 와 padding modifier
<!-- [2021 SwiftUI Tutorial for Beginners (3.5 hour Masterclass)](https://www.youtube.com/watch?v=F2ojC6TNwws&t=1s)   
좋은 강의를 유투브에서 볼 수 있다는 것에 감사하며 들어봅니다.

  {% highlight swift linenos %}
    import SwiftUI

      struct ContentView: View {
        var body: some View {

          Text("Hello!").padding()
          //Text는 element padding은 modifier
        }
      }
  {% endhighlight %}   -->



<!-- ### A Source of Truth  

  SwiftUI data flow(데이터의 흐름)은 데이터가 a single source of truth를 가지고 있다는 개념에 기초한다.

  (전역변수와 비슷하게 느껴짐)

  코드의 모든 부분에서 같은 데이터를 사용할 수 있게 해줌.

  SwiftUI앱(SwiftUI 프레임워크를 사용하는 앱???)에서 변화할 수 있는 모든 데이터와 객체들은 a single source of truth를 필요로 한다.

  뷰가 변경하거나 관찰할 수 있도록하는 방식을 필요로 한다.

  poperty wrappers는 변경되기 쉬운 데이터들과 각각의 뷰들이 어떻게 상호작용을 하는지와 관련이 있다. -->
