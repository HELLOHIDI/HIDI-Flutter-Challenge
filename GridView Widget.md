# GridView Widget

## <a href='https://api.flutter.dev/flutter/widgets/GridView-class.html'>GridView Widget</a>
  - 수평, 수직 방향으로 고정 수의 위젯을 생성하고 반복해서 List를 출력해주는 위젯
  - 주요 축 방향은 Grid가 Scroll 하는 방향
  - 스크롤이 가능하다
  
## GridView Constructure
- **GridView** : 길이가 정해져 있는 GridView
- **GridView.count** : 가로 축에 고정된 수의 타일을 사용한 GridView 
- **GridView.builder** : 필요에 따라 작성되는 GridView

--------------------------
### GridView
- ListView의 생성자와 거의 유사
#### Implementation
<pre>
<code>
GridView(
  {Key? key,
  Axis scrollDirection = Axis.vertical,
  bool reverse = false,
  ScrollController? controller,
  bool? primary,
  ScrollPhysics? physics,
  bool shrinkWrap = false,
  EdgeInsetsGeometry? padding,
  required SliverGridDelegate gridDelegate,
  bool addAutomaticKeepAlives = true,
  bool addRepaintBoundaries = true,
  bool addSemanticIndexes = true,
  double? cacheExtent,
  List<Widget> children = const <Widget>[],
  int? semanticChildCount,
  DragStartBehavior dragStartBehavior = DragStartBehavior.start,
  Clip clipBehavior = Clip.hardEdge,
  ScrollViewKeyboardDismissBehavior keyboardDismissBehavior = ScrollViewKeyboardDismissBehavior.manual,
  String? restorationId}
  )
</code>
</pre>

#### GridView 주요 속성
- **Axis scrollDirection = Axis.vertical** : 스크롤 방향(기본적으로는 수직)
- **required SliverGridDelegate gridDelegate** : gridDelegate에서 자세히 설명
- **List<Widget> children = const <Widget>[]** : GirdView에 들어가는 아이템
- **EdgeInsetsGeometry? padding** : 하위 항목 간의 간격

--------------------------
### GridView.count
#### Implementation
<pre>
<code>
GridView.count(
  {Key? key,
  Axis scrollDirection = Axis.vertical,
  bool reverse = false,
  ScrollController? controller,
  bool? primary,
  ScrollPhysics? physics,
  bool shrinkWrap = false,
  EdgeInsetsGeometry? padding,
  required int crossAxisCount,
  double mainAxisSpacing = 0.0,
  double crossAxisSpacing = 0.0,
  double childAspectRatio = 1.0,
  bool addAutomaticKeepAlives = true,
  bool addRepaintBoundaries = true,
  bool addSemanticIndexes = true,
  double? cacheExtent,
  List<Widget> children = const <Widget>[],
  int? semanticChildCount,
  DragStartBehavior dragStartBehavior = DragStartBehavior.start,
  ScrollViewKeyboardDismissBehavior keyboardDismissBehavior = ScrollViewKeyboardDismissBehavior.manual,
  String? restorationId,
  Clip clipBehavior = Clip.hardEdge}
)
</code>
</pre>

#### GridView.count 주요 속성
- **required int crossAxisCount** : 횡축의 아이템 개수(고정 된 수의 타일이기 때문)
- **double mainAxisSpacing, crossAxisSpacing** : 주축, 횡축 사이의 간격 
- Axis scrollDirection = Axis.vertical : 스크롤 방향(기본적으로는 수직)
- required SliverGridDelegate gridDelegate : gridDelegate에서 자세히 설명
- List<Widget> children = const <Widget>[] : GirdView에 들어가는 아이템
- EdgeInsetsGeometry? padding : 하위 항목 간의 간격

--------------------------
### GridView.builder
  - item의 개수가 동적일 때(무한하거나, 정해지지 않았을 때) 사용하는 생성자

#### Implementation
<pre>
<code>
GridView.builder(
  {Key? key,
  Axis scrollDirection = Axis.vertical,
  bool reverse = false,
  ScrollController? controller,
  bool? primary,
  ScrollPhysics? physics,
  bool shrinkWrap = false,
  EdgeInsetsGeometry? padding,
  required SliverGridDelegate gridDelegate,
  required IndexedWidgetBuilder itemBuilder,
  int? itemCount,
  bool addAutomaticKeepAlives = true,
  bool addRepaintBoundaries = true,
  bool addSemanticIndexes = true,
  double? cacheExtent,
  int? semanticChildCount,
  DragStartBehavior dragStartBehavior = DragStartBehavior.start,
  ScrollViewKeyboardDismissBehavior keyboardDismissBehavior = ScrollViewKeyboardDismissBehavior.manual,
  String? restorationId,
  Clip clipBehavior = Clip.hardEdge}
)
</code>
</pre>

#### GridView.builder 주요 속성
- **required IndexedWidgetBuilder itemBuilder** : 지정된 인덱스에 대한 위젯을 만드는 함수
  <pre>
  <code>
  Widget IndexedWidgetBuilder(
    BuildContext context,
    int index
   )
  </code>
  </pre>
- **int? itemCOunt** : 아이템의 개수
- Axis scrollDirection = Axis.vertical : 스크롤 방향(기본적으로는 수직)
- required SliverGridDelegate gridDelegate : gridDelegate에서 자세히 설명
- List<Widget> children = const <Widget>[] : GirdView에 들어가는 아이템
- EdgeInsetsGeometry? padding : 하위 항목 간의 간격

----------------------------
## <a href='https://api.flutter.dev/flutter/rendering/SliverGridDelegate-class.html'>SliverGridDelegate class</a>
  - 그리드에서 타일의 레이아웃을 제어하는 속성

### SliverGridDelegateWithFixedCrossAxisCount
  - 가로축에 고정 개수의 타일을 사용하여 그리드 레이아웃 작성
  - 타일의 개수가 정해져 있을 경우 사용 가능
  - 동일한 크기와 간격의 타일로 그리드 작성

#### Implementation
<pre>
<code>
const SliverGridDelegateWithFixedCrossAxisCount(
  {required int crossAxisCount,
  double mainAxisSpacing,
  double crossAxisSpacing,
  double childAspectRatio,
  double? mainAxisExtent}
)
</code>
</pre>

#### SliverGridDelegateWithFixedCrossAxisCount 주요 속성
  - **required int crossAxisCount** : 횡축의 아이템 개수
  - **double mainAxisSpacing, crossAxisSpacing** : 주축, 횡축 사이의 간격 
  

### SliverGridDelegateWithMaxCrossAxisExtent
  - 각각 최대 교차 축 범위를 갖는 타일을 사용하여 그리드 레이아웃 작성
  - 동일한 크기와 간격의 타일로 그리드 작성

#### Implementation
<pre>
<code>
const SliverGridDelegateWithMaxCrossAxisExtent(
  {required double maxCrossAxisExtent,
  double mainAxisSpacing,
  double crossAxisSpacing,
  double childAspectRatio,
  double? mainAxisExtent}
)
</code>
</pre>

#### SliverGridDelegateWithMaxCrossAxisExtent 주요 속성
 - **required double maxCrossAxisExtent** : 횡축의 최대 범위
 - **double mainAxisSpacing, crossAxisSpacing** : 주축, 횡축 사이의 간격 

