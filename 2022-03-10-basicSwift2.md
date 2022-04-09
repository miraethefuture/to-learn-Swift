---
title: "A Swift Tour : 디지털 시계 앱을 만들며 스위프트 배워보기"
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
header:
  teaser: /assets/images/yourDigitalClock.png
---

### 💭 ..    
<div class="notice">
  <h4>Swift는 어떤 언어일까?</h4>
  <p>디지털시계 앱을 만들며 Swift의 기초적인 것들을 알아봅니다.</p>
</div>

<!-- Java를 공부한지 거의 5개월이 지났다. 국비수업 2개월 + 독학 3개월의 과정을 지났다. Java는 첫인상 보다는 매력있고 재미있는 언어였다.
가장 많이 사용되는 프로그래밍 언어 중 하나라 자료가 넘치도록 많다는 장점도 가지고 있다. 그러던 중 친구를 통해 Swift의 존재를 알게되었다.
원래 그 이름은 들어봤지만 Swift가 프로그래밍 언어인지 IDE인지 모를정도로 잘 알지 못했다. 그렇게 Swift에 대한 정보는 '잘 알지 못함'에서 '애플 개발자들이 사용하는 언어'로 승급했다.  -->


<center><video src="https://user-images.githubusercontent.com/85061148/159151492-81fcd9d7-b468-460c-ad3a-f7f196d21755.mov" controls="controls" style="max-width: 600px">
</video></center>

