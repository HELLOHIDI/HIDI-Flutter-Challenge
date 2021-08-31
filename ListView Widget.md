# ListView Widget

## <a href='https://api.flutter.dev/flutter/widgets/ListView-class.html'>ListView Widget</a>
  - 가장 일반적으로 사용되는 스크롤 위젯

  ### List View option
  ### 1. ListView 기본 생성자 이용
  - 명시적으로 children으로 넘김
  - 적은 수의 아이템을 가질 때에 적합
  - ListView 로드 시점에 모든 child가 생성
  
  #### 예시 코드
   <pre>
   <code>
   class ExplicitListConstructing extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
      return ListView(
        padding: const EdgeInsets.all(8),
        children: <Widget>[
          HeaderTile(),
          PersonTile(people[0]),
          PersonTile(people[1]),
          PersonTile(people[2]),
          PersonTile(people[3]),
          PersonTile(people[4]),
          PersonTile(people[5]),
        ],
      );
    }
  }
   </code>
   </pre>

#### 실행 결과
![image](https://user-images.githubusercontent.com/54922625/131475286-41886930-4074-4edf-b782-1fa0e689a2fa.png)


  #### Implementation
  <pre>
  <code>
  ListView({
  Key? key,
  Axis scrollDirection = Axis.vertical,
  bool reverse = false,
  ScrollController? controller,
  bool? primary,
  ScrollPhysics? physics,
  bool shrinkWrap = false,
  EdgeInsetsGeometry? padding,
  this.itemExtent,
  bool addAutomaticKeepAlives = true,
  bool addRepaintBoundaries = true,
  bool addSemanticIndexes = true,
  double? cacheExtent,
  List<Widget> children = const <Widget>[],
  int? semanticChildCount,
  DragStartBehavior dragStartBehavior = DragStartBehavior.start,
  ScrollViewKeyboardDismissBehavior keyboardDismissBehavior = ScrollViewKeyboardDismissBehavior.manual,
  String? restorationId,
  Clip clipBehavior = Clip.hardEdge,
}) : childrenDelegate = SliverChildListDelegate(
       children,
       addAutomaticKeepAlives: addAutomaticKeepAlives,
       addRepaintBoundaries: addRepaintBoundaries,
       addSemanticIndexes: addSemanticIndexes,
     ),
     super(
       key: key,
       scrollDirection: scrollDirection,
       reverse: reverse,
       controller: controller,
       primary: primary,
       physics: physics,
       shrinkWrap: shrinkWrap,
       padding: padding,
       cacheExtent: cacheExtent,
       semanticChildCount: semanticChildCount ?? children.length,
       dragStartBehavior: dragStartBehavior,
       keyboardDismissBehavior: keyboardDismissBehavior,
       restorationId: restorationId,
       clipBehavior: clipBehavior,
     );
     </code>
     </pre>
     
 #### ListView 주요 속성
  - **padding** : children을 삽입할 공간 => final EdgeInsetsGeometry? padding;
  - **scrollDirection ** : 스크롤 방향 설정 속성 => final Axis scrollDirection;
 
     
-----------------------------------------------------------------------------------------------------


   
    
  ### 2. <a href='https://api.flutter.dev/flutter/widgets/ListView/ListView.builder.html'>ListView.builder</a> : 하위 항목을 빌드하는 IndexedWidgetBuilder를 사용
  **IndexedWidgetBuilder** : typedef IndexedWidgetBuilder = Widget Function(BuildContext context, int index);<br>
  => **itemBuilder의 생성자**<br>
  => **int index : child가 ListView 몇번째 자식인지를 나타냄**
  
  - 하위 항목 수가 많거나 무한인 경우에 적합
  - itemCount : 리스트에 그려질 총 child 개수
  - itemBuilder : 리스트에 그려질 항목을 Lazy하게, 해당 child가 화면에 보여야 할 때 생성
  
  #### 예시 코드
  <pre>
  <code>
  class UsingBuilderListConstructing extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ListView.builder(
      padding: const EdgeInsets.all(8),
      itemCount: people.length + 1,
      itemBuilder: (BuildContext context, int index) {
        if (index == 0) return HeaderTile();
        return PersonTile(people[index-1]);
      },
    );
  }
}
</code>
</pre>

