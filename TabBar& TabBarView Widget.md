# TabBar& TabBarView Widget

## <a href='https://api.flutter.dev/flutter/material/TabBar-class.html'>TabBar Widget</a>
  - 탭의 가로 행을 표시하는 머티리얼 디자인 위젯
  - statefulWidget으로 연결해야됨!

### Implementation
<pre>
<code>
const TabBar(
  {Key? key,
  required List<Widget> tabs,
  TabController? controller,
  bool isScrollable,
  Color? indicatorColor,
  bool automaticIndicatorColorAdjustment,
  double indicatorWeight,
  EdgeInsetsGeometry indicatorPadding,
  Decoration? indicator,
  TabBarIndicatorSize? indicatorSize,
  Color? labelColor,
  TextStyle? labelStyle,
  EdgeInsetsGeometry? labelPadding,
  Color? unselectedLabelColor,
  TextStyle? unselectedLabelStyle,
  DragStartBehavior dragStartBehavior,
  MaterialStateProperty<Color?>? overlayColor,
  MouseCursor? mouseCursor,
  bool? enableFeedback,
  ValueChanged<int>? onTap,
  ScrollPhysics? physics}
  )
</code>
</pre>

### TabBar 주요 속성
- **required List<Widget> tabs** : tab 화면의 개수<br>
  => Tab요소를 가지는 위젯
- **TabController? controller** : TabController에서 자세히 설명
  
-----------------------------------------------------------------------  
  
## <a href='https://api.flutter.dev/flutter/material/TabBarView-class.html'>TabBarView Widget</a>
  - 현재 선택된 탭에 해당하는 화면 표시하는 위젯
  - TabController.length 와 list item의 개수가 같아야 된다.
  
### Implementation
<pre>
<code>
const TabBarView(
  {Key? key,
  required List<Widget> children,
  TabController? controller,
  ScrollPhysics? physics,
  DragStartBehavior dragStartBehavior}
)
</code>
</pre>

### TabBarView 주요 속성
- **required List<Widget> children** : 각각의 화면
- **TabController controller** : TabController에서 자세히 설명

## <a href='https://api.flutter.dev/flutter/material/TabController-class.html'>TabController</a>
  - TabBar,TabBarView 사이의 탭 선택을 조정하는 속성
  - TabBar,TabBarView 위젯에 객체를 연결하면 선택된 Tab에 따라 화면 변경
  - initState() 함수를 통해서 StatefullWidget에서 초기화를 해서 선언한다.

### Implementation
<pre>
<code>
TabController(
  {int initialIndex = 0,
  required int length,
  required TickerProvider vsync}
)
</code>
</pre>

### TabController 주요 속성
- **required int length** : 탭의 개수
- **required TickerProvider vsync** : this해주면 됨<br>
**=> 단, 애니메이션이 한개 일 때 : SingleTicketProviderStateMixin을 with해주고<br>
              애니메이션이 여러개 일 때 : TickerProviderStateMixin을 with 해준다**



## 예시 코드
<pre>
<code>
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

/// This is the main application widget.
class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  static const String _title = 'Flutter Code Sample';

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      title: _title,
      home: MyStatefulWidget(),
    );
  }
}

/// This is the stateful widget that the main application instantiates.
class MyStatefulWidget extends StatefulWidget {
  const MyStatefulWidget({Key? key}) : super(key: key);

  @override
  State<MyStatefulWidget> createState() => _MyStatefulWidgetState();
}

/// This is the private State class that goes with MyStatefulWidget.
/// AnimationControllers can be created with `vsync: this` because of TickerProviderStateMixin.
class _MyStatefulWidgetState extends State<MyStatefulWidget>
    with TickerProviderStateMixin {
  late TabController _tabController;

  @override
  void initState() {
    super.initState();
    _tabController = TabController(length: 3, vsync: this);
    /// tabController 선언 : 길이가 3이고, 애니메이션이 2개임으로 with TickerProviderStateMixin
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('TabBar Widget'),
        ///TabBar
        bottom: TabBar(
          controller: _tabController, //controller 객체 연결
          tabs: const <Widget>[
            Tab(
              icon: Icon(Icons.cloud_outlined),
            ),
            Tab(
              icon: Icon(Icons.beach_access_sharp),
            ),
            Tab(
              icon: Icon(Icons.brightness_5_sharp),
            ),
          ],
        ),
      ),
      //TabBarView
      body: TabBarView(
        controller: _tabController, //controller 객체 연결
        children: const <Widget>[
          Center(
            child: Text("It's cloudy here"),
          ),
          Center(
            child: Text("It's rainy here"),
          ),
          Center(
            child: Text("It's sunny here"),
          ),
        ],
      ),
    );
  }
}

</code>
</pre>

![image](https://user-images.githubusercontent.com/54922625/132098106-f8feb535-28b1-485a-923d-5a426081892b.png)
