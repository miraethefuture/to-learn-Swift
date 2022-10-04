---
title: "심화 Swift"
categories:
  - TIL
tags:
  - learning
  - 공부 기록
  - Swift
show_date: true
toc: true
toc_sticky: true
toc_label: " "
toc_icon: "kiwi-bird"
#header:
#  teaser: /assets/images/choose2.png
---

<sub>📂 Swift language guide 외의 정보들을 기록합니다.</sub>
<br>
<br>
<br>



# Concurrency
## Parallel Code  

  스위프트는 구조화된 방식으로 비동기 및 병렬 코드를 작성할 수 있도록 지원합니다. (코드를 작성할 수 있는 방식 또는 키워드를 가지고 있는 거겠죠?)  

  비동기 코드(Asynchronous code)는 중단되었다가 다시 시작될 수 있습니다.

 병렬 코드(Parallel code)는 여러개의 코드가 동시에 동작하는 것을 의미합니다. 예를 들어 4 코어 프로세서를 가진 컴퓨터는 네개의 코드를 동시에 실행할 수 있습니다. 각각의 코어는 하나의 일을 수행합니다. 병렬(parallel) 그리고 비동기(asynchronous)코드는 한번에 여러개의 작업을 수행합니다.  
  이것은 외부 시스템을 기다려야 하는 작업을 중지시킵니다. 그리고 memory-safe한 방식으로 코드를 작성하기 쉽도록 만들어 줍니다.  

  아래 설명에서 concurrency라는 단어는 일반적으로 비동기적(asynchronous) 코드와 병렬(parallel)코드를 나타내기 위해 사용됩니다.  

  Swift 언어의 지원 없이도 concurrent한 코드를 작성할 수 있지만, 그렇게 작성된 코드들은 알아보기 어려운 경우가 많습니다.  
  예를 들면, 아래의 코드는 사진의 이름 목록을 다운로드 하고, 목록의 첫번째 사진을 다운로드 합니다. 그리고 그 사진을 사용자에게 보여줍니다.

  ```swift
  listPhotos(inGallery: "Summer Vacation") { PhotoNames in
      let sortedNames = photoNames.sorted()
      let name = sortedNames[0]
      downloadPhoto(name: name) { photo in
          show(photo)
      }  
  }
  ```  

  이렇게 간단한 경우에도, 여러개의 completion handler로 코드가 작성되어야 했기 때문에 결국 nested 클로저를 작성하게 됩니다.  
  이런 방식으로는, nesting이 더 깊어짐과 함께 코드가 복잡해지고 다루기 어려워집니다.

## Defining and Calling Asynchronous Functions  

  비동기 함수(asynchronous function) 또는 비동기 메서드(asynchronous method)는 실행되는 중간에 중단될 수 있는 특별한 종류의 함수 또는 메서드입니다. 실행을 끝까지 완료하고 에러를 던지거나 리턴하지 않는 기존의 방식인 동기 함수, 동기 메서드(synchronous function, synchronous method)와는 대조적입니다. 비동기 함수나 메서드도 위의 세가지 과정 중 하나를 수행하지만 중간에 잠시 어떤 것을 기다리며 멈출 수  있습니다. 비동기 함수 또는 메서드의 바디 안 어디에서 실행을 중단 시킬지 표시할 수 있습니다.  

  Function이나 메서드가 비동기적이라는 것을 나타내기 위해서, 선언 부분의 패러미터 뒤쪽에 async 키워드를 작성해줍니다. throws키워드를 이용해서 throwing function을 작성하는 것과 비슷합니다. 리턴값이 있을 때는 리턴 화살표 전에 async 키워드를 작성합니다.

  ```swift
  func listPhotos(inGallery name: String) async -> [String] {
    let result = // ...비동기적 네트워킹 코드...
    return result
  }
  ```

  비동기적 함수이면서 에러를 던지는 함수를 작성할 때는 async throws 순으로 키워드를 작성합니다.  

  비동기적 메서드를 호출할 때, 해당 메서드가 리턴할 때까지 실행이 중단됩니다. 실행이 중단될 가능성이 있는 호출 앞에 await 키워드를 사용하여 표시해줍니다. 이것은 에러를 던지는 함수를 호출할 때 try 키워드를 작성하는 것과 비슷합니다. try 키워드는 프로그램에 에러가 있다면 실행 흐름이 변경될 수 있다는 것을 알려줍니다.

  <br>

# Codable   

  Codable은 Encodable 프로토콜과 Decodable프로토콜을 합친 type alias입니다.  
  이 프로토콜을 사용하면 JSON 파일로부터 데이터를 가져와 순서대로 출력하거나, 반대로 JSON 파일로 데이터를
  순서대로 출력시킬 수 있는 Codable API를 사용할 수 있습니다.

  <br>

# Completion Handler

    컴플리션 핸들러는 어떤 기능이 작동 완료된 후에 호출되는 콜백 함수이다.
    콜백 함수는 어떤 함수의 인자(argument)로 통과된 함수를 말한다.

  <br>

# filter(_:)  

  ```swift
  let cast = ["Vivien", "Marlon", "Kim", "Karl"]
  let shortNames = cast.filter { $0.count < 5 }
  print(shortNames)
  // Prints ["Kim", "Karl"]
  ```  

  cast라는 배열이 있습니다. filter 메서드를 사용하여 기존 배열에서 글자수가 다섯자 이하인 단어만으로 새로운 배열을 생성합니다. 새롭게 생성된 배열은 shortNames 상수에 할당해줍니다. $0이 cast의 요소라는 것을 알 수 있습니다.

  ```swift
  var filteredLandmarks: [Landmark] {
  //        landmarks.filter { landmark in
  //            (!showFavoritesOnly || landmark.isFavorite)
  //        }
      landmarks.filter { $0.isFavorite == true }
  }
  ```  

  주석처리 한 부분이 원래 튜토리얼의 filter 메서드 코드이고, 주석처리 되지 않은 코드는 위의 예시를 보고 같은 방식으로 만들어 보았습니다. 똑같이 작동하는 것을 알 수 있었습니다. (!showFavoritesOnly 부분은 아직 코드의 영향을 미치지 않음.)
