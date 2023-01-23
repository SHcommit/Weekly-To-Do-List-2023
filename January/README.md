## 1주(2~8)

<img src="https://user-images.githubusercontent.com/96910404/211215304-57390069-e1f3-4ea0-ae3a-289aaad6c80e.jpeg"  width="400" /> 

### 공부한 것

- Combine Asynchronous Programming with Swift 공부 완료
- 다익스트라, 힙 알고리즘 공부
- 영어 쬐끔 아주쬐끔

### 아쉬운 점 

- 컴바인 책을 너무 정독해서 영어 공부에 비중을 못뒀다 ㅋㅋ;;
- 이번 주 내로 컴바인 알고 있는 내용을 정리하려 했는데 다음주까지 틈틈이 해야할 것 같다.

## 2주(9~15)

<img src="https://user-images.githubusercontent.com/96910404/212602677-1a2b8cb6-b0fa-474c-88d6-366d90657a7a.jpeg"  width="400" /> 

### 공부한 것

- 인스타그램 Notificaiton 개발. 아직 push notification은 구현x

- 다익스트라, 플로이드 와샬, 문자열 (조금 )

- Combine에서 subject를 Set<AnyCancellable>에 저장 만 하면 알아서 deinit될 때 연관된 subscription은 다 해제되는 것으로 알고 있었다. 근데 VC가 dismiss가 되는게 아니라 쌓이기 때문에 subsciription은 cancel되지 않고 쌓인다. VC 관련 subscription은 문제가 되지 않았다. tableView, collectionView등의 reusable cell에선 바인딩이 중첩해서 되는 오류를 알아버렸고 cancel을 충분히 해주어야 한다는 것을 알게 되었다. publihser의 publish에서 다른 화면으로 갔다가 되돌아오고 등 여러 상황?을 반복해서 subsciription이 cancel되지 않고 중첩 바인딩 되는 오류를 찾아야 할것 같다...

### 아쉬운 점 

- 인스타그램 notification 개발하면서 예상치 못한 오류를 연달아 발견해서 ( notificationController 의 cell follow에선 팔로우가 되는데 SearchController에서 팔로우를 할 경우 notificationController로 돌아갔을 땐 갱신이 되지 않는 이유, cell 관련 subscription 중첩 바인딩 등) 수정하는데 많은 시간이 들어버렸다...

- 영어 공부를 해야하는데,, 킄킄

## 3주(16~22)

<img src="https://user-images.githubusercontent.com/96910404/213966667-97204170-13bb-4ba6-bd6f-069989759337.jpeg"  width="400" /> 

### 공부한 것

- Coordinator pattern.

- 문자열 알고리즘
 
- 인스타 그램 개발할 때 반복되는 변수를 너무 많이 써서 편리하게 $0으로 사용할 수있게 커스텀 함수를 몇개 만들었습니다. ㅎㅎ
 
- - snapkit은 아니지만.. 예전보단 편한 <a href="https://github.com/SHcommit/LearnMoreSwiftInUdemy/blob/master/Clone%20App/Instagram/Instagram/Features/Shared/Protocols/UIView%2BViewLayoutProtocols.swift">레이아웃 설정 관련</a>
- - coordinator <a href="https://github.com/SHcommit/LearnMoreSwiftInUdemy/blob/master/Clone%20App/Instagram/Instagram/Features/FlowCoordinators/FlowCoordinator%2BUtils.swift">객체 편의 초기화</a> 함수

- 인스타그램 개발을 하면서 다음화면으로 넘어가고를 반복하면 화면이 계속 쌓이는데 이를 어떻게 관리할 것인지 정말 궁금했습니다. MVVM에 Clean architecture 패턴을 적용한 개념도 알게 되었습니다. Layer간 의존성 주입과 역전을 중심으로 각 layer간 의존성이 없는 설계를 구현한다는 개념을 알게 되었습니다. MVVM Clean architecture는 CleanCode 책을 만든 Robert C.Martin이 제안한 system architecture pattern인데(대단,,) 다시 한번 읽으면서 정리해야겠다고 느겼습니다. 하지만 Clean architecture의 도입은 화면 전환에 대한 제 궁금증을 해결하진 못했습니다....

- 인스타그램을 만들 때 물론 기존 MVVM 패턴에서 tabController과 Navigation을 이용했습니다. 앞서 말한 두 object들은 ContainerViewController이기 때문에 각각은 Stack구조로 sub viewController들을 저장하고, push, pop을 통해 LIFO구조로 subController들을 계층적으로 관리한다는 개념을 알고 있었습니다. 그럼에도 뭔가 찝찝했기에 인터넷을 통해 화면 관리 관련 패턴을 찾았습니다.( 결국 화면 관리는 container controller에서 하게 된다는 것을 알게 되었습니다.)

- 지금까지 찾아본 패턴은 Router를 이용한 Vipor patttern, Coordinator pattern이 있다는 점을 알게 되었습니다. <a href="https://khanlou.com/2015/10/coordinators-redux/">KHANLOU</a>의 Coordinator Redux.. MVC, MVVM, MVP 등 다양하게 적용이 가능한 이유는 Coordinator는 vipor를 제외한? 이전 Architecture pattern에서는 다루지 않았던 화면 전환의 역할을 새롭게 담당하는 Pattern이기 때문입니다. Khanlou가 소개한 초기 Coordinator는 앱 델리게이트는 Entry point인 app delegate에서 opening system에서 app의 subsystem으로 메시지를 실어 나르는 책임이 있는데 변경하기 정말 쉽고 이를 이용해 Container의 rootViewController를 app delegate에 넣지만 이마저도  app delegate에 책임을 떠넘기는 것이기 때문에 massive해지게 됩니다. 

