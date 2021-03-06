---
title: "iOS App Dev Tutorials: Scrumdinger"
categories:
  - TIL
tags:
  - learning
  - ๊ณต๋ถ ๊ธฐ๋ก
  - Swift
show_date: true
toc: true
toc_sticky: true
toc_label: "๐"
toc_icon: "kiwi-bird"
header:
  teaser: /assets/images/scrum5.png
---

[Getting Started with Scrumdinger](https://developer.apple.com/tutorials/app-dev-training/getting-started-with-scrumdinger)  
<sub>์๋ ๋ชจ๋  ์ ๋ณด์ ์ถ์ฒ๋ apple developer ๊ณต์ ํ์ด์ง์ด๋ฉฐ ๊ฐ์ธ์ ํ์ต ์ฉ๋๋ก๋ง ์ฌ์ฉ๋์์์ ๋ฐํ๋๋ค.  
All information below comes from the official apple developer page and is for personal learning purposes only.</sub>

<sub>์์ด๋ก ์์ฑ๋ ํํ ๋ฆฌ์ผ์ ์ฝ์ผ๋ฉฐ ์ ๋ฆฌํ๋ ๊ฒ์ด๊ธฐ ๋๋ฌธ์ ํ๊ตญ์ด๋ก ์ฝ์์ ๋ ์์ฐ์ค๋ฝ๊ฒ ์ฝํ๋๋ก ๊ด์ฌ 'a'๊ฐ ์๋ต๋ ๋จ์ํ ๋จ์ด๋ค์ด ๋ง์ด ๋ฑ์ฅํฉ๋๋ค.<br><s>์์ฑ์๊ฐ ๋๋ฌด ์ ๊ฒฝ์ฐ์ด๋ ๊ฒใใใ </s></sub>

# ๐ค

  SwiftUI๋ฅผ ์ด์ฉํ ์๋ฒฝํ ๊ธฐ๋ฅ์ ํ๋ ์ฑ์ ๋ง๋ค์ด๋ณด๋ฉฐ iOS ์ฑ ๊ฐ๋ฐ์ ๊ฐ์ฅ ์ค์ํ ๋ถ๋ถ๋ค์ ๋ํด ์์๋ด๋๋ค.  

## Tour of the App

  ๋ง์ ์ํํธ์จ์ด ์์ง๋์ด๋ง ํ๋ค์ด ๊ทธ๋ ์ ์๋ฌด์ ๋ํ ๊ณํ์ ์ง๊ธฐ ์ํด **scrums**๋ผ๊ณ  ์๋ ค์ง daily meeting์ ํฉ๋๋ค. Scrums๋ ๋ฏธํ์ ์ฐธ์ํ ์ฌ๋๋ค์ด ์ด์  ์ด๋ค๋ธ ์ฑ๊ณผ๋ค๊ณผ ์ค๋ ์์ํ  ์ผ, ๊ทธ๋ฆฌ๊ณ  ๊ทธ๋ค์ ์์์ ์ํฅ์ ๋ฏธ์น ์ง๋ ๋ชจ๋ฅด๋ ์ฅ์ ๋ฌผ์ ๋ํ์ฌ ๋ํ๋ฅผ ๋๋๋ ์งง์ ๋ฏธํ์๋๋ค.  

  ์ด ๋ชจ๋์ ์ฌ์ฉ์๋ค์ ๋ฐ์ผ๋ฆฌ scrums์ ๊ด๋ฆฌ๋ฅผ ๋๋ iOS์ฑ์ธ Scrumdinger๋ฅผ ๊ฐ๋ฐํ๋ ๊ณผ์ ์ ์๋ดํฉ๋๋ค.  

  Scrums๊ฐ ์ง์ค๋ ฅ์๊ฒ ์งง์ ์๊ฐ๋์ ์งํ๋  ์ ์๋๋ก Scrumdinger๋ ๋ฏธํ์ ์ฐธ๊ฐํ ์ฌ๋๋ค์ด ์ผ๋งํผ ์ด์ผ๊ธฐํด์ผ ํ๋์ง๋ฅผ ์๊ฐ์ , ์ฒญ๊ฐ์  ์ ํธ๋ฅผ ์ฌ์ฉํด ์๋ ค์ค๋๋ค. ์ด ์ฑ์ ๋ํ ๋จ์ ์๊ฐ์ ์๋ ค์ฃผ๋ ์คํฌ๋ฆฐ์ ์ ๊ณตํฉ๋๋ค.  

## Build Groups of Views

  View๋ UI์ ํ ๋ถ๋ถ์ ์ ์ํฉ๋๋ค. ์ฑ์ ํ ๋ธ๋ฝ์ ๊ตฌ์ฑํฉ๋๋ค. ๊ฐ๋จํ๊ณ  ์์ view๋ค์ ์กฐํฉํ์ฌ ๋ณต์กํ view๋ฅผ ๋ง๋ญ๋๋ค.

### ContentView.swift  

  ๊ธฐ๋ณธ SwiftUI view file์ ๋๊ฐ์ structures๋ฅผ ์ ์ํฉ๋๋ค. ์ฒซ๋ฒ์งธ structure๋ View ํ๋กํ ์ฝ์ ๋ฐ๋ฆ๋๋ค. View ํ๋กํ ์ฝ์ ์กฐ๊ฑด์ ํ๊ฐ์ง๋ก, ํ๋์ view๋ฅผ ๋ฆฌํดํ๋ body property๋ฅผ ๊ฐ์ง๋ ๊ฒ์๋๋ค. Body ์์ฑ ๋ถ๋ถ์๋ view์ content, layout, behavior๋ฅผ ๋ฌ์ฌํฉ๋๋ค. ๋๋ฒ์งธ structure๋ canvas์ ํ๋ฆฌ๋ทฐ๋ฅผ ์ ๊ณตํฉ๋๋ค.

#### Refactor ContentView.swift  

  ContentView์ ์ด๋ฆ ๋ถ๋ถ์ ์ปจํธ๋กค ํด๋ฆญํฉ๋๋ค. Refactor -> Rename์ ํด๋ฆญ ํ ์ด๋ฆ์ ๋ณ๊ฒฝํฉ๋๋ค. (ํ๋ก์ ํธ ๋ค๋น๊ฒ์ดํฐ์์๋ ์ด๋ฆ์ด ๋ณ๊ฒฝ๋ฉ๋๋ค.)

### ProgressView  

  Body ์์ฑ ์์ ProgressView๋ฅผ ์๋น ๋ฐ์ดํฐ์ ํจ๊ป ์์ฑํด์ค๋๋ค. ProgressView๋ ์ผ์  ์๊ฐ์ ์ง๋จ๊ณผ ๋จ์ ์๊ฐ์ ๋ณด์ฌ์ค ์ ์๊ณ , ๋ก๋ฉ๊ณผ ๊ฐ์ ๋จ์ ์๊ฐ์ด ๋ชํํ์ง ์์ ์๊ฐ์ ์ง๋จ๋ ๋ณด์ฌ์ค ์ ์์ต๋๋ค.

  <center><img src="/assets/images/scrum1.png" alt="ProgressView" width="300"></center>

### Command-click "Embed in VStack"  

  ProgressView๋ฅผ Command-click ํ "Embed in VStack"์ ํด๋ฆญํ๋ฉด ProgressView๊ฐ VStack์์ ๋ค์ด์ค๊ฒ ๋ฉ๋๋ค.

### Label  

  <center><img src="/assets/images/scrum2.png" alt="Label" width="700"></center>

  ์ฒซ๋ฒ์งธ Text ์๋์ ๋ผ๋ฒจ์ ํ๋ ๋ง๋ค์ด์ค๋๋ค. ๋ผ๋ฒจ์ ์ ๋ชฉ์ "300"์ด๊ณ  "hourglass.bottomhalf.fill"์ด๋ผ๋ system image๋ฅผ ์ฌ์ฉํ์ต๋๋ค. ์์คํ์ system images๋ฅผ ํฐํธ๋ก ์ทจ๊ธํ๊ธฐ ๋๋ฌธ์ ์ฌ์ฉ์์ ๋๋ฐ์ด์ค ์ธํ์ ๋์ํ์ฌ ํฌ๊ธฐ๋ฅผ ์กฐ์ ํฉ๋๋ค.  

### Alignment  

  <center><img src="/assets/images/scrum3.png" alt="alignment" width="700"></center>  

  Seconds Elapsed์ Seconds Remaining์ ๋ด๊ณ  ์๋ VStack์ ๊ฐ๊ฐ leading, trailing alignment๋ฅผ ์ฃผ๋ฉด ์ผ์ชฝ ์ ๋ ฌ, ์ค๋ฅธ์ชฝ ์ ๋ ฌ ๋ฉ๋๋ค.

### .font(.caption) modifier  

  .font(.caption) modifier๋ Text์ ๊ธ์จ ํฌ๊ธฐ๋ฅผ ์ค์ฌ์ค๋๋ค. SwiftUI์ view๋ฅผ ์ปค์คํฐ๋ง์ด์ฆํ๊ธฐ ์ํด์๋ modifiers๋ผ๋ ๋ฉ์๋๋ฅผ ์ฌ์ฉํฉ๋๋ค. ๊ฐ๊ฐ์ modifier๋ ์๋ก์ด view๋ฅผ ๋ฆฌํดํฉ๋๋ค. ์ฌ๋ฌ๊ฐ์ modifier๋ฅผ ํ view์ ์ ์ฉํ  ์๋ ์์ต๋๋ค.

### Circle()

  ```swift  
  Circle()
      .strokeBorder(lineWidth: 24)
  ```
  ์์ ์ฝ๋๋ฅผ ์์ฑํจ์ผ๋ก์ ๋ปฅ ๋ซ๋ฆฐ 24 ๊ตต๊ธฐ์ ํ๋๋ฆฌ๋ฅผ ๊ฐ์ง ์ํ์ ์คํฌ๋ฆฐ์ ์ถ๋ ฅํ  ์ ์์ต๋๋ค.

## Supplement Accessibility data

  SwiftUI๋ ๋นํธ์ธ accessibility๋ฅผ ๊ฐ์ง๊ณ  ์์ต๋๋ค. ์์ฃผ ์ ์ ์์ ์์์ผ๋ก accessibility๊ฐ ์ฑ์ ์ง์ํ๋๋ก ํ  ์ ์์ต๋๋ค. ์๋ฅผ ๋ค์ด text view์์ ์๋ ๋ฌธ์์ด์ ์๋์ ์ผ๋ก VoiceOver์ ๊ฐ์ ๊ธฐ๋ฅ์ ํ  ์ ์๊ฒ ๋ฉ๋๋ค. ํ์ง๋ง accessibility ๊ธฐ๋ฅ์ ๊ฐํ๋ฅผ ์ํด์ ์ถ๊ฐ์ ์ธ ์์์ ํด์ผ ํ  ๋๋ ์์ต๋๋ค.  

### VoiceOver  

  ๊ธฐ๋ณธ์ ์ผ๋ก VoiceOver๋ system name์ ์ฝ์ด์ค๋๋ค. ์ง๊ธ ๋ง๋ค์ด๋ณด๊ณ  ์๋ ์ด ์ฑ์ header ๋ถ๋ถ์ ์๋ system ์ด๋ฏธ์ง์ ์ด๋ฆ์ ์ฝ์ ๊ฒ์๋๋ค. hourglass.bottomhalf.fill๊ณผ ๊ฐ์ ์ด๋ฆ์ด์ฃ .

  ```swift
  } // systemImage๋ฅผ ์ฌ์ฉํ๋ HStack ๋๋ถ๋ถ
  .accessibilityElement(children: .ignore)
  ```
  ์์ ์ฝ๋๋ฅผ ์์ฑํ์ฌ HStack์ child view์ ์ฌ์ฉ๋ ๊ฑฐ๋ผ ์์๋ accessibility๋ฅผ ๋ฌด์ํด์ค๋๋ค. ์ด๋ฐ ๊ณผ์ ์ ์ฌ์ฉ์๊ฐ ๋ ์ข์ accessibility ๊ฒฝํ์ ํ  ์ ์๋๋ก ํ  ๊ฒ์๋๋ค.

  ```swift  
  } // systemImage๋ฅผ ์ฌ์ฉํ๋ HStack ๋๋ถ๋ถ
  .accessibilityElement(children: .ignore)
  .accessibilityLabel("Time remaining")
  ```
  ์๋ฏธ๊ฐ ์ผ์นํ๋ ์ด๋ฆ์ ์ฌ์ฉํ์ฌ accessibility label์ HStack์ ์ถ๊ฐํด์ค๋๋ค.
  ์ฌ์ฉ์๊ฐ ํด๋น ์์์ ๋ชฉ์ ์ ์ดํดํ  ์ ์๋๋ก ์ด๋ฆ ์ง์ด ์ค๋๋ค. ์ด ๋ถ๋ถ์์๋ system name ๋ณด๋ค๋ VoiceOver ์ฌ์ฉ์๊ฐ ์ดํดํ๊ธฐ ์ฌ์ด ๊ฐ์ฅ ์ค์ํ ์ ๋ณด๋ฅผ ํํํ๋ ๋ฌธ์๋ฅผ ์ถ๊ฐํด์ฃผ์์ต๋๋ค.

  ```swift  
  } // systemImage๋ฅผ ์ฌ์ฉํ๋ HStack ๋๋ถ๋ถ
  .accessibilityElement(children: .ignore)
  .accessibilityLabel("Time remaining")
  .accessibilityValue("10 minutes")
  ```
  Child view์ ๊ฐ์ ์๋์ ์ผ๋ก ๋ฌด์ํด์ฃผ์๊ธฐ ๋๋ฌธ์ ๊ฐ์ ์ถ๊ฐํด์ฃผ์ด์ผ ํฉ๋๋ค.

## Create a Card View

### Create a Color Theme

  - main color: view์ ๋ฐฐ๊ฒฝ์
  - accent color: view์ ๊ธ์จ์

  ์ ์ด์ฉํ์ฌ Color Theme์ ์์ฑํด๋ด๋๋ค.

#### New Group ๋ง๋ค๊ธฐ

  Xcode ๋งจ ์ผ์ชฝ ์๋์ + ๋ฒํผ์ ๋๋ฅด๋ฉด ํ๋ก์ ํธ ๋ค๋น๊ฒ์ดํฐ์ New Group์ ์์ฑํ  ์ ์์ต๋๋ค.
  <center><img src="/assets/images/scrum4.png" alt="New Group" width="500"></center>

### Color properties

  view๋ฅผ ๋ง๋ค ๊ฒ์ ์๋์ง๋ง Color properties๋ฅผ ์ด์ฉํ๊ธฐ ์ํด์ SwiftUI ํ๋ ์์ํฌ๋ฅผ ์ํฌํธ ํด์ค๋๋ค.

  ```swift
  // Theme.swift

  import Foundation
  import SwiftUI

  enum Theme: String {
      case bubblegum
      case buttercup
      case indigo
      case lavender
      case magenta
      case navy
      case orange
      case oxblood
      case periwinkle
      case poppy
      case purple
      case seafoam
      case sky
      case tan
      case teal
      case yellow

      // ๊ฐ main ์ปฌ๋ฌ์ ๋์๋๋ accentColor๋ฅผ ์ค์ ํด์ฃผ๋ property์๋๋ค.
      var accentColor: Color {
          switch self {
              case .bubblegum, .buttercup, .lavender, .orange, .periwinkle, .poppy, .seafoam, .sky, .tan, .teal, .yellow: return .black
              case .indigo, .magenta, .navy, .oxblood, .purple: return .white
          }
      }
      // ์ด enumeration์ rawValue๋ฅผ ์ฌ์ฉํ์ฌ ์์ ์์ฑํ๋ ์์ฑ
      var mainColor: Color {
        Color(rawValue)
      }
  }

  ```

### Create a Daily Scrum Model  

  DailyScrum์ ์ฃผ๋ชฉ์ ์ value data๋ฅผ ๋ณด์ฌ์ฃผ๋ ๊ฒ์ด๊ธฐ ๋๋ฌธ์ struct๋ฅผ ๋ง๋ค์ด value type์ผ๋ก ๋ง๋ค ๊ฒ์๋๋ค.  
  (Models Group์ DailyScrum์ด๋ผ๋ ํ์ผ ์๋ก ๋ง๋ค๊ธฐ ํ struct ์์ฑ)

  ```swift
  struct DailyScrum {
    var title: String
    var attendees: [String]
    var lengthInMinutes: Int
    var theme: Theme
  }
  ```

  ์ํ ๋ฐ์ดํฐ๋ฅผ ์ ๊ณตํ๋ extension์ ์ถ๊ฐํฉ๋๋ค.

  ```swift
  extension DailyScrum {
    static let sampleData: [DailyScrum] =
    [
        DailyScrum(title: "Design", attendees: ["Future", "Anna", "Happ", "OShel"], lengthInMinutes: 10, theme: .yellow),
        DailyScrum(title: "App Dev", attendees: ["Katie", "Gray", "Euna", "Luis", "Darla"], lengthInMinutes: 5, theme: .orange),
        DailyScrum(title: "Web Dev", attendees: ["Chella", "Chris", "Christina", "Eden", "Karla", "Lindsey", "Aga", "Chad", "Jenn", "Sarah"], lengthInMinutes: 5, theme: .poppy)
    ]
  }
  ```

### Create the Card View  

  CardView๋ DailyScrum ๋ชจ๋ธ ๋ฐ์ดํฐ๋ฅผ ์์ฝํ๊ณ  ์ ๋ชฉ, ์ฐธ๊ฐ ์ธ์์, ์๊ฐ์ ๋ณด์ฌ์ค ๊ฒ์๋๋ค. ๋ ์์ views๋ฅผ ์กฐ๋ฆฝํ์ฌ CardView๋ฅผ ๋ง๋ค ๊ฒ์๋๋ค. ๊ฐ๊ฐ์ views๋ DailyScrum structure์ ๋ฐ์ดํฐ ์กฐ๊ฐ์ ํ๋ฉด์ ๋ณด์ฌ์ค ๊ฒ์๋๋ค.

  <!-- ์์ธํ ๋ด์ฉ ๊ธ๋ก ์ ๋ฆฌ ํ  ๊ฒ -->

### Customize the Label Style  

  Scrum length์ clock ์์ด์ฝ์ ์ํ์ผ๋ก ์๊ธฐ ์ํด label style์ ๋ง๋ค์ด ๋ด๋๋ค. LabelStyle ํ๋กํ ์ฝ์ ์ฌ์ฉํ์ฌ ์ฌ๋ฌ๊ฐ์ views์ ๊ฐ์ label style์ ์ฌ์ฌ์ฉํ์ฌ ์ฑ์ ์ ๋ฐ์ ์ธ ๋์์ธ์ ํต์ผ ์ํฌ ์ ์์ต๋๋ค.  

  (๋ง์ฝ ์ปค์คํ ๋ผ๋ฒจ ์คํ์ผ์ ๋ง๋ค๊ณ  ์ถ์ง ์๋ค๋ฉด built-in label styles๋ฅผ ์ฌ์ฉํ  ์ ์์ต๋๋ค.)  

  ```swift
  // TrailingIconLabel.swift

  import SwiftUI

  struct TrailingIconLabelStyle: LabelStyle {
    func makeBody(configuration: Configuration) -> some View {


    }
  }
  ```

  1. TrailingIconLabel๋ผ๋ ์ด๋ฆ์ ์ ์ค์ํํธ ํ์ผ์ ์์ฑํฉ๋๋ค.
  2. LabelStyle ํ๋กํ ์ฝ์ ๋ฐ๋ฅด๋ TrailingIconLabelStyle๋ผ๋ ์ด๋ฆ์ structure๋ฅผ ์์ฑํฉ๋๋ค. (์์ง LabelStyle ํ๋กํ ์ฝ์ ์๊ตฌ์ฌํญ์ ์ถฉ์กฑํ์ง ์๊ธฐ๋๋ฌธ์ ์ปดํ์ผ๋ฌ๊ฐ error๋ฅผ throwํฉ๋๋ค.)
  3. ๋น์ด์๋ makeBody function์ ์์ฑํฉ๋๋ค. (์ด์  ์๋ฌ๊ฐ ์ฌ๋ผ์ง๋๋ค.)

  ์ด ์คํ์ผ์ด ํ์ฌ์ ๋ผ๋ฒจ ์คํ์ผ์ธ ๋ทฐ hierarchy ์์ ๊ฐ๊ฐ์ Label ์ธ์คํด์ค๋ง๋ค ์์คํ์ ์ด ๋ฉ์๋๋ฅผ ํธ์ถํฉ๋๋ค.

  ```swift
  // TrailingIconLabel.swift

  import SwiftUI

  struct TrailingIconLabelStyle: LabelStyle {
    func makeBody(configuration: Configuration) -> some View {
      HStack {
        configuration.title
        configuration.icon
      }
    }
  }
  ```
  ```swift
  // TrailingIconLabel.swift


  import SwiftUI

  struct TrailingIconLabelStyle: LabelStyle {
      func makeBody(configuration: Configuration) -> some View {
          HStack {
              configuration.title
              configuration.icon
              // ์ด ๋ฉ์๋์ ์ฌ์ฉ์ผ๋ก CardView์ ์ค๋ฅธ์ชฝ Label์ title, icon ์์๊ฐ ๋ฐ๋
          }
      }
  }

  extension LabelStyle where Self == TrailingIconLabelStyle {
      static var trailingIcon: Self { Self() }
      // trailingIcon์ TrailingIconLabelStyle ๋ ์์ ์ ๋ด์์ ๋ค๋ฅธ ๊ณณ์์ ์ฝ๊ฒ ์ฌ์ฉํ  ์ ์๊ฒ ํจ.
      // static ๋ณ์์ด๊ธฐ ๋๋ฌธ์ ์ด๋์๋  leading-dot syntax๋ฅผ ์ด์ฉํ์ฌ ์ฌ์ฉํ  ์ ์์.
      // ์์ ์ด์ ๋ก ์ฝ๋๊ฐ readableํด์ง.

  }
  ```

## Displaying Data in a List

  SwiftUI ForEach view structure๋ฅผ ์ฌ์ฉํ์ฌ DailyScrum object์ ๋ฐฐ์ด๋ก๋ถํฐ ๋์ ์ผ๋ก ํ๋ค์ ๋ง๋ค ๊ฒ์๋๋ค.  

### Display a List of Daily Scrums

  ForEach๋ฅผ ์ด์ฉํ์ฌ List view์ ์ ๋ณด๋ฅผ ์ฑ์์ค๋๋ค. (๋ฏธ๋ฆฌ ์์ฑํด๋ sampleData ๋ฐฐ์ด์ ์ด์ฉํฉ๋๋ค.)

  <center><img src="/assets/images/scrum5.png" alt="list" width="500"></center><br>  


  ```swift
  //  ScrumsView.swift

  import SwiftUI

  struct ScrumsView: View {
      let scrums: [DailyScrum]

      var body: some View {
          List {
              // ForEach closure ์์ CardView initialize ํด์ฃผ๊ธฐ
              // ์ด closure๋ scrums Array์ ์๋ ์์๋ง๋ค CardView๋ฅผ ๋ฆฌํดํจ
              ForEach(scrums, id: \.title) { scrum in
                  // ์ฒซ๋ฒ์งธ scrum์ CardView์ ์์ฑ์ผ๋ก DailyScrum ํ์์.
                  // ๋๋ฒ์งธ scrum์ ForEach๋ฌธ์์ DailyScrum์ ๊ฐ ์์๊ฐ ํ ๋น๋๋ ๊ณณ
                  CardView(scrum: scrum)
                      .listRowBackground(scrum.theme.mainColor)
                  // ๊ฐ scrum ์์์ theme main์ ์ด์ฉ

              }
          }
      }
  }

  struct ScrumsView_Previews: PreviewProvider {
      static var previews: some View {
          ScrumsView(scrums: DailyScrum.sampleData)
      }
  }
  ```

### Make Scrums Identifiable  

  ForEach structure๋ ์๋ณ ๊ฐ๋ฅํ(Identifiable) ์ ๋ณด๋ฅผ ๋ฐ๋ณตํ์ฌ ์คํํ๋ฉฐ ๋์ ์ธ ๋ทฐ๋ฅผ ๋ง๋ญ๋๋ค. ์์์ List ์์ ์ฌ์ฉํ ForEach์์๋ ์์๋ฅผ ์๋ณํ๊ธฐ ์ํ key path๋ก title์ ์ฌ์ฉํ์ต๋๋ค. (sample data์ title์ด ๋ชจ๋ ๋ฌ๋๊ธฐ ๋๋ฌธ์ ๊ฐ๋ฅํ์ต๋๋ค.) ํ์ง๋ง ๋ง์ฝ ์ค์  ์ฌ์ฉ์๊ฐ ์ด๋ฏธ ์กด์ฌํ๋ title๊ณผ ๊ฐ์ title๋ก ์ scrum์ ๋ง๋ ๋ค๋ฉด ๋ฌธ์ ๊ฐ ๋ฐ์ํ  ์ ์์ต๋๋ค.  

#### User-generated content  

  ์ฌ์ฉ์๊ฐ ์์ฑํ๋ ์ปจํ์ธ ๋ฅผ ์ฌ์ฉํ๋ ์ฑ์ ์๋์ํค๊ธฐ ์ํด์ DailyScrum์ด Identifiable ํ๋กํ ์ฝ์ ๋ฐ๋ฅด๋๋ก ํ  ๊ฒ์๋๋ค. ์ด๊ฒ์ ์์์ ์ด์ฉํ๋ ๋ฐฉ๋ฒ์ฒ๋ผ title์ key path๋ก ์ฌ์ฉํ๋ ๊ฒ๋ณด๋ค ๋ ์์ ํ๊ฒ ๋ฌธ์ ๊ฐ ์ฝ๊ฒ ์ผ์ด๋์ง ์์ ๋ฐฉ๋ฒ์ด ๋  ๊ฒ์๋๋ค. Identifiable ํ๋กํ ์ฝ์ ์๊ตฌ์ฌํญ์ id ์์ฑ์ ๊ฐ๋ ๊ฒ์๋๋ค.  

  ```swift  
    struct DailyScrum: Identifiable {
      let id: UUID          // UUID ํ์์ id ์์ฑ ์์ฑ
      var title: String
      var attendees: [String]
      var lengthInMinutes: Int
      var theme: Theme

      // init ์์ฑ์ ์์ฑ
      init(id: UUID = UUID(), title: String, attendees: [String], lengthInMinutes: Int, theme: Theme) {
          self.id = id
          self.title = title
          self.attendees = attendees
          self.lengthInMinutes = lengthInMinutes
          self.theme = theme
      }
  }
  ```

### App protocol  

  ์ด์  ScrumsView๋ฅผ ์ฑ์ ๋ฃจํธ ๋ทฐ๋ก ๋ง๋ค์ด ์ค๋๋ค. SwiftUI ์ฑ์ App ํ๋กํ ์ฝ์ ๋ฐ๋ฅด๋ structure๋ฅผ ์ ์ํจ์ผ๋ก์จ ์์ฑํ  ์ ์์ต๋๋ค. ์ฑ์ ๋ฐ๋ ์์ฑ์ ์ฌ์ฉ์๊ฐ ์ฃผ๋ก ์ฌ์ฉํ  ์ฒซ๋ฒ์งธ ํ๋ฉด์ ๋ณด์ฌ์ฃผ๋ view hierarchy๋ฅผ ๋ด์ Scene์ ๋ฆฌํดํฉ๋๋ค.

  ```swift
  import SwiftUI

  @main
  struct ScrumdingerApp: App {
      var body: some Scene {
          WindowGroup {
              ScrumsView(scrums: DailyScrum.sampleData)
          }
      }
  }
  ```  

#### WindowGroup  

  WindowGroup์ SwiftUI๊ฐ ์ ๊ณตํ๋ scenes ์ค ํ๋์๋๋ค. iOS์์๋, WindowGroup scene builder์ ์ถ๊ฐ๋ view๊ฐ ๊ธฐ๊ธฐ์ ์ ์ฒด ํ๋ฉด์ ์ฑ์ฐ๋ ์๋์ฐ์ ๋ํ๋๊ฒ ๋ฉ๋๋ค.


## Creating a Navigation Hierarchy

  ์ง๊ธ๊น์ง views๋ฅผ ๋ง๋ค์ด ๋ณด์๊ณ  ์ด์ ๋ถํฐ๋ ๊ทธ views ์ฌ์ด๋ฅผ ์ด๋ํ๋ ๋ฐฉ๋ฒ์ ๋ํด ์์๋ณด๊ฒ ์ต๋๋ค.  

### NavigationView์ Link

  ```swift
  //  ScrumsView.swift

  import SwiftUI

  struct ScrumsView: View {
      let scrums: [DailyScrum]

      var body: some View {
          List {
              // ForEach closure ์์ CardView initialize ํด์ฃผ๊ธฐ
              // ์ด closure๋ scrums Array์ ์๋ ์์๋ง๋ค CardView๋ฅผ ๋ฆฌํดํจ
              ForEach(scrums) { scrum in
                  // ์ฒซ๋ฒ์งธ scrum์ CardView์ ์์ฑ์ผ๋ก DailyScrum ํ์์.
                  // ๋๋ฒ์งธ scrum์ ForEach๋ฌธ์์ DailyScrum์ ๊ฐ ์์๊ฐ ํ ๋น๋๋ ๊ณณ
                  NavigationLink(destination: Text(scrum.title)) {
                      CardView(scrum: scrum)
                  }
                  .listRowBackground(scrum.theme.mainColor)
                  // ๊ฐ scrum ์์์ theme main์ ์ด์ฉ

              }
          }
          .navigationTitle("Daily Scrums")   // -> title์ ๋ถ๋ชจ navigation stack ์์ชฝ์
          .toolbar {
              Button(action: {}) {
                  Image(systemName: "plus")
              }
              .accessibilityLabel("New Scrum")
          }
      }
  }

  struct ScrumsView_Previews: PreviewProvider {
      static var previews: some View {
          // Navigation title์ ์ํ padding์ ํ๋ฉด์ ๋ณด์ฌ์ค
          NavigationView {
              ScrumsView(scrums: DailyScrum.sampleData)
          }
      }
  }

  ```

  ScrumsView.swift ํ์ผ์ NavigationView์ NavigationLink๋ฅผ ์ถ๊ฐํ์ฌ ์ฝ๋๋ฅผ ์์ ํด์ค๋๋ค.

  <center><video src="https://user-images.githubusercontent.com/85061148/163188935-455f0ea8-13b2-4d8d-9208-cdbaeb78c528.mov" controls="controls" style="max-width: 400px">
  </video></center><br>  

  ์์์์ ๋ณผ ์ ์๋ฏ์ด SwiftUI๋ ์๋์ผ๋ก ๋ํ์ผ ๋ทฐ์์ Back ๋ฒํผ์ ์ถ๊ฐํ๊ณ  ์  ํ๋ฉด์ ํ์ดํ์ ํ์ํฉ๋๋ค.

### Create the Detail View  

  ๊ณ์ธต ๊ตฌ์กฐ๋ฅผ ๊ฐ์ง๊ณ  ์๋ ์ฑ(hierarchical apps)์์๋, ๋ ๋์ ๊ณ์ธต์ view์์ detailed view๋ก ์ด๋ํฉ๋๋ค. ๊ทธ๋ฌ๋ฏ๋ก์จ ๋ ํน์ ๋ ๋ฐ์ดํฐ๋ฅผ ์กฐ์ํ  ์ ์์ต๋๋ค. ์ด ์น์์๋ ๊ฐ scrum์ ๋ํ์ผ ๋ทฐ๋ฅผ ๋ง๋ค์ด ๋ณผ ๊ฒ์๋๋ค.

  1. DetailView.swift๋ฅผ ์์ฑํฉ๋๋ค.
  2. DetailView.swift์ DailyScrum ํ์์ scrum constant๋ฅผ ์์ฑํฉ๋๋ค.
  3. ScrumsView.swift์ NavigationLink์ destination์ ์์ ํฉ๋๋ค.

  ```swift
  ForEach(scrums) { scrum in
      NavigationLink(destination: DetailView(scrum: scrum)) {
          CardView(scrum: scrum)
      }
      .listRowBackground(scrum.theme.mainColor)
      // ๊ฐ scrum ์์์ theme main์ ์ด์ฉ

  }
  ```
  destination์ DetailView๋ก ์์ ํด์ฃผ์์ต๋๋ค. (scrum: )์ DetailView์ constant์ด๊ณ  ๊ทธ ๋ค์ ์ค๋ scrum์ ForEach๋ฌธ์ ์ฌ์ฉ๋ ๋ณ์์๋๋ค.

### DetailView with Visual Components  

#### List  

  List view๋ฅผ ์ด์ฉํ์ฌ scrum์ ์ด๋ฆ, ๋ฏธํ ์๊ฐ, ์นด๋์ ์, ์ฐธ์์๋ค์ ๋ชฉ๋ก์ ๋ํ์ผ ๋ทฐ์ ๋ณด์ฌ์ค๋๋ค.

  ```swift
  // DetailView.swift

  struct DetailView: View {
    let scrum: DailyScrum

    var body: some View {
        List {
            Section(header: Text("Meeting Info")) {
                Label("Start Meeting", systemImage: "timer")
                Spacer()
                HStack {
                    Label("Length", systemImage: "clock")
                    Spacer()
                    Text("\(scrum.lengthInMinutes) minutes")
                }
                .accessibilityElement(children: .combine)

              }
          }
      }
  }
  ```
  Sections List์์ ๋ชฉ๋ก์ ๊ทธ๋ฃน์ ๋ง๋ค์ด์ ๋์ ๋ณด์ด๋ ๊ตฌ๋ถ์ ์ ๋ง๋ค์ด์ค๋๋ค.  

  .accessibilityElement(children: .combine)  
  ์์ modifier๋ฅผ ์ด์ฉํ์ฌ Label view์ Text view๋ฅผ ํ๋๋ก ํฉ์ณ์ค๋๋ค. (accessibility user๋ฅผ ์ํด)  

### Iterate Through Attendees  

  ```swift  
  //DailyScrum.swift

  struct DailyScrum: Identifiable {
      let id: UUID
      var title: String
      var attendees: [Attendee]
      var lengthInMinutes: Int
      var theme: Theme

      init(id: UUID = UUID(), title: String, attendees: [String], lengthInMinutes: Int, theme: Theme) {
          self.id = id
          self.title = title
          self.attendees = attendees.map { Attendee(name: $0) }
          self.lengthInMinutes = lengthInMinutes
          self.theme = theme
      }
  }

  extension DailyScrum {
      struct Attendee: Identifiable {
          let id: UUID            // id ์์ฑ์ let
          var name: String

          // id ์์ฑ์ defalut ๊ฐ์ ์ฃผ๋ ์์ฑ์
          init(id:UUID = UUID(), name: String) {
              self.id = id
              self.name = name
          }
      }
  }

  ```
  DailyScrum์ extension์ ์ถ๊ฐํ์ฌ ์์ Attendee๋ผ๋ structure๋ฅผ ๋ง๋ค์ด ์ค๋๋ค. ForEach๋ฅผ ์ด์ฉํด sample data์ ์ฐธ์์๋ค์ DetailView์ ๋ณด์ฌ์ค ๊ฒ ์ด๋ฏ๋ก Attendee์ id, name ์์ฑ์ ์ ์ํฉ๋๋ค. id ๊ฐ์ ๋ํดํธ ๊ฐ์ ์ฃผ๊ธฐ ์ํด์ ์์ฑ์๋ฅผ ๋ง๋ญ๋๋ค. ์ฒ์์ ๋ง๋ค์ด ๋์๋ DailyScrum ๋ชจ๋ธ์์ attendees์ ํ์์ [Attendee] (Attendee ํ์์ ๋ฐฐ์ด)๋ก ์์ ํด์ค๋๋ค.

#### map(_:)  

  map(_:)์ ์ด๋ฏธ ์กด์ฌํ๋ collection์ ๊ฐ ์์์ ๋ฐ๋ณตํด์ ๋ณํ๋ฅผ ์ ์ฉํ๋ฉฐ ์๋ก์ด collection์ ์์ฑํฉ๋๋ค.

  ```swift  
  // init ์์ฑ์ ์
  self.attendees = attendees.map { Attendee(name: $0) }
  ```
  ํจ๋ฌ๋ฏธํฐ๋ฅผ ํตํด ๋ค์ด์จ attendees๋ฅผ map์ ์ด์ฉํด ๋ฐ๋ณตํด ๋๋ฉด์ Attendee ํ์์ผ๋ก ๋ฐ๊ฟ์ค๋ค.(?)

#### ForEach

  ```swift
  Section(header: Text("Attendees")) {
                ForEach(scrum.attendees) { attendee in
                    Label(attendee.name, systemImage: "person")
                }
            }
  ```
  Attendee๊ฐ identifiable ํด์ก์ผ๋ฏ๋ก ForEach๋ฅผ ์ฌ์ฉํ์ฌ sample data๋ฅผ ํตํด ๋์ ์ผ๋ก ์ฐธ์์๋ค์ ๋ฆฌ์คํธ๋ฅผ ๋ง๋ค ์ ์๊ฒ ๋์์ต๋๋ค.
  <center><img src="/assets/images/scrum6.png" alt="section" width="400"></center><br>  

### Navigate Between Screens

  DetailView์์ ์ด๋ํ๋ view๋ฅผ ๋ง๋ค๋ฉฐ hierarchy ์ค์ ์ ๋ง๋ฌด๋ฆฌํด๋ด๋๋ค.

  ```swift  
  NavigationLink(destination: MeetingView()) {
                    Label("Start Meeting", systemImage: "timer")
                        .font(.headline)
                        .foregroundColor(.accentColor)
                }
  ```
  NavigationLink๋ฅผ ์ถ๊ฐํ๋ ๊ฒ์ label์ gesture recognizer ํํ๋ก ๊ฐ์ธ์ค๋๋ค. ์ด๋ก ์ธํด ์ฌ์ฉ์๋ค์ ์ด ํ์ ํญํ์ฌ meeting timer screen์ ๋ณผ ์ ์๊ฒ ๋ฉ๋๋ค.

  ์ด๋ ๊ฒ navigation stack์ ์์ฑํ์ต๋๋ค.

## Managing Data Flow Between Views

  ์ฌ์ฉ์์๊ฒ ์ ๋ณด๋ฅผ ๋ณด์ฌ์ฃผ๊ณ  ์ฌ์ฉ์์ ์ํธ์์ฉํ๋ฉฐ ๋ฐ์ดํฐ๋ฅผ ์์ ํด ๋ณด์ฌ์ฃผ๋ ๊ฒ์ ๋๋ถ๋ถ์ ์ฑ๋ค์ ๊ธฐ๋ณธ์ด ๋๋ ๊ธฐ๋ฅ์๋๋ค. ์ฑ์ UI๊ฐ ํ์ฌ ๋ฐ์ดํฐ์ ์ํ๋ฅผ ์ ๋ฐ์ํ๋๋ก ํ๊ธฐ ์ํด @State์ @Binding์ ์ฌ์ฉํ๋ ๋ฐฉ๋ฒ์ ๋ํด ์์๋ด๋๋ค.

### Source of Truth  

  ํ ์ ๋ณด์ ์ฌ๋ฌ๊ฐ์ง ๋ณต์ฌ๋ณธ์ ์ ์งํ๋ ๊ฒ์ ์ฑ์ ๋ฒ๋ฅด๊ณ  ์ด๋๋ ๋ถ์ผ์น๋ฅผ ์ด๋ํ  ์ ์์ต๋๋ค. ๋ฐ์ดํฐ ๋ถ์ผ์น ๋ฒ๊ทธ๋ฅผ ํผํ๊ธฐ ์ํด ์ฑ์ ๊ฐ ๋ฐ์ดํฐ๋ค์ ์ํด a single source of truth๋ฅผ ์ฌ์ฉํฉ๋๋ค. ํ ์ฅ์์ ์์๋ฅผ ์ ์ฅํ์ธ์. (the source of truth์) ๊ทธ๋ฆฌ๊ณ  ๋ช๊ฐ์ view๋  ๊ทธ ๋ฐ์ดํฐ์ ์ ๊ทผํ  ์ ์์ต๋๋ค. Source of truth๋ ์ฝ๋ ์ ์ฒด ์ด๋์๋  ์์ฑํ  ์ ์์ต๋๋ค.  
  Scrumdinger ์ฑ์์๋ ๋ชจ๋  ๋ทฐ๋ค์ด ์ ๊ทผ์ ๊ณต์ ํ  ScrumdingerApp์ source of truth๋ฅผ ์์ฑํ  ๊ฒ์๋๋ค.

### Swift Property Wrappers

#### State  

  @State๋ฅผ ์ด์ฉํด ์์ฑ์ ์ ์ํ๋ฉด, ํด๋น view์์ a source of truth๋ฅผ ์์ฑํ  ์ ์์ต๋๋ค. ์์คํ์ @State property๋ฅผ ์ฌ์ฉํ๋ ๋ทฐ์ ๋ชจ๋  ์์๋ค์ ์๋ณํฉ๋๋ค. ์ฌ์ฉ์์ ์ฌ์ฉ์์์ ์ํธ์์ฉ์ @State ์์ฑ์ ๊ฐ์ ๋ณํ์ํฌ ์ ์๊ณ , ์์คํ์ @State๋ฅผ ์ฌ์ฉํ๋ ์์ฑ์ ์๋ฐ์ดํธ ํจ์ผ๋ก์จ ์๋ก์ด ๋ฒ์ ์ UI๋ฅผ ๋ ๋๋งํฉ๋๋ค.

  @State์ ๊ฐ์ด ๋ณํ๋ฉด ์์คํ์ ์๋ฐ์ด๋ ๊ฐ์ ์ฌ์ฉํ๋ ๋ทฐ๋ฅผ ๋ค์ ๊ทธ๋ฆฝ๋๋ค. ์๋ฅผ ๋ค์ด Scrumdinger ์ฑ์ ์ฌ์ฉ์๊ฐ ํ๋์ scrum์ ์์ ํ๋ฉด ScrumsView๋ ์๋ฐ์ดํธ ๋ ๊ฐ์ ํ๋ฉด์ ๋ณด์ฌ์ฃผ๊ธฐ ์ํด์ list๋ฅผ ๋ค์ ๊ทธ๋ฆฝ๋๋ค.  

  State property๋ ์ ์ ๋จธ๋ฌด๋ฅด๋ ์ํ๋ฅผ ๊ด๋ฆฌํ๋ ๊ฒ์ ๋๊ธฐ ๋๋ฌธ์ private์ผ๋ก ์ ์ํ๊ณ  ์ง์๋์ผํ๋ ์ ์ฅ์๋ ์ฌ์ฉํ๋ ๊ฒ์ ํผํด์ผ ํฉ๋๋ค.

#### Binding  

  @Binding์ ์ฌ์ฉํ์ฌ ๊ฐ์ผ property๋ ์ฝ๊ธฐ ๊ทธ๋ฆฌ๊ณ  ์ฐ๊ธฐ์ ๋ํ ์ ๊ทผ์ ์กด์ฌํ๋ source of truth์ ๊ณต์ ํฉ๋๋ค. (@State property ์ฒ๋ผ...)  
  @Binding์ ๋ฐ์ดํฐ๋ฅผ ์ง์ ์ ์ผ๋ก ๋ด์ง ์์ต๋๋ค. ๋์ , ๊ทธ ๋ฐ์ดํฐ๋ฅผ ์๋ฐ์ดํธํ๊ณ  ํ๋ฉด์ ๋ณด์ฌ์ฃผ๋ source of truth์ view ์ฌ์ด์ ์๋ฐฉํฅ ์ฐ๊ฒฐ์ ์์ฑํฉ๋๋ค. ์ด ์ฐ๊ฒฐ์ ์ฌ๋ฌ๊ฐ์ ๋ทฐ์ ์ฐ๊ฒฐ๋ ํ๋์ ๋ฐ์ดํฐ๊ฐ ํญ์ ์๋ฐ์ดํธ ๋ ์ํ๋ก ์ ์ง๋๊ฒ ํฉ๋๋ค.

  <!-- ๋จ์ ๋ถ๋ถ ์คํตํจ. ์๊ฐ๋๋ฉด ๋ ์ฑ์ฐ๋๋ก. -->

## Creating the Edit View  

### Update the Data Model

  Edit view๋ฅผ ๋ง๋ค๊ธฐ ์ ์, DailyScrum.swift์์ ์๋ก์ด ํ์์ธ Data๋ฅผ ์์ฑํฉ๋๋ค. Data๋ DailyScrum์ ํธ์ง์ด ๊ฐ๋ฅํ ๋ชจ๋  ์์ฑ๋ค์ ๋ด์ ๊ฒ์๋๋ค. ์ด ์์ฑ๋ค์ edit view์ ์์ฑํ  controls์ ์ผ์นํ  ๊ฒ์๋๋ค.  

  ```swift
  struct Data {
      var title: String
      var attendees: [Attendee]
      var lengthInMinutes: Double
      var theme: Theme
  }
  ```
  DailyScrum์ extensnion์์ Data structure๋ฅผ ์ ์ํฉ๋๋ค. ์ฌ์ฉ์๊ฐ Slider view๋ฅผ ์ด์ฉํด ๋ฏธํ ์๊ฐ์ ์กฐ์ ํ๊ฒ ๋ฉ๋๋ค. Sliders๋ Double ๊ฐ์ ์ด์ฉํ๋ฏ๋ก lengthInMinutes์ ์๋ฃํ์ Double๋ก ์ค๋๋ค.  

  Foundation ํ๋ ์์ํฌ์ Data structure๊ฐ ์๊ธฐ ๋๋ฌธ์ DailyScrum์ extension์ Data structure๋ฅผ ์ ์ํด์ nested type์ผ๋ก ๋ง๋ค๋ฉด์ (-> DailyScrum.Data) ๋๊ฐ๋ฅผ ๋ถ๋ฆฌํ  ์ ์๊ฒ ๋ฉ๋๋ค.

  ```swift  
  struct Data {
      var title: String = ""
      var attendees: [Attendee] = []
      var lengthInMinutes: Double = 5
      var theme: Theme = .seafoam
  }

  var data: Data {
      Data(title: title, attendees: attendees, lengthInMinutes: Double(lengthInMinutes), theme: theme)
  }
  ```
  ๊ทธ๋ฆฌ๊ณ  ๊ฐ ์์ฑ์ ๊ธฐ๋ณธ๊ฐ์ ์ค๋๋ค. ๋ชจ๋  ์์ฑ์ด ๊ธฐ๋ณธ ๊ฐ์ ๊ฐ์ง๊ณ  ์๋ค๋ฉด ์ปดํ์ผ๋ฌ๋ ์ธ์๊ฐ ํ์์๋ ์์ฑ์๋ฅผ ๋ง๋ญ๋๋ค. ์ด๋ ๊ฒ ๋ง๋ค์ด์ง ์์ฑ์๋ Data()๋ก ํธ์ถ๋์ด ์ธ์คํด์ค๋ฅผ ์์ฑํ  ์ ์์ต๋๋ค.  

  DailyScrum ์์ฑ ๊ฐ์ ๊ฐ์ง๋ Data๋ฅผ ๋ฆฌํดํ๋ computed property๋ ์์ฑํด ์ค๋๋ค.

### Add an Edit View for Scrum Details  

  - Edit View๋ฅผ ์์ฑํ๊ณ , scrum์ ์ ๋ชฉ๊ณผ ์์ ์๊ฐ์ ์์ ํ๊ธฐ ์ํด ์ด์ฉ๋๋ controls๋ฅผ ์์ฑํฉ๋๋ค.  
  - Scrum ๋ฐ์ดํฐ์ ๋ณํ๋ฅผ Data ์์ฑ ํ์์ผ๋ก ์ ์ฅํฉ๋๋ค.
  - @State property wrapper๋ฅผ ์ฌ์ฉํฉ๋๋ค.

  ```swift  
  @State private var data = DailyScrum.Data()
  ```
  DetailEditView.swift ํ์ผ์ ๋ง๋ค๊ณ  ์์ ์ฝ๋๋ฅผ ์ถ๊ฐํ์ฌ source of truth๋ฅผ ์ ์ํฉ๋๋ค.  
  Data ํ์์ ๋ชจ๋  ์์ฑ์ ๊ธฐ๋ณธ๊ฐ์ ์ฃผ์์ผ๋ฏ๋ก ์๋์ผ๋ก ์์ฑ๋ ์์ฑ์ DailyScrum.Data()๋ฅผ @State property wrapper๋ก ๊ฐ์ธ์ค๋๋ค. ์ค์ง ์ด ์์ฑ์ ์ ์ํ ์ด view์์๋ง ์ ๊ทผ ๊ฐ๋ฅํ๋๋ก private ์์ฑ์ผ๋ก ์ ์ํฉ๋๋ค.

  ```swift  
  struct DetailEditView: View {
      @State private var data = DailyScrum.Data()
      var body: some View {
          Form {
              Section(header: Text("Meeting Info")) {
                  TextField("Title", text: $data.title)
              }
          }
      }
  }
  ```
  Form์ ๋ค๋ฅธ ํ๋ซํผ๋ค์์ controls์ ๋ชจ์์ด ์๋์ผ๋ก ์ ์๋ ๋ชจ์ต์ผ๋ก ๋ ๋๋ง ๋๋๋ก ํฉ๋๋ค.  

  ์ ๋ชฉ์ ์๋ ฅํ  TextField๋ฅผ ์์ฑํฉ๋๋ค. TextField๋ binding์ String์ผ๋ก ๋ฐ์๋ค์๋๋ค. $ syntax๋ฅผ ์ฌ์ฉํ์ฌ data.title์ binding์ ์์ฑํฉ๋๋ค. ํ์ฌ์ ๋ทฐ๋ data ์์ฑ์ ์ํ๋ฅผ ์กฐ์ํ  ์ ์๊ฒ ๋ฉ๋๋ค.

  ```swift  
  HStack {
      TextField("New Attendee", text: $newAttendeeName)
      Button(action: {
          withAnimation {
              let attendee = DailyScrum.Attendee(name: newAttendeeName)
              data.attendees.append(attendee)
              newAttendeeName = ""      // text field๋ฅผ ๋น์์ค
          }
      }) {
          Image(systemName: "plus.circle.fill")
      } // ๋ฒํผ ๋
      .disabled(newAttendeeName.isEmpty)
  }
  ```

  Text field๊ฐ newAttendeeName์ binding์ ๊ฐ์ง๊ณ  ์๊ธฐ ๋๋ฌธ์ ์๋ ๊ฐ์ ์ค์ ํด์ฃผ๋ฏ๋ก์จ text fields์ ์ปจํ์ธ ๋ฅผ ๋น์ธ ์ ์์ต๋๋ค.

  newAttendeeName์ด ๋น์ด์์ ๋๋ ๋ฒํผ์ ๋นํ์ฑํ ์ํต๋๋ค. ์ด๊ฒ์ ์ ์ ๊ฐ ์ด๋ฆ ์๋ ์ฐธ์์๋ฅผ ์ถ๊ฐํ๋ ๊ฒ์ ๋ฐฉ์งํด์ค๋๋ค. ์ ์ ๊ฐ ์ด๋ฆ์ ์๋ ฅํ๋ฉด ๋ฒํผ์ ํ์ฑํ๋ฉ๋๋ค.

### Present the Edit View

  DetailView์์ ๋ฒํผ์ ๋๋ฅด๋ฉด Modal view์ ํ์์ผ๋ก DetailEditView๋ฅผ ๋ณด์ฌ์ค ๊ฒ์๋๋ค.
  ```swift
  @State private var isPresentingEditView = false
  ```
  ```swift
  } // DetailView.swift - List view ๋๋ถ๋ถ
  .navigationTitle(scrum.title)
  .toolbar {
      Button("Edit") {
          isPresentingEditView = true
      }
  }
  .sheet(isPresented: $isPresentingEditView) {
      DetailEditView()
  }
  ```
  - sheet modifier๋ ํ์ฌ ํ๋ฉด์ content๋ฅผ ๋ถ๋ถ์ ์ผ๋ก ๊ฐ๋ฆฌ๋ modal sheet๋ฅผ ์์ฑํฉ๋๋ค.
  - Button์ ๋๋ฅด๋ฉด ์์ ์ ์ํ๋ isPresentingEditView๊ฐ true๋ก ๋ฐ๋๊ณ  sheet๊ฐ ๊ฐ์ง๊ณ  ์๋ isPresentingEditView ๋ฐ์ธ๋ฉ์ด true๊ฐ์ ๊ฐ์ง๊ฒ ๋๋ฉด์ DetailEditView๊ฐ modal sheet๋ก ๋ณด์ฌ์ง๊ฒ ๋ฉ๋๋ค.

  ```swift
  .sheet(isPresented: $isPresentingEditView) {
      NavigationView {
          DetailEditView()
              .navigationTitle(scrum.title)
              .toolbar {
                  ToolbarItem(placement: .cancellationAction) {
                      Button("Cancel") {
                          isPresentingEditView = false
                      }
                  }
                  ToolbarItem(placement: .confirmationAction) {
                            Button("Done") {
                                isPresentingEditView = false
                            }
                        }
              }
      }
  }
  ```
  ToolbarItem์ผ๋ก modal view์ Cancel / Done ๋ฒํผ์ ์์ฑํฉ๋๋ค. Cancel๋ฒํผ์ ๋๋ฅด๋ฉด ๋ณ๊ฒฝ ์ฌํญ์ด ์ ์ฅ๋์ง ์๊ณ  ์ทจ์๋๊ณ  ๋ชจ๋ฌ ๋ทฐ๊ฐ ์ฌ๋ผ์ง๋๋ค. Done ๋ฒํผ์ ๋ณ๊ฒฝ ์ฌํญ์ด ์ ์ฅ๋๊ณ  ๋ชจ๋ฌ ๋ทฐ๊ฐ ์ฌ๋ผ์ง๋๋ค. (์์ง ๋ฐ์ดํฐ๋ฅผ ์ง์ง ์ ์ฅํ  ์๋ ์์ต๋๋ค.)


## Passing Data with Bindings  

### Add a Theme View  

  ์ฌ์ฉ์๊ฐ ๊ฐ scrum์ ๊ตฌ๋ณํ๊ธฐ ์ฝ๊ฒ ํ๊ธฐ ์ํด Color theme์ ์ ํํ  ์ ์๋๋ก ํ  ๊ฒ์๋๋ค. ๋จผ์  theme ์ components๋ฅผ ๋ณด์ฌ์ค theme view๋ฅผ ์์ฑํฉ๋๋ค.

  ```swift
  //  ThemeView.swift

  import SwiftUI

  struct ThemeView: View {
      let theme: Theme

      var body: some View {
          ZStack {
              RoundedRectangle(cornerRadius: 4)
                  .fill(theme.mainColor)
              Label(theme.name, systemImage: "paintpalette")
                  .padding(4)
          }
          .foregroundColor(theme.accentColor)
          .fixedSize(horizontal: false, vertical: true)
      }
  }

  struct ThemeView_Previews: PreviewProvider {
      static var previews: some View {
          ThemeView(theme: .buttercup)
      }
  }
  ```

  fixedSize modifier๋ฅผ ์ฌ์ฉํ์ฌ ๋ผ๋ฒจ์ ์๋ ์ฌ์ด์ฆ์ ํฌ๊ธฐ๋ฅผ ๋ง์ถฐ์ค๋๋ค. Label์ ํจ๋ฉ์ ์ถ๊ฐํด์ฃผ์ด์ ๋ ๋ณด๊ธฐ ํธํ๊ฒ ๋ง๋ค์ด ์ค๋๋ค. ์ฌ๊ธฐ์ ๋ง๋  view๋ ์ ์ฒด ์ปฌ๋ฌ๋ฅผ ๋ณด์ฌ์ฃผ๋ list์ ํ cell๋ก ์ด์ฉํ  ๊ฒ์๋๋ค.

### Add a Theme Picker

  ์ฌ์ฉ์๊ฐ meeting view์ theme ์์ ์ ํํ  ์ ์๋๋กํ๋ custom interactive view๋ฅผ ์์ฑํฉ๋๋ค.

  ```swift
  // ThemePicker.swift

  import SwiftUI

  struct ThemePicker: View {
      @Binding var selection: Theme    

      var body: some View {
          Picker("Theme", selection: $selection) {
              ForEach(Theme.allCases) { theme in
                  ThemeView(theme: theme)
                      .tag(theme)
              }
          }
      }
  }

  struct ThemePicker_Previews: PreviewProvider {
      static var previews: some View {
          ThemePicker(selection: .constant(.periwinkle))
      }
  }
  ```
  ThemePicker.swift ํ์ผ์ ์๋ก ์์ฑํด์ค๋๋ค. DetailEditView์ ๋ค์ด๊ฐ Picker view๋ฅผ ์์ฑํฉ๋๋ค. ForEach๋ฅผ ์ฌ์ฉํด ๊ฐ case๋ก์ ์ ๊ทผ์ ์ฉ์ดํ๊ฒ ํฉ๋๋ค.
  Theme.swift์ enum Theme์ CaseIterable, Identifiable ํ๋กํ ์ฝ์ ์ถ๊ฐํด์ค๋๋ค. id ์์ฑ์ case์ ์ด๋ฆ์ผ๋ก ์ถ๊ฐํด์ค๋๋ค.

  ```swift
  // DetailEditView.swift - body - Form
  } Slider ์๋ HStack ๋๋ถ๋ถ
  ThemePicker(selection: $data.theme)
  ```
  ์์ ThemePicker ์์ฑ์๋ theme selection์ ์ผ์ด๋ ๋ณํ๋ฅผ data.theme์ผ๋ก ๋ค์ ๋๋ ค๋ณด๋๋๋ค.

#### constant(_:) type method

  ๋ณ๊ฒฝ๋์ง ์๋ ๊ฐ์ ๊ฐ์ง๋ binding์ ์์ฑํฉ๋๋ค. PreviewProvider๋ฅผ ์ฌ์ฉํ  ๋, ๋ค๋ฅธ ๊ฐ๋ค์ ์ด๋ป๊ฒ ๋ณด์ฌ์ฃผ๋์ง ์์๋ณด๊ธฐ ์ํด์ ์ฌ์ฉํ  ์ ์์ต๋๋ค.

### Pass the Edit View a Binding to Data

  ์ฌ์ฉ์๊ฐ scrum์ ์ ๋ณด๋ฅผ ์์ ํ๋ฉด, ์ฑ์ ์๋ ์ฌ๋ฌ๊ฐ์ screen์ด ๊ทธ ๋ณ๊ฒฝ๋ ์ ๋ณด๋ฅผ ๋ฐ์ํด์ผ ํฉ๋๋ค. ์ด ์น์์์๋, ์ฌ์ฉ์๊ฐ Done ๋ฒํผ์ ๋๋ ์ ๋ edit view์ detail view์ scrum์ ์๋ฐ์ดํธํ๋ binding์ ์ถ๊ฐํฉ๋๋ค.

  ๋ํ์ผ ํ๋ฉด์ editํ๋ฉด์์ ๋ง๋ค์ด์ง ๋ณ๊ฒฝ ์ฌํญ์ ์๋ฐ์ดํธ ํด์ผ ํฉ๋๋ค. ๊ทธ๋์ ๋ํ์ผ ํ๋ฉด์ source of truth๋ฅผ edit ํ๋ฉด๊ณผ ๊ณต์ ํฉ๋๋ค.

### Edit ํ๋ฉด์ ๊ธฐ์กด scrum ์ ๋ณด ๊ฐ์ ธ์ค๊ธฐ

  Edit ๋ฒํผ์ ๋๋ฅด๋ฉด scrum์ ์๋ ฅ๋์ด ์๋ ๊ธฐ์กด ์ ๋ณด๋ฅผ edit modal sheet์ ๋ณด์ฌ์ฃผ๋๋ก ์ค์ ํด ๋ด๋๋ค.

  ```swift
  .toolbar {
      Button("Edit") {
          isPresentingEditView = true
          data = scrum.data
      }
  }
  ```
  ```swift
  data = scrum.data

  // = ์ผ์ชฝ์ ์๋ data
  @State private var data = DailyScrum.Data()

  // = ์ค๋ฅธ์ชฝ scrum. ๋ค์ data
  var data: Data {
      Data(title: title, attendees: attendees, lengthInMinutes: Double(lengthInMinutes), theme: theme)
  }
  ```
  ๋น์ด์๋ ์์ฑ์๋ ๊ธฐ๋ณธ ๊ฐ์ ๊ฐ์ง ์ธ์คํด์ค๋ฅผ ์์ฑํฉ๋๋ค. ์ด ๊ฐ๋ค์ ์ ํํ scrum์ ๊ฐ์ผ๋ก ์ค์ ํด์ค๋๋ค.

  <!-- ๐ท ๋ฐ์ดํฐ์ ํ๋ฆ ๋ค์ ์ ๋ฆฌ -->

### ํํ ๋ฆฌ์ผ ์ค ๋น ์ง ๋ถ๋ถ(?)

  ```swift
  // DetailView.swift

  ToolbarItem(placement: .confirmationAction) {
      Button("Done") {
          isPresentingEditView = false
          scrum.update(from: data) // <- ๊ณ์ํด์ ์๋ฌ๊ฐ ๋๋ ๋ถ๋ถ
      }
  }
  ```
  ์ปดํ์ผ๋ฌ๊ฐ ์์ ํ์ํ ๊ณณ์์ ์๊พธ ์๋ฌ๋ฅผ ๋ฐ์์์ผฐ๋ค. ์ฝ๋๋ฅผ ๋ค๋ฅด๊ฒ ํ์ดํ ํ๊ฑธ๊นํด์ ์ด์ฌํ ์ฐพ์๋ณด์์ง๋ง ๋ค๋ฅธ ๋ถ๋ถ์ ์์๋ค. Complete ๋ฒ์ ์ ํ๋ก์ ํธ ํ์ผ์ ๋ฐ์์ ํ์ธํด๋ณด๋ ์ค DailyScrum.swift์์ ํํ ๋ฆฌ์ผ์๋ ์๋ function์ ๋ฐ๊ฒฌํ๋ค.

  ```swift
  mutating func update(from data: Data) {
      title = data.title
      attendees = data.attendees
      lengthInMinutes = Int(data.lengthInMinutes)
      theme = data.theme
  }
  ```
  ์์ ์ฝ๋๋ฅผ DailyScrum์ extension์ ์ถ๊ฐํด์ฃผ๋ฉด ์ ์์ ์ผ๋ก ์๋ํ๋ค.

### ํํ ๋ฆฌ์ผ ์ค ์ด ๋ถ๋ถ์์๋ โ

  - @State property wrapper๋ฅผ ์ด์ฉํด์ value type์ source of truth๋ฅผ ์์ฑํด ๋ณด์์ต๋๋ค.
  - @Binding์ ์ฌ์ฉํ์ฌ ๋ค๋ฅธ views์ state์ ์ฐ๊ธฐ ๊ถํ์ ๊ณต์ ํด ๋ณด์์ต๋๋ค. (์ฌ์ฉ์๋ก๋ถํฐ ์๋ ฅ๋ฐ์ ์ ๋ณด๋ก @State๋ก ๊ฐ์ผ ๋ณ์๋ฅผ ์ฌ์ฉํ๋ views์ ๋ฐ์ดํฐ๋ฅผ ์๋ฐ์ดํธํ ๊ฒ์ ๋งํ๋ ๊ฒ ๊ฐ์ต๋๋ค.)


## Making Classes Observable  

  ์์์๋ @State์ @Binding์ ์ด์ฉํ์ฌ value type๋ฅผ source of truth๋ก ์ ์ํ๋ ๊ฒ์ ๋ํด ์์๋ณด์์ต๋๋ค. ์ฌ๊ธฐ์๋ ์ฑ์ UI๋ฅผ ์ํด reference type์ source of truth๋ก ์ ์ํ๋ ๋ฐฉ๋ฒ์ ๋ํด ์์๋ด๋๋ค.  

  @State property wrapper๋ value types์๋ง ์ ์ฉํ  ์ ์์ต๋๋ค. structures๋ enumerations ๊ฐ์ ๊ฒ์ด์ฃ . SwiftUI๋ reference type์ source of truth๋ก ์ ์ํ๋ property wrappers๋ฅผ ์ ๊ณตํฉ๋๋ค.

  - @ObservableObject
  - @StateObject
  - @EnvironmentObject

  reference type์ธ class์ ํจ๊ป property wrappers๋ฅผ ์ฌ์ฉํ๊ธฐ ์ํด์๋ class๋ฅผ observableํ๊ฒ ๋ง๋ค์ด์ผ ํฉ๋๋ค.  

### Making a Class Observable  

  ObservableObject protocol๋ฅผ ๋ฐ๋ฆ์ผ๋ก์จ class๋ฅผ observableํ๊ฒ ๋ง๋ค ์ ์์ต๋๋ค.  
  ํด๋์ค ์์ properties ์ค ์ ๋ณด๊ฐ ๋ณ๊ฒฝ๋์์ ๋ UI์ ๋ณํ๋ฅผ ์ผ์ผํค๋ properties๋ฅผ ์ ํํ๊ณ  ๊ทธ properties์ ๊ฐ๊ฐ @Published attribute๋ฅผ ์ถ๊ฐํด์ค๋๋ค.

  ```swift
  class ScrumTimer: ObservableObject {
      @Published var activeSpeaker = ""
      @Published var secondsElapsed = 0
      @Published var seconds Remaining = 0
      // ...
  }
  ```
  ์ ํด๋์ค์ ์์ฑ์ ํ๋ฒ์ scrum ์ธ์์์ ๋น๋ฒํ๊ฒ ์๋ฐ์ดํธ ๋  ๊ฒ์๋๋ค. ScrumTimer๋ published properties์ ๊ฐ์ ๋ณ๊ฒฝ ์ฌํญ์ด ์์ ๋๋ง๋ค observers์๊ฒ ๊ทธ๊ฒ์ ์๋ ค์ค๋๋ค.

<!-- ### Monitoring an Object for Changes  

  Property๋ฅผ ์ ์ํ  ๋ ์๋ attributes ์ค ํ๋๋ฅผ ์ถ๊ฐํจ์ผ๋ก์จ SwiftUI์๊ฒ observable object๋ฅผ ๋ชจ๋ํฐ๋ง ํ๋๋ก ํ  ์ ์์ต๋๋ค.

  - ObservableObject
  - StateObject
  - EnvironmentObject -->

  <!-- ์ด property wrappers ์ค ํ๋๋ก ์ ์๋ view property๋ ์๋ก์ด source of truth๋ฅผ ์์ฑํฉ๋๋ค. -->

<!-- ๐ท #### @StateObject  

  @StateObject wrapper๋ view์์ ๊ด์ฐฐ ๊ฐ๋ฅํ object๋ฅผ ์์ฑํฉ๋๋ค.

  ```swift
  struct MeetingView: View {
      @StateObject var scrumTimer = ScrumTimer()
      // ...
  }
  ```
  @ObservedObject

  ```swift
  struct ChildView: View {
      @ObservedObject var timer: scrumTimer
      // ...
  }
  ```
  ๊ทธ๋ฆฌ๊ณ  ๋์ observable object์ ์ธ์คํด์ค๋ฅผ view์ initializer์ ํต๊ณผ์ํต๋๋ค.

  ```swift
  struct MeetingView: View {
      @StateObject var scrumTimer = ScrumTimer()
      var body: some View {
          VStack {
            ChildView(timer: scrumTimer)
          }
      }
      // ...
  }
  ```
  ```swift
  struct ParentView: View {
      @StateObject var scrumTimer = ScrumTimer()
      var body: some View {
          VStack {
            ChildView()
                .environmentObject(scrumTimer)
          }
      }
  }
  ``` -->

## Responding to Events  

### Scene Architecture  

  App state์ ๋ํด ์์๋ณด๊ธฐ ์ ์, SwiftUI๊ฐ scenes๋ฅผ ๊ตฌ์ฑํ๋ ๋ฐฉ๋ฒ์ ๋ํด ๋ณต์ตํด ๋ด๋๋ค.  
  Scene์ ์์คํ์ด ๊ด๋ฆฌํ๋, ๋ผ์ดํ ์ฌ์ดํด์ ๊ฐ์ง๊ณ  ์๋ ์ฑ์ ์ฌ์ฉ์ ์ธํฐํ์ด์ค์ ๋ถ๋ถ์๋๋ค.

  - ์ฑ์ ๋ง๋ค๊ธฐ ์ํด์, App protocol์ ๋ฐ๋ฅด๋ structure๋ฅผ ์ ์ํฉ๋๋ค. @main attribute๋ฅผ ์์ ํ์ํด์ค์ผ๋ก์จ ์์คํ์๊ฒ ์ด structure๊ฐ ์ฑ์ entry point๋ผ๋ ๊ฒ์ ์๋ ค์ค๋๋ค.

  - ScrumdingerApp.swift์ structrue์ body ๋ถ๋ถ์ Scene ํ๋กํ ์ฝ์ ๋ฐ๋ฅด๋ scenes๋ฅผ ์ถ๊ฐํ์ต๋๋ค. Scenes๋ ์ฑ์ด ๋ณด์ฌ์ฃผ๋ ๋ทฐ ๊ณ์ธต์ ๋ด๋ ์ปจํ์ด๋ ์๋๋ค.

  - SwiftUI๋ WindowGroup๊ณผ ๊ฐ์ scenes๋ฅผ ์ ๊ณตํฉ๋๋ค. ์์คํ์ scenes์ ๋ผ์ดํ ์ฌ์ดํด์ ๊ด๋ฆฌํ๊ณ  ํ๋ซํผ์ ๋ง๋, ํ๊ฒฝ์ ๋ง๋ ๋ทฐ ๊ณ์ธต์ ํ๋ฉด์ ๋ณด์ฌ์ค๋๋ค. ์๋ฅผ๋ค์ด iPadOS์ ๋ฉํฐํ์คํน์ ๊ฐ์ ์ฑ์ ์ฌ๋ฌ๊ฐ์ ๋ ์์ ์ธ์คํด์ค๋ค์ ๋์์ ๋ณด์ฌ์ค ์ ์์ต๋๋ค.

### Scene Phases and Transitions  

  ์ฑ์ ์คํ ์ค, scene์ 3๋จ๊ณ์ ๋ณํ๊ฐ ์์ ์ ์์ต๋๋ค.

  - active : scene์ด foreground์ ์๊ณ , ์ฌ์ฉ์๊ฐ scene๊ณผ ์ํธ์์ฉํ  ์ ์์ต๋๋ค.
  - inactive : scene์ ๋ณผ ์ ์์ง๋ง ์์คํ์ด scene๊ณผ์ ์ํธ์์ฉ์ ์ค์ง์ํต๋๋ค. ์๋ฅผ ๋ค์ด ๋ฉํฐ ํ์คํน ๋ชจ๋์์ ์ฑ์ ํจ๋ ๋ณผ ์ ์์ง๋ง ํจ๋์ด ํ์ฑํ๋์ด ์์ง๋ ์์ต๋๋ค.
  - background : ์ฑ์ ์๋๋๊ณ  ์์ง๋ง scene์ ๋ณผ ์ ์์ต๋๋ค. ์ฑ์ ์ข๋ฃ ์ ์ scene์ ์ด ๋จ๊ณ์ ๋ค์ด๊ฐ๋๋ค.

## Managing State and Life Cycle  

  Scrumdinger๋ scrum์ด ๋ฐ๋ ๋๋ง๋ค ๋ฐ๋์๋ค๋ ๊ฒ์ ์ฌ์ฉ์์๊ฒ ์๋ ค์ค๋๋ค. ์ด key feature์ ๋ง๋ค๊ธฐ ์ํด scrum์ ๊ด๋ฆฌํ๋ ๋ชจ๋ธ์ ์ ์ดํ๋ life cycle methods๋ฅผ ์ฌ์ฉํ  ๊ฒ์๋๋ค.  

  ์ด ํํ ๋ฆฌ์ผ์์๋ reference type models์ SwiftUI view๋ฅผ ์ด์ฉํ๋ ๋ฐฉ๋ฒ์ ๋ํด ์์๋ด๋๋ค.

### Create an Overlay View  

  MeetingView.swift์ header ๋ถ๋ถ์ ๋ฐ๋ก ๋ถ๋ฆฌํฉ๋๋ค. MeetingHeaderView.swift๋ผ๋ ์ SwiftUI ํ์ผ์ ์์ฑํ๊ณ  ProgressView์ HStack ๋ถ๋ถ์ MeetingHeaderView.swift๋ก ์ฎ๊ฒจ ์ค๋๋ค. ๊ทธ๋ฆฌ๊ณ  ์ง๊ธ๊น์ง static ๋ฐ์ดํฐ๋ฅผ dynamic ๋ฐ์ดํฐ๋ก ๊ต์ฒดํ๊ธฐ ์ํด ์์ฑ์ ์ถ๊ฐํ  ๊ฒ์๋๋ค.

  ```swift
  private var totalSeconds: Int {
      secondsElapsed + secondsRemaining
  }
  private var progress: Double {
      guard totalSeconds > 0 else { return 1 }
      return Double(secondsElapsed) / Double(totalSeconds)
  }
  ```
  ProgressView์์ progress๋ฅผ ๋ํ๋ด๋ computed property์๋๋ค. totalSeconds๊ฐ 0๋ณด๋ค ํฌ๋ฉด ์ง๋ ์๊ฐ์ ์ ์ฒด ์๊ฐ์ผ๋ก ๋๋์ด์ ์งํ๋ ์๊ฐ์ ๋ํ๋ด์ค๋๋ค.

### Add a State Object for a Source of Truth  

  Value type models์ source of truth๋ฅผ ์์ฑํ๊ธฐ ์ํด์ **@State** ๋ฅผ ์ฌ์ฉํ์ต๋๋ค. ObservableObject ํ๋กํ ์ฝ์ ๋ฐ๋ฅด๋ reference type models์ source of truth๋ฅผ ์์ฑํ๊ธฐ ์ํด์๋ **@StateObject** ๋ฅผ ์ฌ์ฉํฉ๋๋ค.

  ```swift
  struct MeetingView: View {
    @Binding var scrum: DailyScrum
    @StateObject var scrumTimer = ScrumTimer()
    // ...
  }
  ```
  @StateObject๋ก ์์ฑ์ wrapping ํ๋ค๋ ๊ฒ์ ์ํ ํด๋น view๊ฐ ๊ทธ object์ source of truth๋ฅผ ์์ ํ๋ค๋ ๊ฒ์ ์๋ฏธํฉ๋๋ค. @StateObject๋ ScrumTimer๋ฅผ MeetingView life cycle์ ์๋ฐ์ํต๋๋ค.

## Persisting data  

### Add a Method to Load Data  

  ```swift
  import Foundation
  import SwiftUI

  // ObservableObject๋ class-constrained protocol -> ์ธ๋ถ์ ๋ชจ๋ธ ๋ฐ์ดํฐ๋ฅผ SwiftUI ๋ทฐ์ ์ฐ๊ฒฐ
  class ScrumStore: ObservableObject {
      @Published var scrums: [DailyScrum] = []

      // ์ฌ์ฉ์์ Documents ํด๋ ์ ํ์ผ์ scrums๋ฅผ ์ ์ฅํ๊ณ  ๊ฐ์ ธ์ฌ ๊ฒ.
      // ์๋ function์ ํ์ผ์ ์ฝ๊ฒ ์ ๊ทผํ๊ธฐ ์ํด ์ฌ์ฉ๋จ.
      private static func fileURL() throws -> URL {
          // default file manager์ url์ ํธ์ถ
          // ํ ์ฌ์ฉ์์ documents ์์น๋ฅผ ๊ฐ์ ธ์ค๊ธฐ ์ํด FileManager์ shared instance ์ฌ์ฉ.
          try FileManager.default.url(for: .documentDirectory, in: .userDomainMask, appropriateFor: nil, create: false)
              // scrms.data๋ผ๋ ์ด๋ฆ์ ๊ฐ์ง ํ์ผ์ URL์ ๋ฆฌํด
              .appendingPathComponent("scrums.data")
      }
  }
  ```

#### Dispatch queues  

  Dispatch queues๋ first in, first out queue์ด๋ค.

<!-- ### Add Life Cycle Events  

  SwiftUI๋ view๊ฐ ๋ํ๋๊ณ  ์ฌ๋ผ์ง ๋ ์ด๋ฒคํธ๋ฅผ ์ผ์ผํค๋ life cycle methods๋ฅผ ์ ๊ณตํฉ๋๋ค. -->
