---
title: "Subscripts"
categories:
  - TIL
tags:
  - learning
  - ๊ณต๋ถ ๊ธฐ๋ก
  - Swift
  - Subscripts
show_date: true
toc: true
toc_sticky: true
toc_label: " "
toc_icon: "kiwi-bird"
#header:
#  teaser: /assets/images/choose2.png
---

# ๐ฉโ๐พ ..

  Classes, structures, ๊ทธ๋ฆฌ๊ณ  enumerations๋ subscripts๋ฅผ ์ ์ํ  ์ ์์ต๋๋ค. Subscripts๋ collection์ด๋ list ๋๋ sequence์ ๋ฉค๋ฒ ์์์ ์ ๊ทผํ๋ ์ฌ์ด ๋ฐฉ๋ฒ๋ค์๋๋ค. ๊ฐ์ ์ค์ ํ๊ณ  ๊ฐ์ ธ์ค๊ธฐ ์ํ ๋ฉ์๋ ์์ด subscripts๋ฅผ ์ฌ์ฉํ์ฌ ์ธ๋ฑ์ค๋ก ๊ฐ์ ์ค์ ํ๊ฑฐ๋, ๊ฐ์ ๊ฐ์ ธ์ต๋๋ค. ์๋ฅผ ๋ค์ด, someArray[index]๋ก Array instance์ ์์์ ์ ๊ทผํ  ์ ์์ต๋๋ค. Dictionary instance์ ์์์ ์ ๊ทผํ๊ธฐ ์ํด์๋ someDictionary[key]๋ฅผ ์ด์ฉํฉ๋๋ค.  

  ํ๋์ ํ์์ ์ฌ๋ฌ๊ฐ์ subscripts๋ฅผ ์ ์ํ  ์ ์์ต๋๋ค. Subscript์ ํต๊ณผ๋ ์ธ๋ฑ์ค ๊ฐ์ ํ์์ ๊ธฐ์ค์ผ๋ก ๊ทธ ์ค ์ ํฉํ subscript๊ฐ ์ ํ๋ฉ๋๋ค. Subscript๋ 1์ฐจ์์ ์ ์ฝ๋์ง ์์ต๋๋ค. ์ปค์คํ ํ์์ด ํ์๋ก ํ๋ ์ฌ๋ฌ๊ฐ์ input ํจ๋ฌ๋ฏธํฐ๋ฅผ ์ด์ฉํ์ฌ subscript๋ฅผ ์ ์ํ  ์ ์์ต๋๋ค.


