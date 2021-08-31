#Icon Widget

## <a href='https://api.flutter.dev/flutter/widgets/Icon-class.html'>Icon Widget</a>
  - 아이콘을 그리는 위젯

  ### Implementation
  <pre>
  <code>
  const Icon(
    this.icon, {
    Key? key,
    this.size,
    this.color,
    this.semanticLabel,
    this.textDirection,
}) : super(key: key);
  </code>
  </pre>
  
  ### Icon 주요 속성
  - icon : 표시할 아이콘 => final IconData? icon;
  - color : 아이콘의 색상 => final Color? color;
  - size : 아이콘의 크기 => final double? size;<br>
    1. 아이콘은 너비와 높이가 같은 정사각형을 차지
    2. 명시적 크기를 지정하지 않은 경우 기본값은 24.0
