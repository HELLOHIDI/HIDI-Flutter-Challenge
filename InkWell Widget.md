# InkWell Widget

## <a href='https://api.flutter.dev/flutter/material/InkWell-class.html'>InkWell Widget</a>
  - 모든 위젯을 버튼화 시켜주는 위젯
  - 버튼 디자인을 가장 자유롭게 할 수 있기 때문에 가장 선호됨
  
  ### Implementation
  <pre>
  <code>
  const InkWell(
    {Key? key,
    Widget? child,
    GestureTapCallback? onTap,
    GestureTapCallback? onDoubleTap,
    GestureLongPressCallback? onLongPress,
    GestureTapDownCallback? onTapDown,
    GestureTapCancelCallback? onTapCancel,
    ValueChanged<bool>? onHighlightChanged,
    ValueChanged<bool>? onHover,
    MouseCursor? mouseCursor,
    Color? focusColor,
    Color? hoverColor,
    Color? highlightColor,
    MaterialStateProperty<Color?>? overlayColor,
    Color? splashColor,
    InteractiveInkFeatureFactory? splashFactory,
    double? radius,
    BorderRadius? borderRadius,
    ShapeBorder? customBorder,
    bool? enableFeedback = true,
    bool excludeFromSemantics = false,
    FocusNode? focusNode,
    bool canRequestFocus = true,
    ValueChanged<bool>? onFocusChange,
    bool autofocus = false}
  )
  </code>
  </pre>
  
  ### InkWell 주요 속성
  - **child** : 자식 위젯을 한개만 가질 수 있음
  - **onTap** : 버튼을 눌렀을 때 일어나는 반응을 담당하는 속성
  
