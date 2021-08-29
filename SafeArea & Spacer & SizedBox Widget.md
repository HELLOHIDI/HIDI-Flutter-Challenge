# SafeArea & Spacer & SizedBox Widget

## <a href = 'https://api.flutter.dev/flutter/widgets/SafeArea-class.html'>SafeArea</a>
  - 운영 체제의 침입을 피하기에 충분한 패딩으로 하위 항목을 삽입하는 위젯
  - 예를 들어, 화면 맨 위에 있는 상태 표시줄을 피할 수 있을 만큼 하위 항목이 들여쓰기됩니다.
  - 최소 패딩이 지정되면 최소 패딩 중 더 큰 패딩 또는 안전 영역 패딩이 적용
  - SafeArea의 위젯이 MediaQuery를 통해 앱의 실제 화면 크기를 계산하고 이를 영역으로 삼아 내용을 표시하기 때문에 잘리거나 가려지는 부분 없이 전부 나올수 있게 되는 것
  
  다음과 같은 상황이 있습니다. 
  
  
  ![image](https://user-images.githubusercontent.com/54922625/131250384-0862895e-246c-4366-ad58-7982293f6706.png)
  
  
  맨 아래에 있는 Text의 경우 잘리게 되죠.
  
  이 부분을 SafeArea로 감싸주게 되면
  
  
  ![image](https://user-images.githubusercontent.com/54922625/131250395-84a1df1a-f7c2-467a-856f-4a18662970b8.png)


  <pre>
  <code>
  const SafeArea({
    Key? key,
    this.left = true,
    this.top = true,
    this.right = true,
    this.bottom = true,
    this.minimum = EdgeInsets.zero,
    this.maintainBottomViewPadding = false,
    required this.child,
}) : assert(left != null),
     assert(top != null),
     assert(right != null),
     assert(bottom != null),
     super(key: key);
 </code>
 </pre>

-----------------------------------------------------------------------------------------------------------

## <a href='https://api.flutter.dev/flutter/widgets/Spacer-class.html'>Spacer</a>
  - 행 또는 열과 같은 Flex 컨테이너의 위젯 간 간격을 조정하는 데 사용할 수 있는 조정 가능한 빈 스페이서를 만드는 위젯
  - Row와 Column 위젯에서 가장 일반적으로 많이 사용한다.
  
  
<pre>
<code>
const Spacer({Key? key, this.flex = 1})
  : assert(flex != null),
    assert(flex > 0),
    super(key: key);
</code>
</pre>

### Spacer 주요 속성
- **flex** : 공간을 얼마나 차지할지 결정하는데 사용하는 속성

### 예시 코드
<pre>
<code>
Row(
    children: const <Widget>[
      Text('Begin'),
      Spacer(), // Defaults to a flex of one.
      Text('Middle'),
      // Gives twice the space between Middle and End than Begin and Middle.
      Spacer(flex: 2),
      Text('End'),
    ],
  );
</code>
</pre>


### 실행 결과
![image](https://user-images.githubusercontent.com/54922625/131250865-37522f31-f1c0-4745-b59b-e49c1d3a2a1c.png)

begin과 middle 사이에 두배만큼 middle과 end 사이가 벌어져있다. => flex가 2이기 때문인다!

-------------------------------------------------------------------------------------------------------------
## <a href='https://api.flutter.dev/flutter/widgets/SizedBox-class.html'>SizedBox</a>
  - 지정된 크기의 상자 위젯
  - 정확한 사이즈로 하위 요소까지 같은 사이조로 만들어줌
  - 위젯 간 여유공간을 확보할 때도 사용 가능
  - sizedBox.expand -> width, height => double.infinity
<pre>
<code>
const SizedBox({ Key? key, this.width, this.height, Widget? child })
  : super(key: key, child: child);
</code>
</pre>

### SizedBox 주요 속성
- **width, height** : 박스의 가로, 세로 크기
- **child** : 단일 위젯 가능
