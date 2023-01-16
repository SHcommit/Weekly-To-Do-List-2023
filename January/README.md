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

### 공부한 것

### 아쉬운 점 

## 4주(23~29)

### 공부한 것

### 아쉬운 점 
