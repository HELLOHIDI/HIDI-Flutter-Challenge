# Row & Column Widget

## <a href="https://api.flutter.dev/flutter/widgets/Row-class.html">Row 위젯</a>
  - 수평 방향 레이아웃 구조를 만들어주는 위젯
  - children 속성을 가짐 : 많은 위젯을 가질 수 있음
  - 스크롤X => ListView 사용 고려
  - 자식이 확장되어 사용 가능한 가로 공간을 채우도록 하려면 자식을 Expanded 위젯으로 래핑
<pre>
<code>
Row({
      Key? key,
      MainAxisAlignment mainAxisAlignment = MainAxisAlignment.start,
      MainAxisSize mainAxisSize = MainAxisSize.max,
      CrossAxisAlignment crossAxisAlignment = CrossAxisAlignment.center,
      TextDirection? textDirection,
      VerticalDirection verticalDirection = VerticalDirection.down,
      TextBaseline? textBaseline, // NO DEFAULT: we don't know what the text's baseline should be
      List<Widget> children = const <Widget>[],
    }) : super(
      children: children,
      key: key,
      direction: Axis.horizontal,
      mainAxisAlignment: mainAxisAlignment,
      mainAxisSize: mainAxisSize,
      crossAxisAlignment: crossAxisAlignment,
      textDirection: textDirection,
      verticalDirection: verticalDirection,
      textBaseline: textBaseline,
    );
</code>
</pre>
  ### Row 위젯 주요 속성<br>
  - **List<Widget> children** : 많은 위젯을 가질 수 있음<br>
  - **MainAxisAlignment mainAxisAlignment** : 주축을 기준으로 정렬 (가로축 기준 정렬)<br>
  - **CrossAxisAlignment crossAxisAlignment** : 주축이 아닌 축을 기준으로 정렬 (세로축 기준 정렬)<br>




----------------------------------------------------------------------------------------------------

## <a href="https://api.flutter.dev/flutter/widgets/Column-class.html">Column 위젯</a>
  - 수직 방향 레이아웃 구조를 만들어주는 위젯
  - children 속성을 가짐 : 많은 위젯을 가질 수 있음
  - 스크롤X => ListView 사용 고려
  - 자식이 확장되어 사용 가능한 가로 공간을 채우도록 하려면 자식을 Expanded 위젯으로 래핑
  
<pre>
<code>
Column({
      Key? key,
      MainAxisAlignment mainAxisAlignment = MainAxisAlignment.start,
      MainAxisSize mainAxisSize = MainAxisSize.max,
      CrossAxisAlignment crossAxisAlignment = CrossAxisAlignment.center,
      TextDirection? textDirection,
      VerticalDirection verticalDirection = VerticalDirection.down,
      TextBaseline? textBaseline,
      List<Widget> children = const <Widget>[],
    }) : super(
      children: children,
      key: key,
      direction: Axis.vertical,
      mainAxisAlignment: mainAxisAlignment,
      mainAxisSize: mainAxisSize,
      crossAxisAlignment: crossAxisAlignment,
      textDirection: textDirection,
      verticalDirection: verticalDirection,
      textBaseline: textBaseline,
    );
</code>
</pre>
  
  
  ### Column 위젯 주요 속성<br>
  - **List<Widget> children** : 많은 위젯을 가질 수 있음<br>
  - **MainAxisAlignment mainAxisAlignment** : 주축을 기준으로 정렬 (세로축 기준 정렬) <br> 
  - **CrossAxisAlignment crossAxisAlignment** : 주축이 아닌 축을 기준으로 정렬 (가로축 기준 정렬) <br> 
  
