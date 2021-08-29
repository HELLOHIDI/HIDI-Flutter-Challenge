# Image Widget

## Image Widget
  - 이미지를 표시하는 위젯
  - 지원되는 이미지 형식 : JPEG, PNG, GIF, 애니메이션 GIF, WebP, 애니메이션 WebP, BMP 및 WBMP
  
<pre>
<code>
const Image({
  Key? key,
  required this.image,
  this.frameBuilder,
  this.loadingBuilder,
  this.errorBuilder,
  this.semanticLabel,
  this.excludeFromSemantics = false,
  this.width,
  this.height,
  this.color,
  this.colorBlendMode,
  this.fit,
  this.alignment = Alignment.center,
  this.repeat = ImageRepeat.noRepeat,
  this.centerSlice,
  this.matchTextDirection = false,
  this.gaplessPlayback = false,
  this.isAntiAlias = false,
  this.filterQuality = FilterQuality.low,
}) : assert(image != null),
     assert(alignment != null),
     assert(repeat != null),
     assert(filterQuality != null),
     assert(matchTextDirection != null),
     assert(isAntiAlias != null),
     super(key: key);
</code>
</pre>

### Image 위젯의 주요 속성
  - width, height : 이미지의 가로, 세로 크기
  - fit : 원하는 공간에 이미지가 들어맞도록 하는 속성
  - alignment : 이미지 정렬
  - semanticLabel : 이미지를 설명하는 소개글

### Image 등록 방법
1. Image.asset() : 앱에 저장된 대상을 끌어와 이미지를 띄움 => 다른 버젼들을 저장해 pubspec.yaml 안에 나열하면 됨
2. Image.file() : 사용자 장치에서 이미지를 가져와서 띄움 
3. Image. memory() : 메모리에 저장된 이미지를 바이트 배열로 나타낼 때
4. Image.network() : URL에서 이미지를 가져와 띄움 => Flutter가 이미지 파일을 다운로드해서 캐시를 저장하고 화면에 띄움

### 예시 코드
  <pre>
  <code>
 import 'package:flutter/material.dart';
 import 'package:file/file.dart';

  void main() => runApp(MyApp());

  /// This is the main application widget.
  class MyApp extends StatelessWidget {
    static String _title = 'Flutter Code Sample';

    @override
    Widget build(BuildContext context) {
      return MaterialApp(
        title: _title,
        debugShowCheckedModeBanner: false,
        home: ImageWidget(),
      );
    }
  }

  class ImageWidget extends StatefulWidget {
    _ImageWidgetState createState() => _ImageWidgetState();
  }

  class _ImageWidgetState extends State<ImageWidget> {
    @override
    Widget build(BuildContext context) {
      return Scaffold(
        appBar: AppBar(),
        body: SafeArea(
          child: Padding(
            padding: const EdgeInsets.all(25.0),
            child: ListView(
              children: [
                Text(
                  "image asset 이용",
                  style: TextStyle(fontSize: 25),
                ),
                Image.asset(
                  'assets/IMG_0239.jpeg',
                  fit: BoxFit.cover,
                ),
                SizedBox(height: 2),
                Text(
                  "image network 이용",
                  style: TextStyle(fontSize: 25),
                ),
                Image.network(
                  'https://flutter.github.io/assets-for-api-docs/assets/widgets/owl.jpg',
                  fit: BoxFit.cover,
                ),
                SizedBox(height: 2),
                Text(
                  "image file 이용 - 추후 수정 예정",
                  style: TextStyle(fontSize: 25),
                ),
                SizedBox(height: 2),
                Text(
                  "image memory 이용 - 추후 수정 예정",
                  style: TextStyle(fontSize: 25),
                ),
                SizedBox(height: 2),
              ],
            ),
          ),
        ),
      );
    }
  }
  </code>
  </pre>
  
  
  ### 실행결과
  ![image](https://user-images.githubusercontent.com/54922625/131250001-c16c21a1-b263-4ea9-9c14-7ac7780d256f.png)

  
  
  
