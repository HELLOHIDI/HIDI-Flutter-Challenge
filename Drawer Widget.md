# Drawer Widget

## Drawer Widget
  - Scaffold 속성 위젯
  - 탐색 링크를 표시하기 위해 Scaffold의 가장자리에서 수평으로 슬라이드 하는 위젯
  - 왼쪽 : drawer 속성 / 오른쪽 : endDrawer 속성
  - drawer의 children은 일반적으로 ListView & ListTiles를 사용한다
  - appBar가 있는 Scaffold는 자동으로 버튼을 추가한다
  - drawer은 Navigator.pop를 통해 닫을 수 있음. ex)서랍 항목을 누르면 서랍이 닫힐 수 있다

### Implementation
<pre>
<code>
const Drawer(
  {Key? key,
  double elevation,
  Widget? child,
  String? semanticLabel}
)
</code>
</pre>

### Drawer 주요 속성
- Widget? child : 단일 위젯을 가짐
