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
       * Installing Provider package
         Go to  
