#### BLoC Pattern

---

- Business Logic Componenet
- presentation Layer와 businessLogic을 분리하여 코드를 작성 할 수 있도록 해줌

![img](https://i0.wp.com/everyday.codes/wp-content/uploads/2020/06/bloc-splash.png?w=925&ssl=1)



- bloc에서 각 ui 객체들은 bloc 객체를 구독하는데, bloc 객체의 상태가 변경되면 구독중인 ui객체들은 그 즉시 해당 상태로 ui를 변경한다.
- bloc객체는 ui객체로부터 이벤트를 전달받으면, bloc객체는 필요한 provider나 repository로부터 데이터를 전달받아 비즈니스 로직을 처리한다.

> UI에서는 여러 BLoC가 존재할 수 있다.
>
> UI에서는 화면에 집중하고, BLoC에서는 로직에 집중한다.
>
> BLoC는 여러 UI에서 구독할 수 있어 재사용성이 좋다.
>
> BLoC만을 분리해서 테스트 가능하다.



**mvvm과의 차이점?**

mvvm은 데이터바인딩을 오직 view-viewmodel끼리 하지만 bloc는 어떤 이벤트에서 발생해도 괜찮음.



참고 글

https://velog.io/@songoori/Flutter-BLoC-%ED%8C%A8%ED%84%B4

https://velog.io/@seunghwanly/Flutter-BLoC-Pattern



#### Provider

---

- 공통 부모 위젯에 Provider를 주입하고 상태를 사용하는 곳에서 provider의 데이터를 읽어서 사용한다.
- provider에 직접 접근해서 받아오면 위젯 전체가 업데이트되기 때문에 consumer 사용 권장



#### Flutter 폴더 구조

---

**mvvm 아키텍처**

- presentation : 위젯, 뷰, 컨트롤러
- domain : 모델
- data : 레포지토리, 데이터 소스 & DTO

위의 세 레이어로 나누어 아키텍처를 구성



기능 우선 방법과 레이어 우선 방법이 존재

- Feature-first
- Layer_first

레이어 우선 방법은 각 레이어 폴더 안에 기능이 들어가는 방식으로, 앱이 커질수록 확장하기 어렵다.
한 기능이 서로 다른 레이어 폴더에 퍼져있기 때문에 점점 찾기 어려워진다.

기능 우선 방법은 모든 앱 기능에 대해 폴더를 먼저 만들고 그 아래에 레이어 폴더가 존재한다.
하지만 기능 폴더를 잘 구성하지 않으면 공통되는 model, repo 파일들을 다시 위로 빼야하는 경우가 발생할 수도 있어서 기능 폴더를 잘 구분하는게 중요하다.



참고 글

- https://devmuaz.medium.com/flutter-clean-architecture-series-part-1-d2d4c2e75c47

- https://codewithandrea.com/articles/flutter-project-structure/#layer-first-features-inside-layers



