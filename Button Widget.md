# Button Widget

## <a href='https://api.flutter.dev/flutter/material/TextButton-class.html'>TextButton Widget</a>
  - 버튼 자체에 아무런 디자인 x
  - 그냥 Text를 클릭할 수 있게 만들어 주는 효과만 가지고 있음

## <a href='https://api.flutter.dev/flutter/material/ElevatedButton-class.html'>ElevatedButton Widget</a>
  - 버튼 자체에 elevation 효과 적용
  - 버튼 오른쪽과 아래쪽 부분에 그림자 효과가 생겨 약간 떠올라 있는 느낌을 줌

## <a href='https://api.flutter.dev/flutter/material/OutlinedButton-class.html'>OutlinedButton Widget</a>
  - 가장자리에 테두리 선을 가지고 있음


### Implementation
<pre>
<code>
const TextButton(
  {Key? key,
  required VoidCallback? onPressed,
  VoidCallback? onLongPress,
  ButtonStyle? style,
  FocusNode? focusNode,
  bool autofocus = false,
  Clip clipBehavior = Clip.none,
  required Widget child}
  )
  </code>
  </pre>

### Button 주요 속성
- **required child** : 버튼의 요소
- **required onPressed** : 버튼을 눌렀을 때 반응을 담당하는 속성
- **style** : Button Style에서 자세히 설명

## <a href='https://api.flutter.dev/flutter/material/IconButton-class.html'>IconButton</a>
  - 아이콘 모양의 버튼
  - 일반적으로 AppBar.actinos 필드에서 사용됨

### Implementation
<pre>
<code>
const IconButton(
  {Key? key,
  double iconSize,
  VisualDensity? visualDensity,
  EdgeInsetsGeometry padding,
  AlignmentGeometry alignment,
  double? splashRadius,
  Color? color,
  Color? focusColor,
  Color? hoverColor,
  Color? highlightColor,
  Color? splashColor,
  Color? disabledColor,
  required VoidCallback? onPressed,
  MouseCursor mouseCursor,
  FocusNode? focusNode,
  bool autofocus,
  String? tooltip,
  bool enableFeedback,
  BoxConstraints? constraints,
  required Widget icon}
)
</code>
</pre>

### IconButton 주요 속성
- **required icon** : 아이콘 모양
- **required onPressed** : 버튼을 눌렀을 때의 반응을 담당하는 속성
- **color** : 아이콘 색상
- **padding** : 여백을 담당하는 속성
- **alignment** : 정렬을 담당하는 속성


## <a href='https://api.flutter.dev/flutter/material/ButtonStyle-class.html'>Button Style Property</a>
  - 버튼이 공통적으로 가지고 있는 시각적 속성

### Implementation
<pre>
<code>
const ButtonStyle(
  {MaterialStateProperty<TextStyle?>? textStyle,
  MaterialStateProperty<Color?>? backgroundColor,
  MaterialStateProperty<Color?>? foregroundColor,
  MaterialStateProperty<Color?>? overlayColor,
  MaterialStateProperty<Color?>? shadowColor,
  MaterialStateProperty<double?>? elevation,
  MaterialStateProperty<EdgeInsetsGeometry?>? padding,
  MaterialStateProperty<Size?>? minimumSize,
  MaterialStateProperty<Size?>? fixedSize,
  MaterialStateProperty<BorderSide?>? side,
  MaterialStateProperty<OutlinedBorder?>? shape,
  MaterialStateProperty<MouseCursor?>? mouseCursor,
  VisualDensity? visualDensity,
  MaterialTapTargetSize? tapTargetSize,
  Duration? animationDuration,
  bool? enableFeedback,
  AlignmentGeometry? alignment,
  InteractiveInkFeatureFactory? splashFactory}
  )
</code>
</pre>



