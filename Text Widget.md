# Text Widget

## Text Widget
  - 단일 스타일의 텍스트 문자열을 표시하는 위젯
  - 문자열이 여러 줄에 걸쳐 끊어지거나 레이아웃 제약 조건에 따라 모두 같은 줄에 표시될 수 있습니다.
  - 스타일 속성을 사용하지 않으면 DefaultTextStyle을 둘러싸는 가장 가까운 곳의 스타일을 사용.
  
  <pre>
  <code>
  const Text(
  String this.data, {
    Key? key,
    this.style,
    this.strutStyle,
    this.textAlign,
    this.textDirection,
    this.locale,
    this.softWrap,
    this.overflow,
    this.textScaleFactor,
    this.maxLines,
    this.semanticsLabel,
    this.textWidthBasis,
    this.textHeightBehavior,
}) : assert(
       data != null,
       'A non-null String must be provided to a Text widget.',
     ),
     textSpan = null,
     super(key: key);
  </code>
  </pre>
  
  
### Text 주요 속성
  - **style** : TextStyle에서 자세히 설명
  - **textAlign** : 텍스트를 가로로 어떻게 정렬할지 정하는 속성
  - **maxLines** : 필요한 경우 줄 바꿈(선택 사항)으로 지정할 텍스트의 최대 행 수
  - **String this.data** : 보여질 텍스트


## <a href='https://api.flutter.dev/flutter/painting/TextStyle-class.html'>TextStyle</a>
  - 텍스트를 포맷하고 그리는 방법을 설명하는 텍스트 위젯 속성
  
  
  <pre>
  <code>
  const TextStyle({
    this.inherit = true,
    this.color,
    this.backgroundColor,
    this.fontSize,
    this.fontWeight,
    this.fontStyle,
    this.letterSpacing,
    this.wordSpacing,
    this.textBaseline,
    this.height,
    this.leadingDistribution,
    this.locale,
    this.foreground,
    this.background,
    this.shadows,
    this.fontFeatures,
    this.decoration,
    this.decorationColor,
    this.decorationStyle,
    this.decorationThickness,
    this.debugLabel,
    String? fontFamily,
    List<String>? fontFamilyFallback,
    String? package,
}) : fontFamily = package == null ? fontFamily : 'packages/$package/$fontFamily',
     _fontFamilyFallback = fontFamilyFallback,
     _package = package,
     assert(inherit != null),
     assert(color == null || foreground == null, _kColorForegroundWarning),
     assert(backgroundColor == null || background == null, _kColorBackgroundWarning);
  </code>
  </pre>
  
  ### TextStyle 주요 속성
  - **fontSize** : 텍스트 크기 => final double? fontSize;
  - **color, backgroundColor** : 텍스트 색, 배경색 => final Color? color; / final Color? backgroundColor;
  - **fontWeight** : 텍스트를 그릴 때 사용할 서체 두께 => final FontWeight? fontWeight;;
  - **fontFamily** : 텍스트를 그릴 때 사용할 글꼴 => final String? fontFamily;
  - **decoration** : 텍스트 근처에 그릴 장식(예: 밑줄) => final TextDecoration? decoration;
