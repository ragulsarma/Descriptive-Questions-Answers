# Descriptive Questions

#### 1.Can we nest the Scaffold widget? Why or Why not?
  No, We should not nest scaffold widget. Scaffold was designed to be the single top level container for a MaterialApp and it's typically not necessary to nest scaffolds. 
     but at the same time, nesting widgets deeply is recommended in Flutter.
     Widgets are lightweight objects optimized specifically to create and destroy tons of them every frame.

#### 2.How to reduce the rebuilding of the widget?
(i) Wrap it as an independent Widget in another Stateful class.
     One of the easiest ways to avoid unwanted reBuilds that are caused usually by calling setState() in order to update only a specific Widget and not refreshing the whole page, is to cut that part of your code and  wrap it as an independent Widget in another Stateful class.
      (ii) Flutter also has ValueListenableBuilder<T> class . 
       It allows you to rebuild only some of the widgets necessary for your purpose and skip the expensive widgets.
     (iii) Also we can mention widget as const widget. 
       Use const constructors whenever possible when building your own widgets or using Flutter widgets. This helps Flutter to rebuild only widgets that should be updated.
        const reduces the required work for the Garbage Collector.

#### 3.How can I access platform(iOS or Android) specific code from Flutter?
To access IOS or Android platform from flutter we have to use Method Channel concept.
    Flutter dart code sends messages to its host(Android or IOS) over a platform channel.
    Host(Android or IOS)  listens on the platform channel and receives the message. It then calls into any number of platform-specific APIs—using the native programming language—and sends a response back to the client (Flutter dart code).
    The host listens on the platform channel and receives the message. It then uses any platform-specific APIs using the native programming language and sends back a response to the Flutter portion of the app. 
    Messages are passed between the Flutter Code(UI) and host (platform) using platform channels. Messages and responses are passed asynchronously and the user interface remains responsive.
       If required, method calls can also be sent in the reverse direction, with the Android/IOS platform acting as client and method implemented in Dart.

#### 4.What is BuildContext? What is its importance?
 When we develop flutter applications we need to track and find widgets on the widget tree so in order solve this situation we have a BuildContext.
       basically it's a locator that is used to track each widget in a tree and locate them and their position in the tree.
       Context -> is an instance of build context it is passed to the builder of a widget in order to let it know where it is inside widget tree. 