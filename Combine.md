- 콤바인을 사용하여 이벤트 소스를 처리할 체인을 생성할 수 있다.
- 체인의 각 파트는 Combine operator인데, 전 스텝에서 생성된 (받은) 요소들에 각기 다른 처리를 실행한다.
- 텍스트 필드에 입력된 값을 통해 필터링을 한다고 가정해보자.
  - 텍스트 필드에 글자가 입력될 때마다 Notificatiion이 생성됨. Combine을 사용하여 이 notification을 subscribe할 수 있음.
  - 받은 notificatiion에 operators들을 사용하여 내용, 이벤트가 전달되는 타이밍등을 변경시키고 최종 결과를 이용해서 앱의 UI를 업데이트 할 수 있다.
  ```swift
  let pub = NotificationCenter.default 
    .publisher(for: NSControl.textDidChangeNotification, object: filterField)
  ```
  - default notification center 인스턴스에 접근하여 해당 인스턴스의 publisher 메서드를 호출
