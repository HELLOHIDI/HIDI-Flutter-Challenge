# AspectRatio & ClipRRect Widget

## <a href='https://api.flutter.dev/flutter/widgets/AspectRatio-class.html'>AspectRatio Widget</a>
  - 특정 종횡비로 자식 크기를 조정하는 위젯
  - 이미지를 화면에 표시할 때는 비율로 표시하는 것이 좋다
  1. 먼저 레이아웃 제약에서 허용되는 가장 큰 너비 시도
  2. 위젯의 높이는 너비에 지정된 가로 세로 비율을 적용하여 결정되며 너비에 대한 높이 비율로 표현
  - ex)  화면 넓이 450, 높이 1000에서 비율을 3/2 일때 이미지의 크기는
    1. 가장 큰 너비 -> 이미지 넓이 450
    2. 3/2 비율 -> 450* 2/3 = 300 높이가 됨
 
### Implementaion
   <pre>
   <code>
 const AspectRatio({
   Key? key,
   required this.aspectRatio,
   Widget? child,
  }) : assert(aspectRatio != null),
     assert(aspectRatio > 0.0),
     // can't test isFinite because that's not a constant expression
     super(key: key, child: child);
     </code>
     </pre>
 ### AspectRatio 주요 속성
 - **aspectRatio** : 가로 세로 화면 비율 => final double aspectRatio;(required)
 - **child** : 자식 한개만 가능 => final Widget? child;
    
---------------------------------------------------------------------------------------------


## <a href='https://api.flutter.dev/flutter/widgets/ClipRRect-class.html'>ClipRRect Widget</a>
  - 둥근 사각형을 사용하여 자식을 자르는 위젯
  - 위젯에 shape이나 decoration 속성이 없다면 ClipRRect를 이용하여 모서리에 곡선을 줄 수 잇다.
  - Container 위젯 같은 경우 사용할 필요 x
  - ClipOval, ClipPath 등 테두리를 관리하는 다른 위젯들도 있음

### Implementation
<pre>
<code>
const ClipRRect({
  Key? key,
  this.borderRadius = BorderRadius.zero,
  this.clipper,
  this.clipBehavior = Clip.antiAlias,
  Widget? child,
}) : assert(borderRadius != null || clipper != null),
     assert(clipBehavior != null),
     super(key: key, child: child);
 </code>
 </pre>
 
 ### ClipRRect 주요 속성
  - **borderRadius** : 둥근 모서리의 테두리 반지름를 설정하는 속성 => final BorderRadius? borderRadius;
  - **child** : 자식 한개만 가능 => final Widget? child;
 

