# Combine - Overview
- 콤바인을 사용하여 이벤트 소스를 처리할 체인을 생성할 수 있다.
- 체인의 각 파트는 Combine operator인데, 전 스텝에서 생성된 (받은) 요소들에 각기 다른 처리를 실행한다.
- 텍스트 필드에 입력된 값을 통해 필터링을 한다고 가정해보자.
  - 텍스트 필드에 글자가 입력될 때마다 Notificatiion이 생성됨. Combine을 사용하여 이 notification을 subscribe할 수 있음.
  - 받은 notificatiion에 operators들을 사용하여 내용, 이벤트가 전달되는 타이밍등을 변경시키고 최종 결과를 이용해서 앱의 UI를 업데이트 할 수 있다.
 
## Connect a Publisher to a Subscriber
  ```swift
  let pub = NotificationCenter.default 
    .publisher(for: NSControl.textDidChangeNotification, object: filterField)
  ```
  - default notification center 인스턴스에 접근하여 해당 인스턴스의 publisher 메서드를 호출
  - for: notification name / object: notification을 발생시키는 객체를 입력
  - .publisher(for:object:)가 notification elements를 리턴

## Change the Output Type with Operators
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
- publisher chain이 원하는 타입을 생성한 뒤, assign(to:on:)을 사용하여 커스텀 뷰 모델에 filterString에 해당 값을 할당함.

## Customize Publishers with Operators
  ```swift
  let sub = NotificationCenter.default
    .publisher(for: NSControl.textDidChangeNotification, object: filterField)
    .map( { ($0.object as! NSTextField).stringValue } )
    .filter( { $0.unicodeScalars.allSatisfy({CharacterSet.alphanumerics.contains($0)}) } )
    .debounce(for: .milliseconds(500), scheduler: RunLoop.main)
    .receive(on: RunLoop.main)
    .assign(to:\MyViewModel.filterString, on: myViewModel)
  ```
- filter(_:)를 사용항여 string value중 알파벳과 숫자로만 이루어진 텍스트를 필터링
- 만약 필터링 작업이, 큰 데이터 베이스에서 쿼리 작업을 하는 경우 등 시간이 오래 걸리는 작업이라면 유저가 타이핑을 할때마다 필터링을 하지 않고, 타이핑을 멈출 때를 기다렸다가 작성된 스트링으로 필터링을 할 수 있음.
- debounce(for:scheduler:options:) operator를 사용하여 특정 미니멈 시간이 지나야 publisher가 이벤트를 일으킬 수 있도록 할 수 있음.


# Replacing Foundation Timers with Timer Publishers
- 만약 Foundation의 Timer 클래스를 사용하여 반복적으로 콜백을 받거나, 특정 시간 간격으로 클로저를 실헹하고 있다면, 이러한 인스턴스를 Combine으로 변환하여 코드를 단순화할 수 있다.

## Performing Periodic Work with a Timer
- 아래 코드 스니펫은 특정 디스페치 큐에서, scheduledTimer(withTimeInterval:repeats:block:)을 사용하여 데이터 모델ㅇ의 lastUpdated 속성을 업데이트 한다.
  ```swift
  var timer: Timer?
  override func viewDidLoad() {
      super.viewDidLoad()
      timer = Timer.scheduledTimer(withTimeInterval: 1, repeats: true) { _
          self.myDispatchQueue.async() {
              self.myDataModel.lastUpdated = Date()
          }
      }
  }
  ```

## Converting to a Timer Publisher
- Combine을 사용하는 방식으로 변환해보자. scheduledTimer(withTimeInterval:repeats:block:)로 부터 리턴된 Timer를 Timer.TimerPublisher로 교체한다. (Timer method publish 를 사용)
- Combine operators로 위 예제 코드의 클로저 속에서 처리한 작업을 모두 처리했다.
  - receive(on:options:) operator(연산자)는 뒤에 붙는 연산자들이 특정 디스패치 큐에서 실행되도록 함. 이것은 위 예제 코드의 async()를 대신함. 
  ```swift
  var cancellable: Cancellable?
  override func viewDidLoad() {
      super.viewDidLoad()
      cacellable = Timer.publish(every: 1, on: .main, in: .default)
          .autoconnect()
          .receive(on: myDispatchQueue)
          .assign(to: \.lastUpdated, on: myDataModel)
  }
  ```
  