### 1. ContentView와 ContentView_Previews
[Intro to SwiftUI: Digital Clock](https://medium.com/iu-women-in-computing/intro-to-swiftui-digital-clock-d0a60e05d394) <- 블로그의 글을 보며 공부합니다.

```swift
//  ContentView.swift
//  Your Digital Clock

import SwiftUI

struct ContentView: View {
    @State var date = Date()
    var body: some View {

        ZStack {
            Image("unsplash-photo")
            .resizable()
            .scaledToFill()
            .ignoresSafeArea()

        VStack {
             Text("\(timeString(date: date))")
                 .font(.system(size: 160))
                 .fontWeight(.bold)
                 .foregroundColor(Color.white)
                 .onAppear(perform: {let _ = self.updateTimer})
                // 여기 이해 안됨. date: date

             Text("\(greeting())")
                 .font(.system(size: 75))
                 .foregroundColor(Color.white)

             Text("\(dateString(date: date))")
                 .font(.system(size: 20))
                 .foregroundColor(Color.white)
                 .onAppear(perform: {let _ = self.updateTimer})
                 .offset(y: 100)
               } // VStack
           } // ZStack
       } // body


    // ContentView structure
    var timeFormat: DateFormatter {
        let formatter = DateFormatter()
        formatter.dateFormat = "hh:mm:ss a"
        return formatter
    } // 시간 부분 Formatter

    var dateFormat: DateFormatter {
        let formatter = DateFormatter()
        formatter.dateFormat = "yyyy/MM/dd EEEE"
        return formatter
    }

    func timeString(date: Date) -> String {
        let time = timeFormat.string(from: date)
        return time
    }

    func dateString(date: Date) -> String {
        let time = dateFormat.string(from: date)
        return time
    }


    var updateTimer: Timer {
        Timer.scheduledTimer(withTimeInterval: 1, repeats: true, block: { _ in
            self.date = Date()
        })
    } // timeInterval 마다 블락 안의 코드가 실행됨

    func greeting() -> String {
        var greet = ""

        let midNight0 = Calendar.current.date(bySettingHour: 0, minute: 00, second:00, of: date)!
        let nightEnd = Calendar.current.date(bySettingHour: 3, minute: 59, second: 59, of: date)!

        let morningStart = Calendar.current.date(bySettingHour: 4, minute: 00, second: 0, of: date)!
        let morningEnd = Calendar.current.date(bySettingHour: 11, minute: 59, second: 59, of: date)!

        let noonStart = Calendar.current.date(bySettingHour: 12, minute: 00, second: 00, of: date)!
        let noonEnd = Calendar.current.date(bySettingHour: 16, minute: 59, second: 59, of: date)!

        let eveStart = Calendar.current.date(bySettingHour: 17, minute: 00, second: 00, of: date)!
        let eveEnd = Calendar.current.date(bySettingHour: 20, minute: 59, second: 59, of: date)!

        let nightStart = Calendar.current.date(bySettingHour: 21, minute: 00, second: 00, of: date)!
        let midNight24 = Calendar.current.date(bySettingHour: 23, minute: 59, second: 59, of: date)!

        if ((date >= midNight0) && (date <= nightEnd)) {
            greet = "Good Night"
        } else if (date >= morningStart) && (date <= morningEnd) {
            greet = "Good Morning"
        } else if ((date >= noonStart) && (noonEnd >= date)) {
            greet = "Good Afternoon"
        } else if ((date >= eveStart) && (eveEnd >= date)) {
            greet = "Good Evening"
        } else if ((date >= nightStart) && (midNight24 >= date)) {
            greet = "Good Night"
        }

        return greet

    } // func greeting

} // ContentView 끝


struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
        .previewInterfaceOrientation(.landscapeLeft)
    }
}
```
Xcode에서 처음 프로젝트를 열면 ContentView 그리고 ContentView_Previews라는 이름을 가진 두개의 structure가 기본적으로 생성되어 있습니다. 이 글에서는 이 두가지의 structure를 이용하여 간단한 디지털 시계앱을 만들어보며 시간/날짜 정보를 불러오는 방법에 대해 알아보겠습니다.

<code>ContentView: View</code>와 <code>var body: some View</code>에서 View는 이 structure가 View protocol을 따를 것이라는 의미입니다. Protocol은 요구사항을 가지고 있습니다. View 프로토콜의 가장 주요한 요구사항은 body property가 있어야 한다는 것입니다.

body property 부분에는 스크린에 나타날 view들이 작성됩니다. 이때의 view는 프로토콜 view가 아닌 Text view, Image view, Button view와 같은 SwiftUI의 built-in view 또는 외부 프레임의 view들을 말합니다. 위 코드에서는 ZStack의 하위에 Image view와 VStack이, 그리고 VStack 하위에는 Text view가 body property 안에 작성되었습니다.

### 2. 현재 날짜와 시간 정보 가져오기  

```swift
struct ContentView: View {
  @State var date = Date()
}
```

- '@State' property wrapper는 해당 변수가 모니터링 되고 있다는 것을 의미합니다.

- 'Date()'는 사용자가 있는 지역의 날짜와 시간 정보를 가져옵니다.

```swift
import SwiftUI

struct ContentView: View {
    @State var date = Date()
    var body: some View {
        VStack {
          Text("\(date)")
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```

시간 정보는 초마다 계속해서 바뀌므로 property wrapper인 @State 를 사용해서 바뀐 시간을 계속해서 업데이트, 반영해 주고 문자열 date에 escape character \ 를 추가해서 Date()를 담고 있는 date 변수의 할당되어 있는 정보를 문자열로 가져옵니다.


### 3. DateFormatter
```swift
import SwiftUI

struct dateString: View {
    @State var date = Date()
    var body: some View {
        Text("\(date)")
    }
}

struct dateString_Previews: PreviewProvider {
    static var previews: some View {
        dateString()
    }
}
```

위 코드로 가져온 날짜/시간 데이터를 화면에 출력해봅니다. 아직 형식을 지정해주지 않았기 때문에 아래 사진처럼 보여집니다. 날짜, 시간, 분이라는 정보가 포함되어 있지 않고 나열된 문자열로써 나타납니다.

<img src="/assets/images/date_original.png" alt="date_original" width="550">

시간 부분의 형식을 먼저 지정해보겠습니다.

```swift
var timeFormat: DateFormatter {
  let formatter = DateFormatter()
  formatter.dateFormat = "hh:mm:ss a"
  return formatter
}
```

**DateFormatter**는 시간/날짜 데이터를 문자열 형식으로 보여지게 하는 Class입니다. dateFormat은 DateFormatter Class의 instance property입니다. 데이터를 받은 사람이 사용할 수 있는 날짜/시간 데이터의 형식 중 하나입니다.
- hh - 12시간 표기법 시간
- mm -  분
- ss -  초
- a - am/pm

그 다음으로는 가져온 시간 데이터를 문자열로 바꿔주는 function을 작성해봅니다.  
```swift
func timeString(date: Date) -> String {
  let time = timeFormat.string(from: date)
  return time
}
```

### 여기까지 수정 👷


### 4. Live Time  


SwiftUI가 State variable에 일어난 변화들을 감시합니다. @State는 스스로 변화를 만들지는 않습니다.  
Date() initializer는 시간의 한 지점을 가져옵니다. 우리가 방금 만든 디지털 시계가 자동으로 흘러가지 않는 이유이죠.

우리가 보는 시계들처럼 초가 흘러가고 60초가 지나면 1분이 늘어나게 만드려면 매초마다 date variable을 새로 고침해주어야 합니다.  
그러려면 Timer 객체를 사용하면 됩니다. Timer는 일정 시간이 지나면 특정 메세지를 타겟 객체에 보냅니다. Timer을 설정해주면
SwiftUI가 @State의 변화를 인식하고 그것에 따라 우리의 시계를 업데이트 해줄 것입니다.

 Timer 객체를 생성하는 코드를 작성해봅니다.

```swift
var updateTimer: Timer {
  Timer.scheduledTimer(withTimeInterval; 1, repeats: true,
    block: {
      self.date = Date()
      })  
}

```  
scheduledTimer() 메서드를 이용합니다. 첫번째 인자는 withTimeInterval이고 시간의 간격을 입력해줍니다.  
두번째는 repeat 입니다. 반복할 것인지 아닌지 bool 타입으로 입력해줍니다.  
세번째는 block 입니다. Timer가 반복될 때마다 작동될 코드를 작성해줍니다.

아직은 초마다 시계가 움직이지 않죠? 한 단계가 더 남아있습니다. Text View 아래에 .onAppear modifier을 사용하여
Timer가 스크린에 나타나도록 해줍니다.

```swift
Text("\(timeString(date: date))")
  .onAppear(perform: {let _ = self.updateTimer})
```

.onAppear(perform: action) 은 function modifier 입니다. View가 나타나면 action을 수행합니다.
self.updateTimer function은 저장할 필요가 없는 값을 반환하기 때문에 'let _'을 사용했습니다. underscore 는 아무것도 할당하고 싶지 않다는 것을 나타냅니다.
이 스텝까지 잘 마치셨다면 디지털 시계가 초마다 움직이는 것을 볼 수 있을 것입니다!



### 5. Time of Day Greeting  

시간에 따라 달라지는 인사말을 추가해볼 것입니다.
- 4:00:00am to 11:59:59am -> Morning
- 12:00:00pm to 4:59:59pm -> Afternoon
- 5:00:00pm to 8:59:59pm -> Evening
- 8:00:00pm to 3:59:59am -> Night  
위의 기준으로 시간을 나누고 각 시간대의 인사말이 시계 아래에 나타나도록 해봅시다.

```swift
func greeting() -> String {
        var greet = ""

        let midNight0 = Calendar.current.date(bySettingHour: 0, minute: 00, second:00, of: date)!
        let nightEnd = Calendar.current.date(bySettingHour: 3, minute: 59, second: 59, of: date)!

        let morningStart = Calendar.current.date(bySettingHour: 4, minute: 00, second: 0, of: date)!
        let morningEnd = Calendar.current.date(bySettingHour: 11, minute: 59, second: 59, of: date)!

        let noonStart = Calendar.current.date(bySettingHour: 12, minute: 00, second: 00, of: date)!
        let noonEnd = Calendar.current.date(bySettingHour: 16, minute: 59, second: 59, of: date)!

        let eveStart = Calendar.current.date(bySettingHour: 17, minute: 00, second: 00, of: date)!
        let eveEnd = Calendar.current.date(bySettingHour: 20, minute: 59, second: 59, of: date)!

        let nightStart = Calendar.current.date(bySettingHour: 21, minute: 00, second: 00, of: date)!
        let midNight24 = Calendar.current.date(bySettingHour: 23, minute: 59, second: 59, of: date)!

        if ((date >= midNight0) && (date <= nightEnd)) {
            greet = "Good Night."
        } else if (date >= morningStart) && (date <= morningEnd) {
            greet = "Good Morning"
        } else if ((date >= noonStart) && (noonEnd >= date)) {
            greet = "Good Afternoon."
        } else if ((date >= eveStart) && (eveEnd >= date)) {
            greet = "Good Evening."
        } else if ((date >= nightStart) && (midNight24 >= date)) {
            greet = "Good night."
        }

        return greet

    }
```


Calendar.current.date(bySettingHour...) 메서드는 주어진 date 데이터에 특정한 시간을 나타내는 variable을 만듭니다.
여기서는 우리가 위에서 만든 @State date가 주어진 날짜 데이터입니다.

아래 부분은 나누어 놓은 시간대와 현재 시간을 비교하는 부분입니다.
현재 시간과 비교해서 해당되는 인사말을 greet 변수에 담고 반환합니다.
여기까지 하면 시간을 스크린에 띄우는 것은 완성!

... 디지털시계 만들기는 계속 됩니다.

<center><video src="https://user-images.githubusercontent.com/85061148/158997210-efaac4ad-797a-4da4-9039-5e5a123a39e9.mov" controls="controls" style="max-width: 600px">
</video></center>
<!--
### 8. 이제부터는 화면을 꾸며보자.  

시계의 배경 부분을 사진을 넣어 사용할 수 있었으면 좋겠다는 생각이 들었다.  
검색 중 Unsplash API를 발견했고 적용해보고자 한다. -->
