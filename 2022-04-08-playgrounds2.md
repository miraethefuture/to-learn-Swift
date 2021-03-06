---
title: "Playgrounds: Learn to Code 2"
categories:
  - TIL
tags:
  - learning
  - ๊ณต๋ถ ๊ธฐ๋ก
  - Swift
  - Playgrounds
show_date: true
toc: true
toc_sticky: true
toc_label: "๐ท"
toc_icon: "kiwi-bird"
---

# Learn to code 2
<sub>์๋ ๋ชจ๋  ๋ด์ฉ๋ค์ Playgrounds์์ ํ์ตํ๋ฉฐ ์ ๋ฆฌํ ๋ด์ฉ์๋๋ค.  
  ๋ชจ๋  ๋ด์ฉ์ ์ถ์ฒ๋ Playgrounds์์ ๋ฐํ๋๋ค.</sub>

## Variables

  ๋จธ๋ฆฌ๋ก ๊ธฐ์ตํ  ์ ์๋ ๊ฒ๋ณด๋ค ๋ ๋ง์ ์ฐ๋ฝ์ฒ๋ฅผ ์ ์ฅํ ์ค๋งํธํฐ์ ์ฐ๋ฝ์ฒ ๋ชฉ๋ก์ ๋ ์ฌ๋ ค ๋ด์๋ค. Coder๋ ๋ณ์(Variables)๋ผ๋ ์ปจํ์ด๋์ ์ด๋ฆ์ ๋ถ์ด๊ณ 
  ์ ๋ณด๋ฅผ ๋ด์ต๋๋ค. ์ฐ๋ฆฌ๊ฐ ์์ ํ๊ธฐ ์ ๊น์ง๋ ์ฐ๋ฝ์ฒ์ ์ ๋ณด๊ฐ ๋ฐ๋์ง ์๋ฏ Variables์ ์ ๋ณด๋ ์ฐ๋ฆฌ๊ฐ ๋ณ๊ฒฝํ๊ธฐ ์ ๊น์ง ์ค์ค๋ก ๋ฐ๋์ง ์์ต๋๋ค.

  ```swift
  var name = "Mia"
  var age = "28"
  ```

  1. var ํค์๋๋ฅผ ์ฌ์ฉํฉ๋๋ค.
  2. ๋ณ์์ ์ด๋ฆ(name, age)์ด ํ์ํฉ๋๋ค.
  3. = (assignment operator, the equal sign)์ ๋ณ์์ ๊ฐ์ ํ ๋นํฉ๋๋ค.
  4. ์์ ๋ณ์ ์ค name์ String์ ๋ด๊ณ  ์์ต๋๋ค. ("text")
  5. ์์ ๋ณ์ ์ค age๋ Int(an integer, a whole number)๋ฅผ ๋ด๊ณ  ์์ต๋๋ค.

### ๐ ํ์ ์์ด ๋จ์ด: a whole number
  <div class="notice">
     <h4>whole numbers</h4>
     <p>0์ ํฌํจํ ์์ฐ์๋ฅผ ๋งํฉ๋๋ค.<br>
     0, 1, 2, 3, 4, .... </p>
  </div>

  ๋ณ์๋ฅผ ํ ๋นํ ๋ค ๋ค๋ฅธ ๊ฐ์ ํ ๋นํ  ์ ์์ง๋ง ์๋ฃํ์ ์ฒ์ ํ ๋นํ ๊ฐ๊ณผ ๊ฐ์์ผ ํฉ๋๋ค. ๋ง์ฝ ์ฒ์ String ํ์์ ์๋ฃ๋ฅผ ๋ด์๋ค๋ฉด ๊ทธ ๋ณ์์๋ ๊ฒ์ํด์ String ํ์์ ์๋ฃํ์ ๋ด์์ผ ํฉ๋๋ค.

  ```swift
  var age = 28
  age = "twenty-nine" // ์๋ฃํ์ด ๋ค๋ฆ์ผ๋ก ๋ถ๊ฐ๋ฅ
  ```

### incrementing a value

  incrementing a value๋ ํ์ฌ ๊ฐ๊ณผ ๋น๊ตํ์ฌ ๊ฐ์ ์ฆ๊ฐ์ํค๋ ์ฝ๋ฉ ํจํด์๋๋ค.
  ```swift
  var myNum = 0
  myNum = myNum + 1
  ```
  variable์์ ํ ๋น๋ ์์ ๋น๊ต ์ฐ์ฐ์๋ฅผ ์ด์ฉํด์ while๋ฌธ์ Boolean ์กฐ๊ฑด์ ๋ง๋ค ์ ์์ต๋๋ค. incrementing values ํ๋ฉฐ ๋ฐ๋ณต ํ์ ๋ฑ์ ๊ธฐ๋กํ  ์ ์์ต๋๋ค.

### ๋ณ์ ์ด๋ฆ ์ ํ๊ธฐ

  1. camelCase: ์ฒซ๋ฒ์งธ ๋จ์ด๋ ์๋ฌธ์๋ก ์์ ๋ค๋ก ์ด์ด์ง๋ ์ ๋จ์ด๋ค์ ๋๋ฌธ์๋ก ์์ํ๋๋ก ์ฐ๋ ๋ฐฉ๋ฒ์๋๋ค.
  2. ๋ณ์์ ๋ด๊ธธ ๊ฐ์ด ๋ฌด์์ธ์ง ์๋ ค์ฃผ๋ ์ด๋ฆ์ผ๋ก ์ ํฉ๋๋ค.

