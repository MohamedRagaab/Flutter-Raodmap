# Flutter-Roadmap

## Content

* Programming
  * Dart 
  
* IDE
  * Android Studio
  * VScode

* UI
  * Widgets
     * Stateless Widget
     * Statefull Widget
     * Accessibility
     * Inherited Widget
        * Theming
        * Localization
  * Assets
     * Fonts
     * Images
     * SVG
     * Audios/Videos
     
* Static User Interface
   * View
      * Text
      * Buttons
      * Images etc
   * ViewGroup
      * Container
      * Row
      * Column
      * Stack
      * Expanded
      * ConstrainedBox
      
* Dynamic User Interface
   * ListView
   * GridView
   * ExpansionTitle

* Async Programming
   * [Isolates and Event loops](#Isolates-and-Event-loops)
   * Futures
   * Streams
   * Async Await
   * Generators
   * URl Launcher
   * Get Data From API
   * API Model
   * Timer
 
* [Lifecycle](#Lifecycle)
   * App Lifecycle 
   * [Widget Lifecycle](#Widget-Lifecycle)
* Animation
   * Animated Widget
   * Animated Builder
   * Animation Controller
   * Curved Animation
   * Hero
   * Opacity
   
* Storage
   * Shared Prefrences
   * File System
   * SqLite

* 3rd Party Libraries
   * http
   * dio
   * get_it
   * cached_network_image
   * font_awesome_flutter
   * SQFLite
   * flutter_webview_plugin
   * rxdart
   * bloc_pattern

* Behavior Components
   * Permission
   * Local Notification
   * Push Notification
   * Download Manager
   * Media Playback
   * Perefrence
  
* State Managment
   * setState
   * [Provider](#Provider)
   * Redux
   * BLoC
   * MobX
  
* Quiality Assurance
   * Firebase
      * Crashlytics
      * App distribution
      * Analytics
   * Google Play beta tests
   * TestFlight
   * App center
   
* Version Control
   * Git
   * GitHub

* Firebase
   * Firebase Auth
   * Firebase Database
   * Firebase Storage
   * Firebase Messaging
* Native Integration
   * Android Studio
   * Java/Kotlin
   * App Signing
   * Google Play Store
   * Xcode
   * Swift/Objective-C
   * Apple Certification
   * AppStore
 
## State Managment
### Provider
#### Advantages
   * Using provider help you when you need to send a state from widget to another instead of using constructors.
   * and also increase the app performance because if you nead to change a state value (variable) you need to change to
        statefull widget and use setState which will call the build method which will rebuild the entire screen ui to just
        change the state value and this is a bad performance, but we can use Provider to solve this issue.
##### USing Provider
   let we need to do a simple app which counts number starting from zero with floating action button, here are some steps we should follow:
   * Installing Provider package 
     Go to https://pub.dev/packages/provider/install and install the package
   * Get the dependcy
  
<div align='center'>
<img height="150px" src="https://user-images.githubusercontent.com/38363762/116162007-29000e80-a6f5-11eb-9d80-0dfdaf509e7d.png">
<hr/>
</div>

   * Import the Package in the right file
  
<div align='center'>
<img height="150px" src="https://user-images.githubusercontent.com/38363762/116162295-c6f3d900-a6f5-11eb-9c51-49abf8066029.png">
<hr/>
</div>

   * Wrap the root widget with ChangeNotifierProvider 
   
<div align='center'>
<img height="300px" src="https://user-images.githubusercontent.com/38363762/116162461-20f49e80-a6f6-11eb-8991-ef6a877f450b.png">
<hr/>
</div>

   * Creat your provider class which contain the states(Variables) and the methods ou will use and mixing it with ChangeNotifier
  
<div align='center'>
<img height="300px" src="https://user-images.githubusercontent.com/38363762/116162662-8c3e7080-a6f6-11eb-9140-7079eb488722.png">
<hr/>
</div>

   * import your class provider in the file which you want to use the methods and variables you created 
   
<div align='center'>
<img height="250px" src="https://user-images.githubusercontent.com/38363762/116163357-e7bd2e00-a6f7-11eb-925c-832f36ccc7ce.png">
<hr/>
</div>

   * Get your state in the right place
   
<div align='center'>
<img height="300px" src="https://user-images.githubusercontent.com/38363762/116163061-51890800-a6f7-11eb-8bac-c692d0acc600.png">
<hr/>
</div>

## Async Programming
### Isolates and Event loops
  If you are waiting for a task to complete for example, your app is downloading a video so it is not good to block the app until this   task finished but we can use a method from the fowllowing
  * Synchronous 
    It means that the compiler must wait until this part of the code finished.  
  * Asnchronous
    It means that the compiler must not wait until this part of the code finished but it is running in a different thread.  
    * Isolate 
     our main program run in isolate space but we can create another isolate to run a part of the code or function inside it and the last isolate it is considerd as son of the father isolate (main isolate) and those isolates can communicate with each other by sending messages.
      * Using Isolate
        <br>first we should import dart.isolate library 
        <br>and we can use isolate.spawn method which accept two parameters, first one is a function with a parameter which will take much time(this function must be in the top level and doesn't belong to any class or we can create a class and make the function static so we can access it without object) and seconed one is a message parameter.

<div align='center'>
<img height="300px" src="https://user-images.githubusercontent.com/38363762/117896140-2ccc8d00-b2c0-11eb-86cf-ab8533f52b85.png">
<hr/>
</div>

<div align='center'>
<img height="500px" src="https://user-images.githubusercontent.com/38363762/117896167-3d7d0300-b2c0-11eb-8f46-c8d4c98382c8.png">
<hr/>
</div>

<div>
   <br>the output of the program is:    
   <br>flutter: main isolate
   <br>flutter: begin
   <br>flutter: end 
   <br>which means the compiler will not wait until the blockApp function completion but it will run the seconed line then returned to the function.
 <br>
</div>
<div>
   <br>Note we can import foundation.dart library and replace the isolate.spawn method with compute and we will have the same results
</div>
<div align='center'>
<img height="500px" src="https://user-images.githubusercontent.com/38363762/118033996-c13efa00-b369-11eb-93e4-2226771132b1.png">
<hr/>
</div>


## Lifecycle
### Widget LifeCycle
  * Stateless Widget
    <br>A stateless widget can only be drawn once when the Widget is loaded/built.
  * StateFull Widget
    <br>The Stateful widget is mutable that's why it can be drawn multiple times within its lifetime.
    
  * There are multiple methods that recall the build method:
    * initState() => This is the first method called when a stateful widget is created after the class constructor.
    * didUpdateWidet() 
  <br>If the parent widget change configuration and has to rebuild this widget. But it's being rebuilt with the same runtimeType, then didUpdateWidget() method is called. The framework updates the widget property of this state object to refer to the new widget and then call this method with the previous widget as an argument.
    * setState()
  <br>This method is called from the framework and the developer. We can change the internal state of a State object and make the change in a function that you pass to setState().
    * A stateful widget has the following lifecycle stages:
    
<div align='center'>
<img height="600px" src="https://user-images.githubusercontent.com/38363762/116098098-1234ca00-a6ab-11eb-837d-466775527e9d.PNG">
<hr/>
</div>
   
  * dispose() 
<br>This is called when the State object is removed permanently.
    
    
