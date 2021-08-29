# Padding & Expanded Widget

## <a href='https://api.flutter.dev/flutter/widgets/Padding-class.html'>Padding</a>
  - 지정된 패딩으로 하위 항목을 삽입하는 위젯
<pre>
<code>
const Padding({
  Key? key,
  required this.padding,
  Widget? child,
}) : assert(padding != null),
     super(key: key, child: child);
 </code>
 </pre>
 
 ### Padding 주요 속성
  - **padding** : child를 삽입할 공간의 양
  - **child** : 단일 위젯 사용 가능

 ### EdgeInsets : 패딩 치수를 설명하는 데 사용되는 클래스
  - **EdgeInsets.all()** : 전체에 설정 가능 ex)const EdgeInsets.all(8.0)
  - **EdgeInsets.symmetric()** : vertical, horizontal에 설정 가능 ex)const EdgeInsets.symmetric(vertical: 8.0)
  - **dgeInsets.only** : left, right, top, bottom에 설정 가능 ex)const EdgeInsets.only(left: 40.0)

-------------------------------------------------------------------------------------------------------------


## <a href='https://api.flutter.dev/flutter/widgets/Expanded-class.html'>Expanded</a>
  - Column, Row 또는 Flex의 하위 항목을 확장하여 하위 항목이 사용 가능한 공간을 채우도록 하는 위젯
  - 주축을 따라 사용 가능한 공간을 채움
  - 확장하고 싶은 위젯에 둘러싸면 됨
  
  <pre>
  <code>
  const Expanded({
  Key? key,
  int flex = 1,
  required Widget child,
}) : super(key: key, flex: flex, fit: FlexFit.tight, child: child);
  </code>
  </pre>
  
  