### Constant

  Constant(์์)๋ variable(๋ณ์)์ ๊ฐ์ด ๊ฐ์ ๋ด๋ ์ด๋ฆ ๋ถ์ธ ์ปจํ์ด๋์๋๋ค. ํ์ง๋ง ํ๋ก๊ทธ๋จ์ด ์คํ๋๋ ๋์์๋ ๊ฐ์ ๋ณ๊ฒฝํ  ์ ์๋ค๋ ์ฐจ์ด์ ์ด ์์ต๋๋ค.

  1. 'let' ํค์๋๋ฅผ ์ฌ์ฉํฉ๋๋ค.
  2. ๊ฐ์ด ๋ณ๊ฒฝ๋์ง ์๋๋ค๋ ๊ฒ์ ์๋ ๊ฒฝ์ฐ ์์๋ฅผ ์ฌ์ฉํฉ๋๋ค.

  ```swift
  let numberOfTries = 3
  ```

  ๋ณ์์ ๊ฐ๊ณผ ์์์ ๊ฐ์ ๋น๊ตํ๋ ์์ ์ฝ๋๊ฐ ์์ฃผ ์ฌ์ฉ๋ฉ๋๋ค.

### Compound assignment operator

  ```swift
  gemCounter = gemCounter + 1
  gemCounter += 1
  ```


### ์๋ฃํ(Types)

  ์ง์ ์ง์ ๋๋ blue print๋ฅผ ์ฌ์ฉํฉ๋๋ค. Blue print๋ ๊ฑฐ์ค, ํ์ฅ์ค, ์นจ์ค๊ณผ ๊ฐ์ ์ง์ ๊ธฐ๋ฅ๋ค์ ๋ณด์ฌ์ค๋๋ค. ์ฌ๋ฌ๊ฐ์ ์ง๋ค์ ์ง์ ๋ ํ blue print๋ฅผ ์ด์ฉํ๋ค๋ฉด ๊ทธ ์ง๋ค์ ๋ชจ๋ ๋น์ทํ ๋ชจ์์ผ๋ก ์ง์ด์ง ๊ฒ์๋๋ค.
  ํ๋ก๊ทธ๋๋ฐ์์ **type**์ blue print์ ๊ฐ์ต๋๋ค. ๊ทธ๋ฆฌ๊ณ  **instance**๋ blue print๋ฅผ ํตํด ์ง์ด์ง ์ง๊ณผ ๊ฐ์ต๋๋ค.
  Blue print๋ ์ง์ ํน์ง(feature)๊ณผ ์๋ ๋ฐฉ์(behavior)์ ์๋ ค์ค๋๋ค.
  Type์์ features๋ properties๋ผ๊ณ  ๋ถ๋ฅด๊ณ  ์๋ ๋ฐฉ์(behavior)๋ method๋ผ๊ณ  ํฉ๋๋ค.

  ~~~swift
  Features: Color, Bedromms

  var color = green
  var bedrooms = 2

  // property๋ ํ์์์์ ๋ณ์์๋๋ค.
  ~~~
  ```swift
  Behaviors: Run Water, Turn on Lights

  runWater()
  turnLightsOn()

  // method๋ ํ์์์์ function์๋๋ค.
  ```

  ์ฐ๋ฆฌ๊ฐ ๋ง๋  ์ฌ๋ฌ๊ฐ์ ์ง์ค ํ๋์ ์ฐจ๊ณ ๋ฅผ ์ด๊ณ  ์ถ๋ค๊ณ  ๊ฐ์ ํด๋ด๋๋ค. ๋จผ์  ์ฐ๋ฆฌ๋ ์ด๋ค ์ง์ธ์ง ์ด๋ฆ์ ํตํด ์ง์ ํฉ๋๋ค.

  ```swift
  myHouse.openGarageDoor()
  ```
  Swift์์ .(dot notation) ์๋ถ๋ถ์ธ myHouse๋ ํน์ ํ ์ง์ ๊ฐ๋ฆฌํค๋ instance์๋๋ค.
  . ๋ท๋ถ๋ถ์ openGarageDoor()๋ผ๋ myHouse์ ๋ฉ์๋์๋๋ค.

  ```swift
  bluePortal.isActive() = false
  ```
  bluePortal์ด๋ผ๋ ์ธ์คํด์ค์ isActive()๋ผ๋ ๋ฉ์๋๊ฐ bluePortal์ ์ผ ๋ค๊ณ  ๊ฐ์ ํ์ ๋ '= false'๋ bluePortal์ ๋๋๋ค.

