# Combine - Overview
- 콤바인을 사용하여 이벤트 소스를 처리할 체인을 생성할 수 있다.
- 체인의 각 파트는 Combine operator인데, 전 스텝에서 생성된 (받은) 요소들에 각기 다른 처리를 실행한다.
- 텍스트 필드에 입력된 값을 통해 필터링을 한다고 가정해보자.
  - 텍스트 필드에 글자가 입력될 때마다 Notificatiion이 생성됨. Combine을 사용하여 이 notification을 subscribe할 수 있음.
  - 받은 notificatiion에 operators들을 사용하여 내용, 이벤트가 전달되는 타이밍등을 변경시키고 최종 결과를 이용해서 앱의 UI를 업데이트 할 수 있다.
 
# Connect a Publisher to a Subscriber
  ```swift
  let pub = NotificationCenter.default 
    .publisher(for: NSControl.textDidChangeNotification, object: filterField)
  ```
  - default notification center 인스턴스에 접근하여 해당 인스턴스의 publisher 메서드를 호출
  - for: notification name / object: notification을 발생시키는 객체를 입력
  - .publisher(for:object:)가 notification elements를 리턴

# Change the Output Type with Operators
  ```swift
  let sub = NotificationCenter.default
    .publisher(for: NSControl.textDidChangeNotification, object: filterField)
    .map( { ($0.object as! NSTextField).stringValue } )
    .sink(receiveCompletion: { print ($0) },
          receiveValue: { print ($0) })
  ```
- 만약 텍스트 필드의 string 값만 필요하다면, NotificationCenter.Publisher.Output 타입을 변환할 수 있다.
- publisher의 아웃풋은 시간에 따라 발생하는 요소의 연속적인 값인데, Combine이 제공하는 operators를 사용하여 이 값들을 수정할 수 있다.
- 위 코드에서는 publisher의 output 타입을 변경하기 위해 map(_:) operator를 사용하여 클로저를 통해 다른 타입을 리턴했다.
- notification 객체를 NSTextField로 얻은 뒤, field의 stringValue를 얻었다.
  ```switft
  let sub = NotificationCenter.default
        .publisher(for: NSControl.textDidChangeNotification, object: filterField)
        .map( { ($0.object as! NSTextField).stringValue } )
        .assign(to: \MyViewModel.filterString, on: myViewModel)
  ```
- 
