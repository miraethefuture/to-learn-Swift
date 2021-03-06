---
title: "Navigating Apps: Date Planner"
categories:
  - TIL
tags:
  - learning
  - ๊ณต๋ถ ๊ธฐ๋ก
  - Swift
  - Sample Apps Tutorials
show_date: true
toc: true
toc_sticky: true
toc_label: "๐"
toc_icon: "kiwi-bird"
---

[Sample Apps Tutorials: About Me(Navigating Apps)](https://developer.apple.com/tutorials/sample-apps/aboutme)  
<sub>์๋ ๋ชจ๋  ์ ๋ณด์ ์ถ์ฒ๋ apple developer ๊ณต์ ํ์ด์ง์ด๋ฉฐ ๊ฐ์ธ์ ํ์ต ์ฉ๋๋ก๋ง ์ฌ์ฉ๋์์์ ๋ฐํ๋๋ค.</sub>

๐ค Date Planner ์ฑ์ ๋ ์ง๋ณ๋ก ์ด๋ฒคํธ๋ฅผ ๊ณํํ๊ณ  ์ ๋ฆฌํ๋ ์ฑ์๋๋ค.  
์ด ํํ ๋ฆฌ์ผ์์๋ list, ๊ทธ๋ฆฌ๊ณ  ์ด๋ฒคํธ๋ฅผ ๋ณด์ฌ์ค ๋์  ๋ฆฌ์คํธ๋ฅผ ์์ฑํ๊ธฐ ์ํด observable data model์ ๋ํด ๋ฐฐ์๋๋ค.

# Section 1: App Configuration

  ์ฑ์ด ํ๋์ ๋ฐ์ดํฐ ๊ฐ์ฒด๋ฅผ ์์ฑํ๊ณ  ๊ทธ๊ฒ์ ์ ์ฒด ๋ทฐ ๊ณ์ธต์์ ์ฌ์ฉ ๊ฐ๋ฅํ๋๋ก ํจ์ผ๋ก์จ views๋ค ์ฌ์ด์์ ๋ฐ์ดํฐ๋ฅผ ๊ณต์ ํ๋ ๋ฐฉ์์ ๋ํด ์์๋ด๋๋ค.

## DatePlannerApp.swift  

  ```swift
  // DatePlannerApp.swift

  import SwiftUI

  @main
  struct DatePlannerApp: App {
      @StateObject private var eventData = EventData()

    var body: some Scene {
      WindowGroup {
        NavigationView {
            EventList()
            // ๋ ๋์ ํ๋ฉด์ ์ฌ์ฉํ  ๋ (iPad์ ๊ฐ๋ก ์ ์ฒด ํ๋ฉด ๋ฑ) ํ์ํ ์์          
            // ํ๋ฉด์ด ๋๋์ด์ก์ ๋ ๋น ํ๋ฉด์ placeholder๋ก Text view์ ๋ด์ฉ์ด ๋ํ๋จ
            // ๋ฆฌ์คํธ์ ์์ดํ์ ์ ํํ๋ฉด ํด๋น ์ด๋ฒคํธ ๋ทฐ๋ก ๋ฐ๋๊ฒ ๋จ
            Text("Select an Event")
                .foregroundStyle(.secondary)
        }
        .environmentObject(eventData)
      }
    }
  }
  ```
### NavigationView

  - views๋ฅผ ์ด๋ํ๊ธฐ ์ํด ์ฑ์ top-level view์ NavigationView๋ฅผ ์์ฑํฉ๋๋ค.
  - NavigationView ์๋์๋ ์ฑ์ home view๊ฐ ์์ฑ๋ฉ๋๋ค.
  - ์ด ์ฑ์ ์ฒซํ๋ฉด์ด์ home view๋ EventList() ์๋๋ค.
  - iPad์ ๊ฐ๋ก ํ๋ฉด๊ณผ ๊ฐ์ ๋ ๋์ ์ฑํ๋ฉด ๊ตฌ์ฑ์์, SwiftUI๋ NavigationView๋ฅผ ์ด์ฉํ  ๋ ์ฌ๋ฌ๊ฐ์ ์ปจํ์ธ ๋ฅผ ํ๋์ ์คํ์ด ์๋ ๋๋ํ ํ๋ค๋ก ํ๋ฉด์ ๋ํ๋๋๋ค. ์ด ์ฑ์์ EventList๋ ํ๋์ sidebar column์ ๋ํ๋ฉ๋๋ค. ๊ฐ ์ปจํ์ธ ๋ primary pane์ ๋ํ๋ฉ๋๋ค.

### var eventData  

  ```swift
  @StateObject private var eventData = EventData()
  ```

  ์ด ์ฑ์ eventData๋ผ๋ ์ด๋ฆ์ ๋ณ์์ ๋ฐ์ดํฐ๋ฅผ ์ ์ฅํฉ๋๋ค. eventData ๋ณ์๋ @StateObject wrapper์ ํจ๊ป observable object์ธ EventData์ instance๋ฅผ ๋ง๋ญ๋๋ค. SwiftUI๋ observable object์ ์ผ์ด๋๋ ๋ณํ๋ฅผ ์ถ์ ํฉ๋๋ค. ๋ง์ฝ ๋ณํ๊ฐ ์๊ธฐ๋ฉด SwiftUI๊ฐ ์๋์ผ๋ก ์ด object๋ฅผ ์ฌ์ฉํ๋ view๋ฅผ ์๋ฐ์ดํธ ํฉ๋๋ค.


  ```swift
  } // NavigationView ๋
  .environmentObject(eventData)
  ```

  eventData๋ฅผ ์ ์ฒด view ๊ณ์ธต์์ ์ฌ์ฉํ๊ธฐ ์ํด์ .environmentObject์ eventData instance๋ฅผ ์ฌ์ฉํฉ๋๋ค. ์ด๊ฒ์ ์ฌ์ฉํ๋ฏ๋ก์จ ์ฑ์ ๋ชจ๋  navigation view์ child views๋ค ๊ทธ๋ฆฌ๊ณ  child view์ child view๊น์ง ์ด ๋ฐ์ดํฐ๋ฅผ ์ฌ์ฉํ  ์ ์๊ฒ ๋ฉ๋๋ค.

# Section 2: Event Model  

  ์๋์์ Event model์ ์ด๋ฒคํธ๋ฅผ ๊ตฌ์ฑํ๊ณ  ์๊ฐํํ๊ธฐ ์ํด ํ์ํ ๋ชจ๋  ๋ฐ์ดํฐ๋ฅผ ๊ฐ์ง๊ณ  ์์ต๋๋ค.  
  Event ๋ชจ๋ธ์ ๊ตฌ์ฑํ๋ ๋ฐฉ๋ฒ์ ๋ํด ์์๋ด๋๋ค.

## Event.swift  

  ```swift  
  // Event.swift

  import SwiftUI

  struct Event: Identifiable, Hashable {
    var id = UUID()
    var symbol: String = EventSymbols.randomName()
    var color: Color = ColorOptions.random()
    var title = ""
    var tasks = [EventTask(text: "")]
    var date = Date()

    var remainingTaskCount: Int {
        tasks.filter { !$0.isCompleted }.count
    }

    var isComplete: Bool {
        tasks.allSatisfy { $0.isCompleted }
    }

    var isPast: Bool {
        date < Date.now
    }

    var isWithinSevenDays: Bool {
        !isPast && date < Date.now.sevenDaysOut
    }

    var isWithinSevenToThirtyDays: Bool {
        !isPast && !isWithinSevenDays && date < Date.now.thirtyDaysOut
    }

    var isDistant: Bool {
        date >= Date().thirtyDaysOut
    }

  }

  ```

  Event planner๋ ๋ฐ์ดํฐ๋ฅผ ๋ถ๋ฅ, ๊ตฌ์ฑํ๊ธฐ ์ํด์ ์ฌ๋ฌ๊ฐ์ Event object์ ๋ชจ์(collection)์ ์ฌ์ฉํฉ๋๋ค. ๊ฐ๊ฐ์ Event object๋ ์บ ํ, ์ฌํ, ์์ผํํฐ์ ๊ฐ์ ํน์  ์ด๋ฒคํธ๋ฅผ ๋ํ๋๋๋ค.

  - **Identifiable protocol**์ ์ด๋ฒคํธ์ ๋ฆฌ์คํธ๋ฅผ ์์ฑํ  ๋ SwiftUI๊ฐ ์ด๋ฒคํธ์ ๊ฐ์ ๋ค๋ฅธ ๊ฒ๋ค๊ณผ ํ์คํ ๊ตฌ๋ณํ๊ณ  ๊ทธ๊ฒ์ ์๋ฐ์ดํธ ํ  ์ ์๋๋ก ํฉ๋๋ค.

### ๐ ํ์ ์์ด ๋จ์ด: populate
  <div class="notice">
     <h4>The Event type contains all of the information you need to populate an event.</h4>
     <p>์ปดํจํฐ์์ ๋ฐ์ดํฐ ๋ฒ ์ด์ค๋ ํ์ด๋ธ์ ์ ๋ณด๋ฅผ ์๋ ฅํ๋ ๊ฒ์ ๋งํฉ๋๋ค.</p>
  </div>

### Event Type
  ```swift
  struct Event: Identifiable, Hashable {
    var id = UUID()
    var symbol: String = EventSymbols.randomName()
    var color: Color = ColorOptions.random()
    var title = ""
    var tasks = [EventTast(text: "")]
    var date = Date()
  }
  ```
  Event type์ ํ๋์ ์ด๋ฒคํธ๋ฅผ ๋ง๋ค๊ธฐ ์ํ ๋ชจ๋  ์ ๋ณด๋ฅผ ๊ฐ์ง๊ณ  ์์ต๋๋ค. ์ฌ๋ณผ๊ณผ ์, ์ด๋ฒคํธ์ ์ด๋ฆ, ์ด๋ฒคํธ ์์์ ์ํํด์ผ ํ  tasks์ ๋ ์ง์๋๋ค. task๋ ์ด๋ฒคํธ๋ฅผ ๋๋ฅด๋ฉด to-do ํ์์ผ๋ก ๋ํ๋ฉ๋๋ค.

### Computed properties  

  Stored properties ์๋์๋ computed properties๊ฐ ์์ต๋๋ค. Computed properties๋ ๋ ์ง๋ ์ํํ task ์๋ฅผ ๊ธฐ๋ฐ์ผ๋ก ์ด๋ฒคํธ๋ฅผ ์ ๋ ฌํ  ์ ์๋๋ก ํฉ๋๋ค.

  ```swift  
  var isPast: Bool {
    date < Date.now
  }
  ```
  ์๋ฅผ ๋ค์ด ์์ isPast property๋ ํ์ฌ ๋ ์ง, ์๊ฐ๋ณด๋ค ์ด๋ฒคํธ์ ๋ ์ง ์๊ฐ์ด ์ ์ผ๋ฉด true๋ฅผ ๋ฐํํฉ๋๋ค. ์ด๊ฒ์ ์ด์ฉํด ์ฌ์ฉ์๋ค์ ๊ณผ๊ฑฐ ์ด๋ฒคํธ๋ฅผ ์ํ ์นดํ๊ณ ๋ฆฌ์ ์ง๋ ์ด๋ฒคํธ๋ค์ ๋ชจ์๋ ์ ์์ต๋๋ค.

<!-- ๐ท #### filter(_:)   -->



#### UUID()  

  <sub>[์ฐธ๊ณ ํ ํ์ด์ง](https://www.hackingwithswift.com/books/ios-swiftui/working-with-identifiable-items-in-swiftui)</sub>

  a Universally Unique Identifier์ ์ฝ์์๋๋ค.
  ์ ์ ์ธ view๋ฅผ ๋ง๋ค๋๋ SwiftUI๊ฐ ์ด๋ค ๋ทฐ๋ฅผ ์ฐ๋ฆฌ๊ฐ ์ด์ฉํ๊ณ  ์๋์ง ์๊ณ , ์ฌ๋ฌ๊ฐ์ง ์์์ ํ  ์ ์์ต๋๋ค. ํ์ง๋ง ์ฐ๋ฆฌ๊ฐ ๋์ ์ธ view๋ฅผ ๋ง๋ค๊ธฐ ์ํด์ List๋ ForEch๋ฌธ์ ์ฌ์ฉํ๋ฉด SwiftUI๋ ๊ฐ ์์ดํ๋ค์ ๊ตฌ๋ณํ  ๋ฐฉ๋ฒ์ด ํ์ํด์ง๋๋ค. ์ด๋ ์ฌ์ฉํ  ์ ์๋ ๊ฒ์ด UUID()์๋๋ค.

# Section 3: Event Task  

  ํ๋์ EventTask๋ ํ๋์ to-do ์์ดํ์ ๋ํ๋๋๋ค. ์ด ์ฑํฐ์์๋ ์ด๋ค ๋ฐฉ์์ผ๋ก task ๋ถ๋ถ์ ๊ตฌ์ฑํ๋์ง ์์๋ด๋๋ค.

## EventTask.swift  

  ```swift  
  // EventTask.swift  

  import SwiftUI

  struct EventTask: Identifiable, Hashable {
    var id = UUID()
    var text: String
    var isCompleted = false
    var isNew = false
  }
  ```

  Event type๊ณผ ๋ง์ฐฌ๊ฐ์ง๋ก EventTask type ์ญ์ Identifiable protocol์ ๋ฐ๋ฆ๋๋ค. ์ด๊ฒ์ SwiftUI์ด ๋ฆฌ์คํธ ์ to-do ์์ดํ์ ์ํ๋ฅผ ๊ด๋ฆฌํ๊ณ  ์๋ฐ์ดํธ ํ  ์ ์๋๋ก ํฉ๋๋ค. EventTask type์ id, text, isCompleted, isNew์ ๊ฐ์ to-do ์์ดํ์ ์์ฑ๋ค์ ๊ฐ์ง๊ณ  ์์ต๋๋ค.
  ์ฌ์ฉ์๊ฐ ํ task๋ฅผ ์๋ฃํ๋ค๊ณ  ํ์ํ๋ฉด, isCompleted๋ฅผ true๋ก ์ค์ ํ  ๊ฒ์๋๋ค. ์ด๋ ๊ฒ ํจ์ผ๋ก์จ ์ฑ์ด ๋จ์์๋ task๋ฅผ ์ถ์ ํ  ์ ์๊ฒ ํฉ๋๋ค.

# Section 4: Event Data

  ์ฑ์ ์ด๋ฒคํธ ๋ชฉ๋ก์ ์ ๋ณด๋ฅผ ์ฑ์ฐ๊ธฐ ์ํด observable object์ธ EventData๋ฅผ ์ฌ์ฉํฉ๋๋ค. ์ด ์น์์์๋ ์ด๋ป๊ฒ ๋ฐ์ดํฐ๋ฅผ ๊ตฌ์ฑํ๊ณ  ์๋ฐ์ดํธํ๋์ง ์์๋ด๋๋ค.  

## EventData type  

  ```swift
  // EventData.swift

  import SwiftUI

  class EventData: ObservableObject {
      @Published var events: [Event] = [
          Event(symbol: "gift.fill",
                color: .red,
                title: "Future's Birthday",
                tasks: [EventTask(text: "Wine"),
                        EventTask(text: "Cheese plate"),
                        EventTask(text: "Something too sweet"),
                        ],
                date: Date.roundedHoursFromNow(60 * 60 * 24 8 30)),
          Event(symbol: "theatermasks.fill",
                //์์ ๊ฐ์ ๋ด์ฉ)
      ]
  }
  ```

  - EventData type์ ์ดํ์ ๋ํ๋๋ ๋ชจ๋  ์ด๋ฒคํธ์ ๋ํ ์ ๋ณด๋ฅผ ์ ์ฅํ๊ณ  ์์ ํฉ๋๋ค.
  - ObservableObject protocol์ ๋ฐ๋ฆ๋๋ค. ์ด๊ฒ์ EventData์ ์๋ published values ์ค ์ด๋ค ๊ฒ์๋  ๋ณํ๊ฐ ์ผ์ด๋๋ฉด SwiftUI๊ฐ ๊ทธ values๋ฅผ ์ฌ์ฉํ๊ณ  ์๋ view๋ค(observers)์ ์ฐพ๊ณ  ์๋์ผ๋ก ์๋ฐ์ดํธ ํด์ค๋๋ค.

### events property

  - EventData๋ events๋ผ๋ property๋ฅผ ๊ฐ์ง๊ณ  ์์ต๋๋ค. ์์ ์์์์ ์ด property๋ Eventํ์์ ๊ฐ์ ๊ฐ์ง ๋ฐฐ์ด๋ก ๊ฐ์ด ๋ฏธ๋ฆฌ ์ฑ์์ ธ ์์ต๋๋ค.
  - @Published property wrapper๋ events ๋ฐฐ์ด์ ๋ณํ๊ฐ ์ผ์ด๋ ๋๋ง๋ค SwiftUI๊ฐ ๋ณํ๋ฅผ ์ธ์งํ๊ณ  ๊ทธ ๋ฐฐ์ด์ ์ฌ์ฉํ๋ view๋ค์ ์๋ฐ์ดํธ ํ๊ฒ ํฉ๋๋ค. ์ด๊ฒ์ ๋ฐฐ์ด๋ก๋ถํฐ ์ด๋ฒคํธ๋ฅผ ์ถ๊ฐํ๊ฑฐ๋ ์ญ์ ํ๋ฉด ๋ฐ๋ก UI์ ๋ณด์ฌ์ง๋๋ก ํฉ๋๋ค.

### EventData์ ๋ฉ์๋  

  ```swift
    ] // events ์์ฑ์ ๋ฐฐ์ด ๋๋ถ๋ถ

    func delete(_ event: Event) {
      events.removeAll { $0.id == events.id }
    }

  }
  ```
  ์์ ๋ฉ์๋๋ ์ ํ๋ ์ด๋ฒคํธ์ ๋ชจ๋  ์ ๋ณด๋ฅผ ์ญ์ ํด์ค๋๋ค.

<!-- #### class EventData

  class๋ ์ธ์คํด์ค์ ๊ฐ์ด ๋ณ๊ฒฝ๋๋ฉด ๋ฉ๋ชจ๋ฆฌ์ ์์ฑ๋ ํด๋์ค ์์ฒด์ ๊ฐ๋ ํจ๊ป ๋ฐ๋๊ธฐ ๋๋ฌธ์ class๋ฅผ ์ฌ์ฉํ๋๊ฑธ๊น? -->


<!-- #### removeAll(where:)  

  removeAll(where:) ๋ฉ์๋๋ ๊ธฐ์ค์ ๋ถํฉํ๋ ์งํฉ์ ๋ชจ๋  ์์๋ค์ ์ญ์ ํ๋ ๋ฉ์๋์๋๋ค.
 -->
<!-- ### ๊ถ๊ธํ ๊ฒ

<div class="notice--warning">
๋ฐฐ์ด์ ๋ง์ง๋ง ์์ ๋ค์ ์ , ๊ฐ ์์๊น?
</div> -->

# Section 5: Event List  

  List view๋ฅผ ์ฌ์ฉํ์ฌ ์ฑ์ ์ฃผ์ UI์ธ event list๋ฅผ ๊ทธ๋ฆฌ๋ ๋ฐฉ๋ฒ์ ๋ํด ์์๋ด๋๋ค.

## @EnvironmentObject  

  DatePlannerApp.swift์์ ๊ฐ์ฅ ๋์ ๋ ๋ฒจ์ ๋ค๋น๊ฒ์ด์ ๋ทฐ๋ EventData์ ์ธ์คํด์ค๋ฅผ ํต๊ณผ์ํค๊ธฐ ์ํด .environmentObject modifier๋ฅผ ์ฌ์ฉํฉ๋๋ค. ์ด๊ฒ์ผ๋ก ๋ชจ๋  child views๋ ์ธ์คํด์ค์ ์ฝ๊ฒ ์ ๊ทผํ  ์ ์๊ฒ ๋ฉ๋๋ค.  

  ```swift
  // EventList.swift

  import SwiftUI

  struct EventList: View {
      @EnvironmentObject var eventData: EventData
      //...
  }
  ```

  Child view์ธ EventList์์ @EnvironmentObject property wrapper๋ฅผ ์ฌ์ฉ, EventData type์ ์ฃผ์ด ๋ณ์๋ฅผ ์ ์ํจ์ผ๋ก์จ EventData ์ธ์คํด์ค์ data์ ์ ๊ทผํ  ์ ์๊ฒ ๋ฉ๋๋ค.  

## List view  

  ๋ชฉ๋ก์ ์์ฑํ๊ธฐ ์ํด List view๋ฅผ ์ฌ์ฉํ๊ณ  ForEach loop๋ฅผ ์ฌ์ฉํด์ ์์์ ์ค์ ํ ๋ชจ๋  ์๊ฐ๋๋ฅผ ๊ธฐ์ค์ผ๋ก ๋ฐ๋ณตํฉ๋๋ค. (nextSevenDays, nextThirtyDays, future, past)