### Using dot notation syntax

  ์ปดํจํฐ๊ฐ ์ดํดํ  ์ ์๋ ์ฝ๋๋ฅผ ์์ฑํ๋ ๊ท์น์ syntax๋ผ๊ณ  ํฉ๋๋ค. Dot notation systax๋ ์๋์ ๊ฐ์ด ์๊ฒผ์ต๋๋ค.
  ```swift
  greenPortal.isActive = true
  ```
  Dot notation์ ์ด์ฉํ๋ฉด ํน์  instance์ properties์ ์ํ๋ฅผ ๋ณ๊ฒฝ์ํฌ ์ ์์ต๋๋ค. ๋๋๋ก ํ๋ก๊ทธ๋จ ์์์ ์ฌ๋ฌ๋ฒ instance์ propert์ ์ํ๋ฅผ ๋ณ๊ฒฝํด์ผํฉ๋๋ค. greenPortal์ instance์ ์ด๋ฆ์ด๊ณ  isActive๋ greenPortal์ property์๋๋ค.

  **State**
  State๋ ์ด๋ค ์ฃผ์ด์ง ํน์  ์๊ฐ์ ๋ณ์์ ๋ด๊ธด ์ ๋ณด๋ฅผ ๋งํฉ๋๋ค.

  instance์ ์ด๋ฆ์ ๋ถ์ฌํ๊ณ  ์ด๋ฆ์ผ๋ก ๊ทธ๊ฒ์ ๋ํ๋ด๋ ๊ฒ์ ํ๋ก๊ทธ๋จ ์์์ ์ธ์คํด์ค์ ์์๋ค์ ์ด์ฉํ  ์ ์๊ฒ ํด์ค๋๋ค.

  ๋ ํจ์จ์ ์ธ ๋ฌธ์  ํด๊ฒฐ๋ฒ์ ์ฐพ๋ ๊ฒ์ ํ๋ก๊ทธ๋จ์ด ๋ ๋น ๋ฅด๊ฒ ์๋ํ๋ค๋ ๊ฒ์ด๊ณ  ๊ทธ๊ฒ์ ์ฌ์ฉ์๋ค์ด ์ฑ์ ์ฌ์ฉํ  ๋ ํ๋ณตํด์ง๋ค๋ ๊ฒ์๋๋ค. ๊ทธ๋ฆฌ๊ณ  ๋ฐฐํฐ๋ฆฌ๊ฐ ์ผ๋งํผ ์ค๋ ๋ณด์กด๋๋์ง์๋ ๊ด๋ จ์ด ์์ต๋๋ค.

### Factoring

  ์ฝ๋๋ฅผ ํจ์จ์ ์ผ๋ก ์์ฑํ๋ ๋ฐฉ๋ฒ์ ๋ํด ์๊ฐํด๋ณด๋ ๊ฒ์ ์ค์ํฉ๋๋ค. ์๋ํ๋ ๋ฐฉ์์ ์์ ๋จ์๋ก ๋๋์ด ์ฌ์ฌ์ฉ ๊ฐ๋ฅํ function์ ์์ฑํ๋ค๋ฉด ์ ์ฒด์ ์ผ๋ก๋ ๋ ์ ์ ๋ผ์ธ์ ์๋ก ์ฝ๋๋ฅผ ์์ฑํ  ์ ์์ต๋๋ค. ์ด๋ฐ ๊ฒ์ factoring ์ฝ๋๋ผ๊ณ  ํฉ๋๋ค. factoring the code๋ ์ฌ์ฌ์ฉ์ฑ์ ๋์ฌ์ค ๋ฟ ์๋๋ผ ์ฝ๋์ ๊ฐ๋์ฑ์ ๋์ฌ์ฃผ์ด ์์ฑ์ ๋ฟ ์๋๋ผ ๋ค๋ฅธ ๋๊ตฌ๋  ์ฝ๋๊ฐ ์ด๋ป๊ฒ ์์ฑ๋๊ฑด์ง ์์๋ณด๊ธฐ ์ฝ๊ฒ ํด์ค๋๋ค.

  //๐ทโโ๏ธ Learn to Code 2: Random Gems Everywhere ๋ค์ ํ๊ธฐ

### Initialization

  Initialization์ ํตํด instance๋ฅผ ๋ง๋ค ์ ์์ต๋๋ค.

  ```swift
  let expert = Expert()
  ```
  1. let ํค์๋๋ฅผ ์ฌ์ฉํ์ฌ constant๋ฅผ ์์ฑํฉ๋๋ค.
  2. Type์ ์ด๋ฆ + ()๋ฅผ ์ฐ์ธก์ ์์ฑํ์ฌ ์ด๊ธฐํ(Initialize) ํฉ๋๋ค.

  ```swift
  expert.turnLockUp()
  ```
  expert๋ผ๋ instance์ ๋ฉ์๋ turnLockUp()์ ํธ์ถํ๋ ๋ฐฉ์์๋๋ค. dot notation์ ์ฌ์ฉํฉ๋๋ค. ๋ฉ์๋๋ฅผ ์ฌ์ฉํ๊ธฐ ์ํด์๋ ๋จผ์  Initialize ํด์ฃผ์ด์ผ ํ๋ค๋ ๊ฒ์ ๊ธฐ์ตํฉ์๋ค.

