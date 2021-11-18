
### Video player in Flutter using Chewie and Getx

### Introduction

The default flutter video_player limits the user when he/she wants to perform an action to a video. Chewie is an Application Programming Interface that adds more functionality to the default flutter video player. Some of these functions include are like the addition of play controls to the video player.
The default flutter video_player limits the user when they want to perform an action to a video. Chewie is an Application Programming Interface that adds more functionality to the default flutter video player. Some of these functions include are like the addition of play controls to the video player.

In this article, we're going to build a video player using Dart and Flutter.

@@ -74,7 +74,7 @@ Widget build(BuildContext context) {
```

As you see, we have a very simple screen with an `appbar `, which will have the title of our player, and a `Scaffold`. The scaffold will contain the background image of our video player and two rows: one with the "Play" button on top, and another one for showing the title and URL of the selected resource.
As you see, we have a very simple screen with an `appbar `, which will have the title of our player, and a `Scaffold`. The Scaffold will contain the background image of our video player and two rows: one with the "Play" button on top, and another one for showing the title and URL of the selected resource.

The first row is an Align widget:

@@ -166,7 +166,7 @@ Container build(BuildContext context) {
```

The `Row` contains two buttons: one for playing and another one for stepping backward in the video (this is to skip intros and similar stuff).
The Row contains two buttons: one for playing and another one for stepping backward in the video (this is to skip intros and similar stuff).

We use two Expanded widgets. The first one lets us add a border-radius to our container with a circular shape, and the second one lets us add more padding on the top and on the bottom of our video player.

We're going to use `Padding` during the whole screen, but on this row, we need it in both directions because we'll have one button that stretches across all its width (the "PLAY" one) and another that has a smaller width (the "STEP_BACKWARD" one).
Now, let's see how we'll build the elements on this row. First of all, we have to create a button with some text inside it:
```dart
Widget buildButton(String title, BuildContext context) { 
 return new Container( 
    height: 50.0, padding: const EdgeInsets.only(top: 5.0),
     decoration: new BoxDecoration( color: Colors.white, ),
      child: new Text( title, style: const TextStyle(fontWeight: FontWeight.bold, fontSize: 20.0), 
      ), 
      ); 
      }
```
We use a Container to create our button with a height of 50dp and top padding of 5dp.
Next, we add a `BoxDecoration` to apply a white background with the same height and width as our container, and finally, we get the text inside the button. In this case, it is just some random string I typed in, but normally you would use an `IconButton` to get the correct icon.
Finally, we use the `buildButton` method that receives as a parameter the string that should be inside our button, and then it returns the built button (a Container).
We do almost the same thing to build the other button:
```dart
Widget buildButton(String title, BuildContext context) { 
 return new Container(
    height: 50.0, padding: const EdgeInsets.only(top: 5.0), decoration: new BoxDecoration( 
      color: Colors.white, 
      ), 
      child: new Text( title, style: const TextStyle(fontWeight: FontWeight.bold, fontSize: 20.0), 
      ),
 ); 
}
```
This time, we only have to modify the text a little bit. The "STEP_BACKWARD" string should appear in blue, so we add a second parameter called `color` with the value `Colors. blue`.
Almost done! We just have to update our main method to show the video player:
```dart
void main() { 
 runApp(new VideoPlayerApp());
}
```
We will instantiate the `VideoPlayerApp` in the main method, and then we create a new instance of it (using our video URL) to start playing.
Now you can show some videos to your friends!
Widgets used in this example:
```dart
Widget buildButton(String title, BuildContext context) { 
 return new Container( 
   height: 50.0, padding: const EdgeInsets.only(top: 5.0), decoration: new BoxDecoration( 
     color: Colors.white, ),
      child: new Text( title, style: const TextStyle(fontWeight: FontWeight.bold, fontSize: 20.0),
   ), 
 ); 
}
Widget buildButton(String title, BuildContext context, [Color color]) { 
 return new Container(
   height: 50.0, padding: const EdgeInsets.only(top: 5.0), decoration: new BoxDecoration( color: color, ),
    child: new Text( title,
     style: const TextStyle(fontWeight: FontWeight.bold, fontSize: 20.0),
    ), 
 ); 
}
```
I hope you enjoyed this article and that it helps you build your next app using Flutter.
### Conclusion
If you would like to see some other widgets, let us know in the comments! And of course, if you liked this article and want more content like this, don't forget to reach out to GitHub @kanoinikita
***ARTICLE END***
Thanks for reading my articles
