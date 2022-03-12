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
  <h4>Swift를 배워봅니다.</h4>
  <p> 선택한 튜토리얼들을 보며 전체적으로 한번 훓어보려고 합니다. 그 과정에서 기록이 필요한 것들을 정리해봅니다.</p>
</div>


### 유투브 튜토리얼 & 인프런 강의
[2021 SwiftUI Tutorial for Beginners (3.5 hour Masterclass)](https://www.youtube.com/watch?v=F2ojC6TNwws&t=1s)  
[개발하는 정대리 스위프트 기초 문법](https://www.inflearn.com/course/%EC%A0%95%EB%8C%80%EB%A6%AC-%EC%8A%A4%EC%9C%84%ED%94%84%ED%8A%B8-%EA%B8%B0%EC%B4%88/lecture/96073?tab=curriculum&volume=1.00&speed=1.5)  
  
이런 양질의 자료를 무료로 볼 수 있다는 것에 감사하며 시작!



```swift

    import SwiftUI

      struct ContentView: View {
        var body: some View {

          Text("Hello!").padding()

        }
      }

```

**struct와 class**
struct와 class는 여러개의 데이터들을 한곳에 모아놓은 모델이다. 
메모리에 올려진 struct와 class는 서로다른 방식으로 복사된다.  
struct의 경우 다른 이름의 메모리 공간에 복사되면 원본과 복사본이 서로 연결되지 않는다. 복사본 struct에 변경된 사항들은 원본 struct에 영향을 주지 않는다.
class의 경우에는 복사본과 원본이 서로 연결되어있다. 복사본의 변경사항이 원본에도 똑같이 일어난다. 


```

    import SwiftUI

      struct ContentView: View {
        var body: some View {

          Text("Hello!").padding()

        }
      }

```