### ์ฌ๋ฌ๊ฐ์ instances

  ์ฝ๋๋ฅผ ์์ฑํ  ๋๋ ํฐ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๊ธฐ ์ํด ๋ณดํต ์ฌ๋ฌ๊ฐ์ instance์ element๋ฅผ ํจ๊ป ์ฌ์ฉํ๊ฒ ๋ฉ๋๋ค. ๋ง์ฝ ์ฌ์ง ํธ์ง ์ฑ์ ๋ง๋ ๋ค๋ฉด ์ด๋ฏธ์ง๋ฅผ ์ดฌ์ํ๊ธฐ ์ํด ์นด๋ฉ๋ผ ์ฑ์, ํจ๊ณผ๋ฅผ ์ ์ฉํ๊ธฐ ์ํด ํํฐ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ์ฌ์ฉํ  ๊ฒ์๋๋ค.

  ํ๋ ์ด์์ instance๋ฅผ ์ฌ์ฉํ  ๋๋ instance์ ์ด๋ฆ์ ์ฌ์ฉํ์ฌ ๊ฐ instance์ ๋ฉ์๋๋ฅผ ํธ์ถํฉ๋๋ค.

### Parameters

  ์ง์ ์ฌ๋ฌ๊ฐ์ง ์์ผ๋ก ํ์ธํธ ์น ํ๋ค๊ณ  ์์ํด ๋ด๋๋ค. ๊ทธ๋ ๋ค๋ฉด ์๋ง๋ค ๊ฐ๊ธฐ ๋ค๋ฅธ ๋ฉ์๋๋ฅผ ๋ง๋ค ์ ์๊ฒ ์ฃ .
  ~~~swift
  paintGreen()
  paintBlue()
  paintOrange()
  ~~~
  ๋ง์ฝ ์ด๋ก์ ํ์ธํธ๋ก ์ธ ๋ ์ด์ด์ ๊ฑธ์ณ ์์ ์น ํ๊ณ  ์ถ๋ค๋ฉด ์๋์ฒ๋ผ ์ธ๋ฒ paintGreen() ๋ฉ์๋๋ฅผ ํธ์ถํ  ์ ์์ต๋๋ค.
  ```swift
  paintGreen()
  paintGreen()
  paintGreen()
  ```

  ๊ฐ ์๋ง๋ค function์ ๋ง๋ค์ด ์ฌ์ฉํ  ๋์ ์ Parameter๋ฅผ ์ด์ฉํด์ ์ํ๋ ์์ ์ฌ์ฉํ  ์ ์์ต๋๋ค.
  ```swift
  func paint(color: Color)
  ```
  color parameter๋ function์ input value์๋๋ค. ํจ๋ฌ๋ฏธํฐ๋ Color์ ๊ฐ์ ํน์ ํ Type์ ๊ฐ์ง๋๋ค. function์ ํธ์ถํ๋ฉด ์๋๋ฐฉ์ ์ค ์ฌ์ฉํ  argument๋ฅผ ํต๊ณผ ์ํต๋๋ค.
  ```swift
  func paint(color: Color, layers: 3)
  ```
  ์ฌ๋ฌ๊ฐ์ ํจ๋ฌ๋ฏธํฐ๋ฅผ ๊ฐ์ง ์ ์์ต๋๋ค.

  ```swift
  func move(count: Int) {
    for i in 1...count {
      moveForward()
    }
  }
  ```
  Int Type์ count๋ผ๋ ํจ๋ฌ๋ฏธํฐ๋ฅผ ๊ฐ์ง function move์๋๋ค. count๋ function์ ๋ฐ๋ ๋ถ๋ถ์์ for๋ฌธ์ด ์ผ๋งํผ ๋ฐ๋ณต๋ ์ง๋ฅผ ํน์ ํฉ๋๋ค. move function์ ํธ์ถ ์
  ```swift
  move(count: 3)
  ```
  argument 3์ ํต๊ณผ์ํด์ผ๋ก์จ for๋ฌธ์ ์ธ๋ฒ ๋๋ฆด ์ ์๊ฒ ๋ฉ๋๋ค.

   ์ฌ๋ฌ๊ฐ์ parameter๋ฅผ ์ด์ฉํ๋ฉฐ function์ด ๋์ํ๋ ์ค ๋ง์ ๋ถ๋ถ์ ์ปค์คํฐ๋ง์ด์ง ํ  ์ ์์ต๋๋ค. ๋ช ๋ฒ ๋ฐ๋ณต๋ฌธ์ ๋์์ํฌ์ง, Boolํ์์ ์ด์ฉํ๋ค๋ฉด ๋์์ ์ํฌ์ง ์ํค์ง ์์์ง ๋ฑ ๋ง์ ๋ถ๋ถ์ ์ํ๋๋๋ก ํน์  ์ง์ ์ ์์ต๋๋ค.

### ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๋ฉฐ ์์ฑํด ๋ณธ ์์  ์ฝ๋

   ```swift
   let expert = Expert()
   let character = Character()

   var gemCount = 0

   func turnMethod(up: Bool, times: Int) {
       if up == true {
           for i in 1...times {
               expert.turnLockUp()
           }
           expert.turnRight()
       } else {
           for i in 1...times {
               expert.turnLockDown()
           }
           expert.turnRight()
       }
   }

   for i in 1...4 {
       turnMethod(up: true, times: 4)
   }

   while gemCount != 3 {
       if character.isOnGem {
           character.collectGem()
           gemCount += 1
           character.turnRight()

       }
       character.moveForward()
   }

   for i in 1...4 {
       turnMethod(up: false, times: 3)
   }

   while gemCount < 7 {
       if !character.isBlockedRight && gemCount > 5 {
           character.moveForward()
       } else if character.isBlockedRight && character.isBlockedLeft{
           character.moveForward()
       } else if !character.isBlockedRight {
           character.turnRight()
           character.moveForward()
       } else if character.isBlockedRight && gemCount == 6 {
           character.moveForward()
       }

       if character.isOnGem {
           character.collectGem()
           gemCount += 1
           character.turnLeft()
           character.turnLeft()
           character.moveForward()
       }
   }
   ```
  (ํจ๋ฌ๋ฏธํฐ๋ฅผ ์ด์ฉํ funtion์ ์ด์ฉ์ ๊ณต๋ถํ๋ฉฐ ์์ฑํด๋ณธ ์์ ์๋๋ค. ๋ ์ ์ ๋ผ์ธ์ ์ฝ๋๋ก ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ  ์ ์์ ๊ฒ ๊ฐ์๋ฐ ์์ง์ ์๊พธ๋ง ์ฝ๋๊ฐ ๊ธธ์ด์ง๋๋ค.)

### Type๊ณผ Instances

  ํ๋์ type์ ์ด์ฉํด ์ฌ๋ฌ๊ฐ์ instance๋ฅผ ๋ง๋ค ์ ์์ต๋๋ค. type์ ์ค๊ณ๋, ์ฒญ์ฌ์ง์ ์์ฃผ ๋น์ ๋ฉ๋๋ค. ๊ฐ์ ์ค๊ณ๋๋ฅผ ์ฌ์ฉํด์ ๋ง๋  instance์ด๋ฏ๋ก ๊ฐ์ ๋ฉ์๋๋ฅผ ์ฌ์ฉํด ๊ฐ์ ์์ฑ๋ค์ ์ ๊ทผ, ์ด์ฉํ  ์ ์์ต๋๋ค.

### World Building

  ```swift
  let block1 = Block()
  let block2 = Block()
  let block3 = Block()
  let block4 = Block()
  let block5 = Block()

  var gemCounter = 0

  func stackBlocks(block: Block, col: Int, row: Int) {
          world.place(block, atColumn: col, row: row)
  }
  func turnAround() {
      turnLeft()
      turnLeft()
  }
  func moveAndCollect(times: Int) {
      for i in 1...times {
          moveForward()
          if isOnGem {
              collectGem()
              turnAround()
          }
      }
  }

  // stack blocks to get gems
  stackBlocks(block: block1, col: 2, row: 2)
  stackBlocks(block: block2, col: 2, row: 2)
  stackBlocks(block: block3, col: 4, row: 2)
  stackBlocks(block: block4, col: 6, row: 2)
  stackBlocks(block: block5, col: 6, row: 2)

  while gemCounter < 3 {
      moveForward()
      if isOnClosedSwitch {
          toggleSwitch()
          turnRight()
      } else if isBlocked && isOnGem {
          collectGem()
          gemCounter += 1
          turnAround()
      } else if isOnOpenSwitch && gemCounter >= 1{
          turnRight()
      }
  }
  ```
  (์ฌ๋ฌ๊ฐ์ instance ์ฌ์ฉ / factor codes into a function์ ๊ณต๋ถํ๋ฉฐ ์์ฑํ ์์ . ์ฒ์ ์์ฑํ์๋๋ else if๊ฐ ์ธ๊ฐ ๋ ์์๋๋ฐ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๋ฉฐ ์ฝ๋๋ฅผ ์ค์ผ ์ ์์๋ค.)

## Array

  - [] = square brakets
  - , = a comma

  ์ ๋๊ฐ์ง๋ฅผ ์ด์ฉํ์ฌ ๋ฐฐ์ด(Array)๋ฅผ ๋ง๋ญ๋๋ค.

  ```swift
  var ingredients = [icecream, bananas, chocolate, cherries]
  ```

  ๋ฐฐ์ด์ ์์ดํ์ ์์๋๋ก ๋์ดํ ๋ชฉ๋ก์๋๋ค. ์์๋ Index๋ก ํํํฉ๋๋ค. Index๋ฅผ ์ด์ฉํ์ฌ ๊ฐ item์ ๋ณ๊ฒฝํ  ์ ์์ต๋๋ค.

  ```swift
  [icecream, bananas, chocolate, cherries]
      0         1         2          3

  ingredients[1] = strawberries
  ingredients[3] = sprinkles

  [icecream, strawberries, chocolate, sprinkles]
      0           1            2          3
  ```

  ์ปดํจํฐ๋ 0๋ถํฐ ์๋ฅผ ์ธ๊ธฐ ๋๋ฌธ์ index ์ญ์ 0๋ถํฐ ์์ํฉ๋๋ค.