- massive한 상태를 없애기 위해 소개된 것이 ViewController를 관리하는 Coordinator 패턴입니다. 이는 ApplicationCoordinator를 app delegate에 생성함으로써 App delegate에 massive한 code를 넣지 않도록 해결할 수 있습니다. App delegate는 간단하게 ApplicationCoordinator를 start하기만 하면 됩니다. 그리고 ApplicationCoordinator로부터 주요한 viewController의 관리를 setup하면 됩니다.

- 새로 호출되기 위한 A type의 ViewController는 A type를 호출하기 이전 뷰에 의해서 생성되고 호출되야 하는가? ViewModel에서 해야하는가?.. Coordinator에서 하면 됩니다. Coordinator는 viewController를 생성하고 의존성 주입을 합니다. 그리고 새로운 child coordinator들을 관리합니다. 화면의 생성과 호출은 Coordinator가 담당함으로 ViewController는 데이터를 표시, 화면 UI update, VM과 binding, congif Layout..를 할 뿐 화면 관리를 하지 않습니다.

- flow... . Coordinator를 사용하지 않는 ViewController는 다음에 호출 될 flow를 다뤄야 할 책임이 없음에도 불구하고 logic이 들어가야 합니다. 그리고 상위 container Controlller에게 호출까지 해야합니다. ViewController(View)로부터 flow logic이 분리된다면 ViewController는 더이상 다음에 호출 될 flow를 다뤄야 할 책임에서 벗어납니다. flow logic를 담당하는 것이 Coordinator pattern입니다.

- 그렇기에 childCoordinator, parentCoordinator간 관계, Coordinator의 childCoordinator를 홀딩함으로 navigation stack에 저장된 각각의 viewController 하위 계층에 대한 정보를 갖고 있는(각각의 chhildViewController)를 생성한 Coordinator는 childCoordinator를 배열로 저장함으로 ViewController를 관리하는 것입니다. 

- 즉 ViewController를 모아서 관리합니다. 새로운 layer. Coordinator객체를 통해 flow logic을 담당합니다.

- 이 패턴을 지금 개발중인 인스타그램 앱에 도입했습니다. 한가지 주의할 점은 Coordinator를 단순히 childCoordinator에 저장시킨다면 반드시 memory leak에 주의해야합니다. 결국 chlid coordinator를 생성하고 화면 전환을 하는 것은 coordinator에 있는 presenter.. containerController인 navigationController or tabController인 것인데 이를 통해 push하기 전에 childCoordinators등 하위 subCoordinator를 holding하기 위해 배열에 저장하게 된다면 만약 해당 childCoordinator의 ViewController가 pop, dismiss될 때, 이를 구성하는 childCoordinator의 할당을 parentCoordinator로부터 해제하지 않으면 화면 dismiss는 되서 ViewController는 사라졌지만 childCoordinator는 계속 parentCoordinator에 저장되어 유지되기 때문에 memory leak가 발생할 수 있습니다.

<a href="https://github.com/SHcommit/LearnMoreSwiftInUdemy/blob/master/Clone%20App/Instagram/Instagram/Features/FlowCoordinators/FlowCoordinator%2BUtils.swift">FlowCoordinator+Utils</a>파일의 testNavigationController(_:didShow:animated:castingLogic:)를 통해 확인을 해 본 결과 Coordinator가 사라지지 않는 다는 것을 알게 됬고 많은 시간을 들여 해결했습니다.. 

- 원래 parentCoordinator를 사용하지 않으려 했는데 인스타그램의 경우 메인 로직을 담당하는 Container type이 tabBarController이기 때문에 이와 같은 방법을 선택했습니다.( presenter의 controller property가 MainHomeTabControlelr인지의 여부를 통해 childCoordinator start로직을 변경,,)

### 아쉬운 점 

- Coordinator 패턴. 이름만 들어봤지 저번주부터 공부를 하게 됬는데 적용할 때, 패턴 구현 부분에서 tree 알고리즘 구조 등을 이용해야 해서 약간의 시간이 걸렸습니다. 또한 처음으로 Coordinator 패턴을 적용했기에... MVC - C등 Coordinator 객체로만 분리하면 될 줄 알았는데 이전에  제가 개발했던 인스타그램에선 deleagate를 통해서도 다른 ViewController를 호출하고, VM의 state변화에 따라 ViewController를 호출하고, ViewModel을 생성하기 위해선 메인에 있는 로그인한 유저 정보 프로필 이미지 등.. 너무 많이 서로 의존성으로 묶여 있어서 분리하는데 시간이 많이 들었습니다.

- 패턴 적용과 리펙토링에 시간을 정말 많이 써서 다른 공부를 하지 못했습니다. 인스타그램 flow패턴 분리 리펙터링이 거의 완료되었기에 영어 공부를 조금씩 진짜 하려고 합니다.,,

## 4주(23~29)

### 공부한 것

### 아쉬운 점 
 
