# AppBar Widget

## <A href='https://api.flutter.dev/flutter/material/AppBar-class.html'>AppBar Widget</a>
  -  앱 바를 디자인하는 위젯
  -  SliverAppBar: 앱바를 사용하여 사용자 지정 스크롤 보기에서 사용할 수 있는 유연한 앱바를 제공
  -  시스템 UI 침입을 방지하기 위해 주변 MediaQuery의 패딩에 따라 콘텐츠를 삽입합니다.


  ![image](https://user-images.githubusercontent.com/54922625/131448624-08a61a01-9a1a-4d06-aa89-92796bf4dafe.png)
  
  ### Implementation
  <pre>
  <code>
   AppBar({
    Key? key,
    this.leading,
    this.automaticallyImplyLeading = true,
    this.title,
    this.actions,
    this.flexibleSpace,
    this.bottom,
    this.elevation,
    this.shadowColor,
    this.shape,
    this.backgroundColor,
    this.foregroundColor,
    this.brightness,
    this.iconTheme,
    this.actionsIconTheme,
    this.textTheme,
    this.primary = true,
    this.centerTitle,
    this.excludeHeaderSemantics = false,
    this.titleSpacing,
    this.toolbarOpacity = 1.0,
    this.bottomOpacity = 1.0,
    this.toolbarHeight,
    this.leadingWidth,
    this.backwardsCompatibility,
    this.toolbarTextStyle,
    this.titleTextStyle,
    this.systemOverlayStyle,
}) : assert(automaticallyImplyLeading != null),
     assert(elevation == null || elevation >= 0.0),
     assert(primary != null),
     assert(toolbarOpacity != null),
     assert(bottomOpacity != null),
     preferredSize = Size.fromHeight(toolbarHeight ?? kToolbarHeight + (bottom?.preferredSize.height ?? 0.0)),
     super(key: key);
     </code>
     </pre>
 ### AppBar 주요 속성
  - **actions** : 제목 위젯 다음에 행에 표시할 위젯 목록입니다. => final List<Widget>? actions; <br>
      1. 일반적으로 iconButton으로 구성된다
  - **leading** : 툴바 제목 앞에 표시할 위젯 => final Widget? leading; <br>
      1. 일반적으로 icon 또는 iconButton으로 구성된다.
      2. 네비게이션의 주요 구성 요소가 됨.
  
  - **title** : 앱 모음에 표시되는 기본 위젯 => final Widget? title;
  - **bottom** : 앱 바의 맨 아래를 나타냄 => final PreferredSizeWidget? bottom;
      1. 일반적으로 탭 표시줄로 사용
      2. PreferredSizeWidget을 구현하는 위젯만 사용 가능.
  - **backgroundColor** : 앱바의 배경 색 => final Color? backgroundColor;
  - **elevation** : 앱 바 아래의 그림자 크기를 제어 => final double? elevation;
  
  