### Array Methods

  Swift์๋ ์์ดํ์ ์ญ์ , ์ถ๊ฐํ๋ ๋ฑ ๊ฐ๋จํ ๋์์ ์ํํ๊ธฐ ์ํด array์ ํจ๊ป ์ฌ์ฉ๋๋ ๋ฉ์๋๊ฐ ์์ต๋๋ค.

  ```swift
  [icecream, bananas, chocolate, cherries]
      0         1         2          3

  // remove(at: index numbers) ๋ฉ์๋
  ingredients.remove(at: 2)

  [icecream, bananas, cherries]
      0         1         2

  // append() ๋ฉ์๋
  ingredients.append(sprinkles)

  [icecream, bananas, cherries, sprinkles]
      0         1         2         3

  // insert(item, at: index number)
  ingredients.insert(strawberries, at: 1)

  [icecream, strawberries, bananas, cherries, sprinkles]
      0            1         2         3          4
  ```
  item์ด ์ถ๊ฐ, ์ญ์ ๋จ์ ๋ฐ๋ผ index ๋ฒํธ๊ฐ ์๋์ผ๋ก ๋ฐ๋๋๋ค.

### Iteration

  ๋ฐฐ์ด์ ๋ด๊ธด ๊ฐ ์์ดํ๋ง๋ค ๊ฐ์ ๋์์ ๋ฐ๋ณตํ  ์ ์์ต๋๋ค. ์ด๋ฐ ๊ณผ์ ์ **iteration** ์ด๋ผ๊ณ  ํฉ๋๋ค.

  ```swift
  for item in ingredients {
    place(item, in: bowl)
  }
  ```

  ์ ์ฝ๋๋ ๊ฐ item ๋ง๋ค place(item, in: bowl) ์ด๋ผ๋ ์ฝ๋๋ฅผ ๋ฐ๋ณตํ๋ฉฐ ์ํํฉ๋๋ค.

<!-- #### ๐ ํ์ ์์ด ๋จ์ด: iterate
  <div class="notice">
     <h4>if a computer iterates, it goes through a set of instructions before going through them for a second time.</h4>
     <p>์ปดํจํฐ๊ฐ iterate ํ๋ค๋ ๊ฒ์ ๋ฐ๋ณตํด์ ์ฌ๋ฌ๊ฐ์ ์ฝ๋๋ฅผ ํต๊ณผํ๋ ๊ฒ์๋๋ค.</p>
  </div> -->

### Code comments

  **//** ๋ฅผ ์ด์ฉํ๋ฉด ์ฃผ์(code comments)๋ฅผ ์์ฑํ  ์ ์์ต๋๋ค. ์ฃผ์์ ์ฝ๋์ ๋ํ ์ ๋ณด๋ฅผ ์ ๊ณตํฉ๋๋ค. ์ฑ์ ์ด ์ฝ๋๋ฅผ ์คํํ์ง ์์ต๋๋ค.

### Item์ ์๋ฃํ

  ํ array์์ ์๋ฃ๋ค์ ๋ชจ๋ ๊ฐ์ ์๋ฃํ์ ๊ฐ์ง๊ณ  ์์ด์ผ ํฉ๋๋ค.
  ๋ง์ฝ ์ฒ์ integer ์๋ฃํ์ ๋ฐฐ์ด์ ๋ง๋ค์๋ค๋ฉด String ์์ดํ์ ์ถ๊ฐํ  ์ ์์ต๋๋ค.

### For-in loop

  ```swift
  let columns = [0, 1, 2, 3, 4]

  for i in columns {
    world.place(Gem(0), atCol: i, row: 1)
  }
  ```
  For-in ๋ฐ๋ณต๋ฌธ์ ๋ฐฐ์ด์ ๊ฐ value๋ง๋ค { } ์์ ์ฝ๋๋ฅผ ๋ฐ๋ณตํด์ ์คํํฉ๋๋ค. ์ ์ฝ๋์์ i๋ columns ๋ฐฐ์ด์ ๊ฐ ๊ฐ์ ๋ด๋ ๋ณ์์๋๋ค. ๋ฐฐ์ด columns์ ๊ฐ์ธ 0, 1, 2, 3, 4๊ฐ i์ ํ ๋น๋๊ณ  ๊ฐ ๊ฐ์ { } ์์ ์์ฑ๋ ์ฝ๋์ธ place ๋ฉ์๋์ atCol ํจ๋ฌ๋ฏธํฐ์ ์ธ์๋ก ํต๊ณผ๋ฉ๋๋ค. for-in ๋ฐ๋ณต๋ฌธ์ด ๋๋๋ง๋ค (Gem(), 0, 1), (Gem(), 1, 1), (Gem(), 2, 1) ... ์์ผ๋ก ์ฝ๋๊ฐ ์คํ๋ฉ๋๋ค. ๋์ด์ ํ ๋น๋  ๊ฐ์ด ์์ผ๋ฉด ๋ฃจํ๋ ๋์ด๋ฉ๋๋ค.

### An array of type Coordinate

  Coordinate์ ์ธ์คํด์ค๋ column๊ณผ row arguments๋ฅผ ์ด์ฉํ์ฌ ์ฅ์๋ฅผ ๋ํ๋๋๋ค.

  ```swift
  // Coordinate ์ธ์คํด์ค์ ์.
  let corner = Coordinate(column: 3, row: 3)

  // blockLocations๋ผ๋ Coordinate type์ ๋ฐฐ์ด ๋ง๋ค๊ธฐ
  var blockLocations = [
      Coordinate(column: 0, row: 0),
      Coordinate(column: 3, row: 3),
      Coordinate(column: 0, row: 3),
      Coordinate(column: 3, row: 0)
  ]
  ```

