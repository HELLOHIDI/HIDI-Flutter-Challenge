# StatelessWidget vs StatefulWidget

## StatelessWidget
  - 화면 표시용 위젯
  - 위젯이 로딩되어 화면에 표시된 이후에는 사용자 이벤트나 동작이 있어도 내용을 변경 x
  - final 변수를 선호 -> 상태가 없기 때문

## StatefulWidget
  - 변경 가능한 상태를 가진 위젯
  - 처음 화면에 그려질 때 변수의 값에 따라 위젯을 그릴 수 있고
  - 그려진 후 사용자에 액션에 따라 위젯을 다시 그릴 수도 있는 위젯
  - 변경할 수 있는 일반적인 변수를 가짐

## stateful Widget 생명주기
  - **createedState()**
    - 상태가 생성, 플러터가 StatefulWidget을 빌드하도록 지시하면 즉시 호출된다.
  - **initState()**
    - 위젯이 생성될 때 처음으로 호출되는 메서드
    - 생성된 위젯 인스턴스의 BuildContext에 의존적인 것들의 데이터 초기화(걍 초기화를 위한 함수)
    - 최초에 단 한 번만 실행되는 함수
  - **build()**
    - 위젯을 화면에 표시하는 메서드
    - 화면에 표시할 위젯을 반환
  - **setState()**
    - 위젯의 상태를 갱신
    - 이 메서드를 실행하면 위젯을 처음부터 다시 만들지만 initState() 메서드는 호출 x
    - 데이터가 변경되었음을 프레임워크에 알리는데 사용되며 build context의 위젯을 다시 빌드하게 함
    - 그렇기에 변경해야 되는 위젯의 BuildContext를 분리하는 것이 좋음
