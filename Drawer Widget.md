# Drawer Widget

## <a href='https://api.flutter.dev/flutter/material/Drawer-class.html'>Drawer Widget</a>
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

### 예시 코드
<pre>
<code>
Scaffold(
  appBar: AppBar(
    title: const Text('Drawer Demo'),
  ),
  drawer: Drawer(
    child: ListView(
      padding: EdgeInsets.zero,
      children: const <Widget>[
        DrawerHeader(
          decoration: BoxDecoration(
            color: Colors.blue,
          ),
          child: Text(
            'Drawer Header',
            style: TextStyle(
              color: Colors.white,
              fontSize: 24,
            ),
          ),
        ),
        ListTile(
          leading: Icon(Icons.message),
          title: Text('Messages'),
        ),
        ListTile(
          leading: Icon(Icons.account_circle),
          title: Text('Profile'),
        ),
        ListTile(
          leading: Icon(Icons.settings),
          title: Text('Settings'),
        ),
      ],
    ),
  ),
)
</code>
</pre>

### 실행 결과
https://user-images.githubusercontent.com/54922625/132118029-857a6c09-5630-4510-9eba-55cae7ade9ce.mp4