#### 실행 결과
![image](https://user-images.githubusercontent.com/54922625/131476650-1e9e7482-f3e5-4e78-8934-a6c8911325ab.png)



#### Implementation
 <pre>
 <code>
 ListView.builder({
  Key? key,
  Axis scrollDirection = Axis.vertical,
  bool reverse = false,
  ScrollController? controller,
  bool? primary,
  ScrollPhysics? physics,
  bool shrinkWrap = false,
  EdgeInsetsGeometry? padding,
  this.itemExtent,
  required IndexedWidgetBuilder itemBuilder,
  int? itemCount,
  bool addAutomaticKeepAlives = true,
  bool addRepaintBoundaries = true,
  bool addSemanticIndexes = true,
  double? cacheExtent,
  int? semanticChildCount,
  DragStartBehavior dragStartBehavior = DragStartBehavior.start,
  ScrollViewKeyboardDismissBehavior keyboardDismissBehavior = ScrollViewKeyboardDismissBehavior.manual,
  String? restorationId,
  Clip clipBehavior = Clip.hardEdge,
}) : assert(itemCount == null || itemCount >= 0),
     assert(semanticChildCount == null || semanticChildCount <= itemCount!),
     childrenDelegate = SliverChildBuilderDelegate(
       itemBuilder,
       childCount: itemCount,
       addAutomaticKeepAlives: addAutomaticKeepAlives,
       addRepaintBoundaries: addRepaintBoundaries,
       addSemanticIndexes: addSemanticIndexes,
     ),
     super(
       key: key,
       scrollDirection: scrollDirection,
       reverse: reverse,
       controller: controller,
       primary: primary,
       physics: physics,
       shrinkWrap: shrinkWrap,
       padding: padding,
       cacheExtent: cacheExtent,
       semanticChildCount: semanticChildCount ?? itemCount,
       dragStartBehavior: dragStartBehavior,
       keyboardDismissBehavior: keyboardDismissBehavior,
       restorationId: restorationId,
       clipBehavior: clipBehavior,
     );
 
 </code>
 </pre>
 
 #### ListView.builder 주요 속성
  - **scrollDirection** : 스크롤 방향 설정 속성 => final Axis scrollDirection;
  - **padding** : children을 삽입할 공간 => final EdgeInsetsGeometry? padding;
  - **itemCount** : child의 개수 => int? itemCount
  - **itemBuilder** : child들을 어떻게 배치할 지 정하는 속성 => required IndexedWidgetBuilder itemBuilder


----------------------------------------------------------------------------------------------------------------------
  
  ### 3. <a href='https://api.flutter.dev/flutter/widgets/ListView/ListView.seperated.html'>ListView.seperated</a> : 자식 수가 고정된 목록일 경우 적합
  - 스크롤이 적용되지 않는 부분을 제작하고 싶을 때 활용
  - 두 개의 IndexedWidgetBuilder를 사용
  - 스크롤 영향 item - 구분 기호 - 스크롤 영향 item 순으로 계속 반복
  - ListView.seperated -> separatorBuilder 이런 식으로 코딩
  - separatorCount = itemCount-1
  
  #### 예시 코드
  <pre>
  <code>
  class UsingSeparateListConstructing extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ListView.separated(
        itemCount: people.length + 1,
        itemBuilder: (context, index) {
          if (index == 0) return HeaderTile();
          return PersonTile(people[index - 1]);
        },
        separatorBuilder: (context, index) {
          if (index == 0) return SizedBox.shrink();
          return const Divider();
        },
    );
  }
}
  </code>
  </pre>
  
  #### 실행 결과
  ![image](https://user-images.githubusercontent.com/54922625/131477761-b080e3bc-2e07-46fd-bc67-a45e86b1e355.png)
  
  
  #### Implementation
  <pre>
  <code>
  ListView.separated({
  Key? key,
  Axis scrollDirection = Axis.vertical,
  bool reverse = false,
  ScrollController? controller,
  bool? primary,
  ScrollPhysics? physics,
  bool shrinkWrap = false,
  EdgeInsetsGeometry? padding,
  required IndexedWidgetBuilder itemBuilder,
  required IndexedWidgetBuilder separatorBuilder,
  required int itemCount,
  bool addAutomaticKeepAlives = true,
  bool addRepaintBoundaries = true,
  bool addSemanticIndexes = true,
  double? cacheExtent,
  DragStartBehavior dragStartBehavior = DragStartBehavior.start,
  ScrollViewKeyboardDismissBehavior keyboardDismissBehavior = ScrollViewKeyboardDismissBehavior.manual,
  String? restorationId,
  Clip clipBehavior = Clip.hardEdge,
}) : assert(itemBuilder != null),
     assert(separatorBuilder != null),
     assert(itemCount != null && itemCount >= 0),
     itemExtent = null,
     childrenDelegate = SliverChildBuilderDelegate(
       (BuildContext context, int index) {
         final int itemIndex = index ~/ 2;
         final Widget widget;
         if (index.isEven) {
           widget = itemBuilder(context, itemIndex);
         } else {
           widget = separatorBuilder(context, itemIndex);
           assert(() {
             if (widget == null) {
               throw FlutterError('separatorBuilder cannot return null.');
             }
             return true;
           }());
         }
         return widget;
       },
       childCount: _computeActualChildCount(itemCount),
       addAutomaticKeepAlives: addAutomaticKeepAlives,
       addRepaintBoundaries: addRepaintBoundaries,
       addSemanticIndexes: addSemanticIndexes,
       semanticIndexCallback: (Widget _, int index) {
         return index.isEven ? index ~/ 2 : null;
       },
     ),
     super(
       key: key,
       scrollDirection: scrollDirection,
       reverse: reverse,
       controller: controller,
       primary: primary,
       physics: physics,
       shrinkWrap: shrinkWrap,
       padding: padding,
       cacheExtent: cacheExtent,
       semanticChildCount: itemCount,
       dragStartBehavior: dragStartBehavior,
       keyboardDismissBehavior: keyboardDismissBehavior,
       restorationId: restorationId,
       clipBehavior: clipBehavior,
     );
     </code>
     </pre>
     
   #### ListView.separated 주요 속성
  - **padding** : children을 삽입할 공간 => final EdgeInsetsGeometry? padding;
  - **scrollerDirection** : 스크롤 방향 설정 속성 => final Axis scrollDirection;
  - **itemBuilder** : child들을 어떻게 배치할 지 정하는 속성 => required IndexedWidgetBuilder itemBuilder
  - **separatorBuilder** : 구분자를 어떻게 그릴지 정하는 속성 => required IndexedWidgetBuilder separatorBuilder
  - **itemCount** : child의 개수 => required int itemCount
  

  
  
  #### 4. ListView.custom : 사용자가 정의 가능


 
 
 
 
 
