# Container Widget
  
## <a href='https://api.flutter.dev/flutter/painting/Container-class.html'>Container Widget</a>
  - 빈 박스 위젯
  - BUT SizedBox와 차이점은 내부에 decoration 속성이 있어 박스를 꾸밀 수 있다.cf)SizedBox는 보통 마진을 줄 때 사용
  - 자식이 없는 Container는 가능한 한 박스를 크게 만들려고 함
  - but 자식이 있는 COntainer는 자식의 크기에 맞게 조정됨

  ### Implementation
  <pre>
  <code>
  Container({
    Key? key,
    this.alignment,
    this.padding,
    this.color,
    this.decoration,
    this.foregroundDecoration,
    double? width,
    double? height,
    BoxConstraints? constraints,
    this.margin,
    this.transform,
    this.transformAlignment,
    this.child,
    this.clipBehavior = Clip.none,
}) : assert(margin == null || margin.isNonNegative),
     assert(padding == null || padding.isNonNegative),
     assert(decoration == null || decoration.debugAssertIsValid()),
     assert(constraints == null || constraints.debugAssertIsValid()),
     assert(clipBehavior != null),
     assert(decoration != null || clipBehavior == Clip.none),
     assert(color == null || decoration == null,
       'Cannot provide both a color and a decoration\n'
       'To provide both, use "decoration: BoxDecoration(color: color)".',
     ),
     constraints =
      (width != null || height != null)
        ? constraints?.tighten(width: width, height: height)
          ?? BoxConstraints.tightFor(width: width, height: height)
        : constraints,
     super(key: key);
  </code>
  </pre>
  
  ### Container 주요 속성
  - **padding** : 장식 내부에 새길 빈 공간, child는 padding 안에 배치 됨 => final EdgeInsetsGeometry? padding;
  - **color** : child 뒷 배경색 , 그라데이션 이미지 같은 것은 decoration에서 활용  => final Color? color;
  - **decoration** : child를 장식하는 속성 => final BoxDecoration? decoratino;(주로 사용)
  - **width, height** : container 가로 세로 크기
  - **constraints** : 하위 항목에 적용할 추가 제약 조건 => final BoxConstraints? constraints;
      1. 생성자 폭 및 높이 인수 등등 
      2. 패딩은 구속조건 안으로 들어감 
  - **child** : 한 개의 위젯만 가능 => final Widget? child;
  - **alignment** : child 내부를 정렬 => final AlignmentGeometry? alignment; 
  
  
## BoxDecoration
  - 상자를 그리는 다양한 방법 제공

  ### Implementation
  <pre>
  <code>
  const BoxDecoration({
    this.color,
    this.image,
    this.border,
    this.borderRadius,
    this.boxShadow,
    this.gradient,
    this.backgroundBlendMode,
    this.shape = BoxShape.rectangle,
}) : assert(shape != null),
     assert(
       backgroundBlendMode == null || color != null || gradient != null,
       "backgroundBlendMode applies to BoxDecoration's background color or "
       'gradient, but no color or gradient was provided.',
     );
     </code>
     </pre>
 
 ### <a href='https://api.flutter.dev/flutter/painting/BoxDecoration-class.html'>BoxDecoration 주요 속성</a>
  - **color** : 상자의 배경을 채울 색상 => final Color? color;
      1. 색상은 상자 모양으로 채워짐
  - **image** : 배경색 또는 그라데이션 위에 그릴 이미지 => final DecorationImage? image;
  - **border** : 테두리를 그리는 속성 => final BoxBorder? border;
      1. shape, borderRadius 속성에 따른다
  - **borderRadius** : 테두리를 얼만큼 둥글게 만들지 결정하는 속성 => final BorderRadiusGeometry? borderRadius;
      1. 모양이나 테두리가 장식된 Container의 child를 잘라내지 않음
  - **shape** : 박스 모양을 결정하는 위젯(circle,Recktangle) => final BoxShape shape;
      1. 모양이나 테두리가 장식된 Container의 child를 잘라내지 않음