### Array method

  ```swift
  characters = [
      Character(name: .blu),
      Portal(color: pink),
      Character(name: .hopper),
      Gem()
      ]

  // Remove the portal.
  characters.remove(at: 1)

  // Remove the gem.
  characters.remove(at: 2)

  // Insert the expert.
  characters.insert(Expert(), at: 1)
  ```

  .remove() / .insert() / .append()
  .removeFirst() / .removeLast / .removeAll

  ๋ฑ์ด ์์ต๋๋ค.

### Creating an empty array

  ๊ฐ์ด ์ฃผ์ด์ง์ง ์์ ๋น ๋ฐฐ์ด์ ๋ง๋ค ๋์๋ type์ ์ ํด์ฃผ์ด์ผ ํฉ๋๋ค.

  ```swift
  var newLocations: [Coordinate] = []
  // ๋ฐฐ์ด์ ์ด๋ฆ: [๋ฐฐ์ด์ type] = []
  ```

### Assign a removed item

  ๋๋๋ก ํ ๋ฐฐ์ด์์ ์ญ์ ํ ์์ดํ์ ์ฌ์ฉํ๊ณ  ์ถ์ ๋๊ฐ ์์ ๊ฒ๋๋ค. ๋คํํ๋ ์ญ์ ๋ item์ ์งง์ ์๊ฐ๋์ ์ ์ฅ๋ฉ๋๋ค. ๊ทธ๋ฌ๋ฏ๋ก ์ญ์ ๋ ๊ฐ์ ๋ค๋ฅธ ๋ณ์์ ํ ๋นํ๊ฑฐ๋ ๋ค๋ฅธ ๋ฐฐ์ด์ append ํ  ์ ์์ต๋๋ค.  

  ```swift  
  // Example

  var rightColumn = world.column(7)
  newArray.append(rightColumn.remove(at: 1))
  ```

  ์ ์์ ์ฝ๋์์ newArray์ append๋ ์ขํ๋ rightColumn์์ ์ญ์ ๋ ์ขํ์๋๋ค.
  ์ ์ฝ๋์์ rightColumn์ ๋ฉ์๋๋ก ์ด๊ธฐํ๋์์ต๋๋ค. world ์ธ์คํด์ค๋ ํ ํ, ๋๋ ์ด์ ๋ชจ๋  ์ขํ๋ฅผ ๊ฐ์ง๊ณ  ์๋ ๋ฐฐ์ด์ ๋น ๋ฅด๊ฒ ์์ฑํ  ์ ์๋ ๋ช๊ฐ์ง ๋ฉ์๋๋ฅผ ๊ฐ์ง๊ณ  ์์ต๋๋ค.

  ```swift  
  // Calling a method to create an array

  var row1 = world.row(1)
  var column5 = world.column(5)

  var topRows = world.coordinates(inRows: [5, 6, 7])
  var allCoords = world.allPossibleCoordinates
  ```

### Fixing Index Out of Range Errors  

  Index out of range ์๋ฌ๋ฅผ ์ฐพ๊ณ  ํด๊ฒฐํด ๋ด๋๋ค.  

  Index๋ฅผ ์ฌ์ฉํด์ ๋ฐฐ์ด์ ๊ฐ ์์ดํ์ ์ ๊ทผํ  ์ ์์ต๋๋ค. ๋ฐฐ์ด์ ์์ดํ์ ์ ๊ทผํ๋ค๋ ๊ฒ์ ๊ทธ ์์ดํ์ ๋ณ์์ฒ๋ผ ์ฌ์ฉํ  ์ ์๊ฒ ๋๋ค๋ ๊ฒ์๋๋ค.

  ```swift  
  // Using an index to access an item  

  let characters = [
    Character(name: .byte),
    Character(name: .blu),
    Character(name: .hopper)
  ]

  // Byte toggles a switch
  character[0].toggleSwitch

  // Hopper jumps
  character[2].jump()

  // Index out of range error
  character[3].collectGem()
  ```
  ์์ ๋ง์ง๋ง ์์  ์ฝ๋์ฒ๋ผ ์กด์ฌํ์ง ์์ index๊ฐ์ ์ ๊ทผํ๋ ค๊ณ  ํ๋ฉด index out of range ์ค๋ฅ๊ฐ ๋ฐ์ํฉ๋๋ค. ์ด๊ฒ์ ์ฑ์ ์คํ์ ๋ง๋ bug์ด๊ธฐ ๋๋ฌธ์ ์กฐ์ฌํด์ผ ํฉ๋๋ค.  

  ๋ฒ๊ทธ๋ฅผ ์ฐพ๊ณ  ํด๊ฒฐํ๋ ๊ฒ์ ์ฝ๋๋ก์จ ์ค์ํ ์ผ์๋๋ค. Index out of range ์๋ฌ๋ ์ฑ์ ์คํ์ ์ค๋จ์ํค๋ ๊ฐ์ฅ ํํ ์๋ฌ ์ค ํ๋์๋๋ค.

