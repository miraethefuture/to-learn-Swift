# Encoding and Decodable Custom Types

  // Custom types?
  ```swift
  struct Coordinate: Codable {
      var latitude: Double
      var longitude: Double
  }

  var location: Coordinate // Custom type!!!
```

##property list  

  내가 만든 어떤 클래스나, 스트럭처나 등등 데이터를 이용해야하는 객체(?)들에
  Codable 자료형을 준다. = Encodable , Decodable protocol 얘네 두개를 합친게
  Codable. 데이터를 가지고 작업을 하는 와중에 암호화하거나 해독하거나 하는 과정들이 생김.
  그 작업을 도와주는게 Codable인거지. Type Alias...자료형에 가명을 주는건가?

  이미 Codable한 property를 사용하는게 가장 쉬운 방법이다.
  아래는 그 예시

  Standard library types
  - String
  - Int
  - Double

  Foundation types
  - Date
  - Data
  - URL

  Built-in types
  - Array
  - Dictionary
  - Optional

  위와 같은 자료형은 이미 Codable한 자료형이다.

  ```swift
  struct Landmark {
    var name: String
    var foundingYear: Int
  }
  ```

  // inheritance list에 Codable을 추가해주면 자동으로

  ```swift
  struct Landmark: Codable {
    var name: String
    var foundingYear: Int
  }
  ```
  Codable 메서드의 생성자 init(from:) 와 encode(to:) support하게 됨.
  상속...?

  // 배열 또 한번 봐야겠구먼

  // nested?

  //enemeration


  Coding key를 이용해서 Encode나 Decode할 property를 선택하래.
  types를 Codable하게 만든다...