## Subscript Syntax

  Subscript๋ ํ๋ ๋๋ ์ฌ๋ฌ๊ฐ์ ๊ฐ์ instance์ ์ด๋ฆ ๋ค [] ์์ ์์ฑํจ์ผ๋ก์จ ์ธ์คํด์ค์ ๋ํ ์ ๋ณด๋ฅผ ๊ฐ์ ธ์ค๋ ๊ฒ์ ๊ฐ๋ฅํ๊ฒ ํฉ๋๋ค. Subscript syntax๋ instance method syntax ๊ทธ๋ฆฌ๊ณ  commputed property syntax์ ๋น์ทํฉ๋๋ค. subscript keyword๋ฅผ ์ฌ์ฉํ๊ณ  ํ๋ ๋๋ ์ฌ๋ฌ๊ฐ์ ์ธํ ํจ๋ฌ๋ฏธํฐ์ ๋ฆฌํด ํ์์ ํน์  ์ง์ด ์ค๋๋ค. (instance method์ ๊ฐ์ ๋ฐฉ๋ฒ์ผ๋ก)  
  Instance method์๋ ๋ค๋ฅด๊ฒ, subscript๋ read-write ๋๋ read-only๊ฐ ๋  ์ ์์ต๋๋ค. Computed property์์์ ๋ง์ฐฌ๊ฐ์ง๋ก getter ๊ทธ๋ฆฌ๊ณ  setter์ ์ํด ์คํ๋ฉ๋๋ค.

  ```swift
  subscript(index: Int) -> Int {
    get {
        // ์ ํฉํ subscript ๊ฐ์ ๋ฆฌํด
    }
    set(newValue) {
        // ์ ํฉํ setting action ์ํ
    }
  }
  ```

  newValue์ ํ์์ subscript์ ๋ฆฌํดํ์๊ณผ ๊ฐ์ต๋๋ค. Computed property์์์ฒ๋ผ, setter์ (newValue)ํจ๋ฌ๋ฏธํฐ๋ฅผ ํน์ ์ง์ง ์์ ์ ์์ต๋๋ค. ๋ง์ฝ ์ด๋ ๊ฒ ํน์ ์ง์ง ์๋๋ค๋ฉด newValue๋ผ๋ ์ด๋ฆ์ ๋ํดํธ ํจ๋ฌ๋ฏธํฐ๊ฐ ์ ๊ณต๋ฉ๋๋ค.  

  read-only computed property์ฒ๋ผ, get ํค์๋์ { } ๋ฅผ ์ ๊ฑฐํ์ฌ read-only subscript๋ฅผ ๋จ์ํ ํํ๋ก ์ ์ํ  ์ ์์ต๋๋ค.

  ```swift
  subscript(index: Int) -> Int {
        // ์ ํฉํ subscript ๊ฐ์ ๋ฆฌํด
  }
  ```

  ์๋๋ read-only subscript์ ๊ตฌํ ์์์๋๋ค. TimesTable stucture๋ ํ ์ ์์ n-times-table์ ๋ํ๋๋๋ค.

  ```swift
  struct TimesTable {
      let multiplier: Int
      subscript(index: Int) -> Int {
          return multiplier * index
      }
  }
  let threeTimesTable = TimesTable(multiplier: 3)
  print("six times three is \(threeTimesTable[6])")
  // Prints "six times three is 18"
  ```

  ์์ ์์์, TimesTable์ ์ instance๋ three-times-table์ ๋ํ๋ด๊ธฐ ์ํด ์์ฑ๋์์ต๋๋ค. ์ด๊ฒ์ TimesTable structure์ ์์ฑ์ multiplierํจ๋ฌ๋ฏธํฐ์ ๊ฐ 3์ ํต๊ณผ์ํด์ผ๋ก์จ ์ด๋ฃจ์ด์ง๋๋ค.  

  threeTimesTable์ subscript๋ฅผ ํธ์ถํจ์ผ๋ก์จ ์ ๋ณด๋ฅผ ๊ฐ์ ธ์ฌ ์ ์์ต๋๋ค. (threeTimesTable[6])

## Subscript Usage  

  "subscript"์ ์ ํํ ์๋ฏธ๋ ์ด๊ฒ์ด ์ฌ์ฉ๋ ๊ณณ์ ์ ํ ๊ด๊ณ์ ๋ฌ๋ ค์์ต๋๋ค. Subscripts๋ ๋ณดํต collection, list ๋๋ sequence์ ์์์ ์ ๊ทผํ๋ ์ง๋ฆ๊ธธ(์ฌ์ด ๋ฐฉ๋ฒ)์ผ๋ก ์ฌ์ฉ๋ฉ๋๋ค.

  ์๋ฅผ ๋ค์ด, Swift์ Dictionary type์ ์ด๋ค Dictionary instance์ ์ ์ฅ๋ ๊ฐ์ ๊ฐ์ ธ์ค๊ฑฐ๋, ๊ฐ์ ์ค์ ํ๊ธฐ ์ํด subscript๋ฅผ ์ฌ์ฉํฉ๋๋ค. ๋์๋๋ฆฌ์ ํค ํ์์ ๋ง๋ ํค๋ฅผ subscript brackets์์ ์ ๊ณตํ๊ณ  ๋์๋๋ฆฌ์ ๊ฐ ์๋ฃํ๊ณผ ์ผ์นํ๋ ๊ฐ์ ํ ๋นํด์ค์ผ๋ก์จ ํค์ ๊ฐ์ ์ค์ ํ  ์ ์์ต๋๋ค.

  ```swift
  var numberOfLegs = ["Spider": 8, "ant": 6, "cat": 4]
  numberOfLegs["bird"] = 2
  ```

<!-- ## Subscript Options  

  Subscripts๋  -->