### Generate a Landscape  

  Int ํ์์ ๋ฐฐ์ด์ ์ด์ฉํ์ฌ landscape์ ์์ฑํด ๋ด๋๋ค.  

  ```swift  
  // ๊ฐ ์ธ๋ฑ์ค์ ํ ๋น๋์ด ์๋ ๊ฐ์ ์ ๊ทผํ๊ธฐ
  var heights = [7, 3, 2, 4]
  for i in 1...heights[0]
  ```
  heights ๋ฐฐ์ด์ 0๋ฒ์งธ ์ธ๋ฑ์ค์ ํ ๋น๋ ๊ฐ์ด 7์ด๋ฏ๋ก ์์ for loop์ 7๋ฒ ๋ฐ๋ณตํฉ๋๋ค.   

  ```swift
  // Example

  var index = 0
  for coordinate in allCoordinates {
    for i in 1...height[index] {
      world.place(Block(), at: coordinate)
    }
    index += 1
  }
  ```

  ์ ์ฝ๋์์๋ index ๋ณ์์ ๊ฒ์ํด์ ๋์ ์ผ๋ก 1์ ๋ํด์ฃผ๊ธฐ ๋๋ฌธ์ index out of range ์๋ฌ๊ฐ ๋ฐ์ํ๋ค. ์ด๊ฒ์ ๋ง๊ธฐ ์ํด์ heights.count๋ฅผ ์ฌ์ฉํ  ์ ์๋ค.  

  ```swift  
  var index = 0
  for coordinate in allCoordinates {
    if index == heights.count {
      index = 0 // Array out of bounds error๋ฅผ ๋ง๋ ์ฝ๋
    }
    for i in 0...heights[index] {
      world.place(Block(), at: coordinate)
    }
    index += 1
  }
  ```

  heights.count๋ ๋ฐฐ์ด์ ์์ดํ ์์๋๋ค. ์์ดํ์ ์๊ฐ 10๊ฐ๋ผ๋ฉด ์ธ๋ฑ์ค๋ 9๊น์ง ์กด์ฌํฉ๋๋ค. (0๋ถํฐ ์์ํ๊ธฐ ๋๋ฌธ์) index == heights.count ๋ผ๋ ๊ฒ์ ์ธ๋ฑ์ค๊ฐ 10์ด ๋์๋ค๋ ๊ฒ์ ์๋ฏธํจ์ผ๋ก index out of range๊ฐ ๋ฉ๋๋ค. ์ด๊ฒ์ ๋ฐฉ์งํ๊ธฐ ์ํด index๊ฐ heights ๋ฐฐ์ด ์์ดํ์ ์์ ๊ฐ์์ก์ ๋ 0์ ํ ๋นํด์ฃผ๋ ๊ฒ์๋๋ค.  

### Randomized Lands  

  ์ ๋ํฌํ ์๋๋ฅผ ๋ง๋ค์ด ๋ณด๊ธฐ ์ํด randomization์ ์ฌ์ฉํด ๋ด๋๋ค.  

  ```swift  
  for i in 1...20 {
    let localNumber = randomInt(from: 0, to: 12)
    heights.append(localNumber)
  }
  ```
  ๋๋ค ๊ฐ์ ์ด์ฉํ๋ฉด ์ฝ๋๊ฐ ์คํ๋ ๋๋ง๋ค ์กฐ๊ธ์ฉ ๋ค๋ฅธ ๊ฒฐ๊ณผ๋ฅผ ๋ง๋ค ์ ์์ต๋๋ค. ๋๋ Boolean ํ์์ ์ฌ์ฉํ ์๋ ์์ต๋๋ค.

#### Local variables  

  function์ด๋ loop์ ๊ฐ์ code structure ์์์ ์ ์๋ ๋ณ์๋ฅผ local variable์ด๋ผ๊ณ  ํฉ๋๋ค. ์์ ์์ ์ฝ๋์์๋ localNumber๊ฐ ์ด์ ํด๋น๋ฉ๋๋ค. local variable์ ์ค๋ก์ง ๋ง๋ค์ด์ง code structure์์์๋ง ์ฌ์ฉํ  ์ ์์ต๋๋ค. ๊ทธ๋ฐ์ ๋ค๋ฅธ ๊ณณ์์๋ ์ฌ์ฉํ  ์ ์์ต๋๋ค.

### Read and Tweak  

  ์ด๋ฏธ ์์ฑ๋ ์ฝ๋๋ฅผ ์ฝ๊ณ , ์์ ํ๋ ๊ฒ์ ์ฝ๋์๊ฒ ์ค์ํ ๋ฅ๋ ฅ์๋๋ค. ๋ค๋ฅธ ์ฌ๋์ด ์์ฑํ ์ฝ๋๋ฅผ ์ฝ๊ณ  ์ดํดํด์ผํ๋ ์ผ์ด ๋ง์ ๊ฒ์๋๋ค. code comment๋ฅผ ์ด์ฉํ์ฌ ๋ค๋ฅธ ์ฌ๋๋ค์ด ๋์ ์ฝ๋๋ฅผ ์ข ๋ ์ฝ๊ฒ ์ดํดํ  ์ ์๋๋ก ํ๋ ๊ฒ๋ ์ข์ ๋ฐฉ๋ฒ์๋๋ค.
