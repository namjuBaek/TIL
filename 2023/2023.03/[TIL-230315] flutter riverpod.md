### flutter riverpod

---

- riverpod란 플러터용 프로바이더 패턴의 상태관리 라이브러리이다.

**riverpod with mvvm**

- 앱의 상태를 나타내고 비즈니스 로직을 포함하는 viewmodel 클래스를 정의해야 한다.
- view는 provider를 통해 viewmodel에 바인딩되고 해당 데이터를 표시한다.



**provider에서 ref 얻기**

- 모든 provider는 ref 객체를 파라미터로 받음
- 이 ref는 또 다른 provider를 참조하는데 사용할 수 있음

```
final provider = Provider((ref) {
	final test = ref.watch(testProvider);
});
```



**StatelessWidget 대신 ConsumerWidget**

- statefulWidget을 상속받아서 만들어진 커스텀 위젯
- build 메소드에서 widgetRef를 파라미터로 받아서 사용할 수 있음
- **widgetRef는 provider를 참조할 수 있도록 도와주는 객체**



**StatefullWidget + State 대신 ConsumerWidget +ConsumerState 상속**

- ConsumerWidget과 동일한 방법으로 ref객체를 사용 가능
- 대신 파라미터로 전달되는 것이 아니라, ConsumerState 객체 속성이다.



**ref로 provider와 상호작용**

1. ref.watch
   - provider의 값을 가져와 변화를 감지하고, 변경되면 위젯을 리빌드하거나 구독 위치에 값을 전달한다.

2. ref.listen
   - provider 값의 변화를 감지하지만 위젯을 리빌드하거나 상태값을 다른 곳에 전달하지 않는다.
   - 상태 변경이 있을 때, 특정 행위를 해야할 때 사용 (e.g. SnackBar 보여주기)

3. ref.read
   - provider의 값을 가지고 올 때 사용



<br>

#### flutter dependencies/dev_dependencies

---

**devpendencies** : 개발 완료 후 앱을 배포할 때 포함되는 플러그인 목록 (컴파일 시 필요)

**dev_dependencies** : 개발 단계에서 앱을 테스트하기 위해 필요한 플러그인 목록 (개발 시 필요)

<br>

#### flutter Linter

---

코드의 스타일 통일을 도와주고, 잠재적인 버그를 찾을 수 있도록 도와주는 라이브러리

- analysis_options.yaml 파일에 linter rule을 설정하여 코드 스타일 통일 및 버그 방지
- severity로 심각도 설정 가능 (ignore, info, warning, error)

**dart linter rule**

- https://dart-lang.github.io/linter/lints/





**참고 글**

---

https://velog.io/@udong85/Flutter-Riverpod-%EB%A1%9C-%EC%83%81%ED%83%9C-%EA%B4%80%EB%A6%AC-%ED%95%98%EA%B8%B0-1

https://dart-lang.github.io/linter/lints/