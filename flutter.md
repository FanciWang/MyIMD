# Flutter

### 基本介绍

Flutter是Google发布的一个用于创建跨平台、高性能移动应用的框架。开发者使用Dart语言开发App，相同代码可以在Android和iOS系统运行，提供了丰富的组件和接口，使用Native引擎渲染视图。

目前Flutter默认支持iOS、Android、Fuchsia三个移动平台。但也可支持Web开发（Flutter for web）和PC开发，可谓是智能移动开发的“万金油”。

#### Dart语言

Dart 是一个为全平台构建快速应用的客户端优化的编程语言。Dart语言为基于事件驱动的用户界面提供成熟且完备的异步-等待体系。专为构建用户界面优化，包含了用于展开集合的展开操作符，以及集合内的条件语句用于为每个平台定制UI。Dart语言支持AOT（Ahead of time）即 “提前编译”，保证了Dart语言可以提供流畅、高保真的UI体验。

#### 跨平台自绘引擎——Skia

Flutter使用自己的高性能渲染引擎来绘制widget，而不使用操作系统的原生控件，不依赖于操作系统。这样不仅可以保证在Android和iOS上UI的一致性，而且也可以避免对原生控件依赖而带来的限制及高昂的维护成本。

Flutter使用Skia作为其2D渲染引擎，Skia是Google的一个2D图形处理函数库，包含字型、坐标转换，以及点阵图都有高效能且简洁的表现，Skia是跨平台的，并提供了非常友好的API，为开发者提供最大程度的便利。

目前Flutter默认支持iOS、Android、Fuchsia（Google新的自研操作系统）三个移动平台。但Flutter亦可支持Web开发（Flutter for web）和PC开发，本书的示例和介绍主要是基于iOS和Android平台的，其它平台读者可以自行了解。

#### 框架结构

Framework：Dart语言，它使用自底向上的方法实现了一套基础库，底下两层（Foundation和Animation、Painting、Gestures）在Google的一些视频中被合并为一个dart UI层，对应的是Flutter中的`dart:ui`包，它是Flutter引擎暴露的底层UI库，提供动画、手势及绘制能力。Rendering层，最核心的部分，这一层是一个抽象的布局层，它依赖于dart UI层，Rendering层会构建一个UI树，当UI树有变化时，会计算出有变化的部分，然后更新UI树，最终将UI树绘制到屏幕上。Widgets层是Flutter提供的的一套基础组件库，在基础组件库之上，Flutter还提供了 Material 和Cupertino两种视觉风格的组件库。

Engine：C++语言实现，其中包括了 Skia引擎、Dart运行时、文字排版引擎等。在代码调用 `dart:ui`库时，调用最终会走到Engine层，然后实现真正的绘制逻辑。

### 优势一：快速开发

Flutter使用毫秒级的热重载，帮助开发者快速地进行测试、构建UI、添加功能并更快地修复错误。在iOS和Android模拟器或真机上可以在亚秒内重载，并且不会丢失状态。Flutter通过将更新的源代码文件注入到正在运行的 Dart 虚拟机（VM）来实现热重载。在虚拟机使用新的字段和函数更新类之后， Flutter 框架会自动重新构建 widget 树，以便开发者可以快速查看更改的效果。

### 优势二：富有表现力和灵活的UI

Flutter聚焦原生体验，内置美丽的Material Design和Cupertino（iOS风格）widget、丰富的motion API、平滑而自然的滑动效果和平台感知，同时允许开发者自定义分层架构，从而实现富有表现力和灵活的UI设计。

### 优势三：功能强大

使用Flutter的现代、响应式框架和一系列基础widget，轻松构建您的用户界面，以达到和iOS和Android原生应用一样的性能。