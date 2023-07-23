# fundamentals

A new Flutter project.

- created classes must extend either stateless or stateful widget
- Generic Tyoes
    - generic types are "flexible types" that "work together" with other types
        - List<string>
        - List<double>
        - State<DummyWidget>
- You can store widgets with variables:
    - ex. var dummy = DummyWidget();
      ![](../../Desktop/Screenshot 2023-06-27 at 2.22.53 PM.png)

Render Content Conditionally

```dart

Widget activeScreen = const StartScreen();

void switchScreen() {
  setState(() {
    activeScreen = const QuestionsScreen();
  });
}

...

child: activeScreen

```

- this is how you can conveniently use variables for widgets

Lifting State up
![](../../Desktop/Screenshot 2023-06-27 at 6.16.48 PM.png)
![](../../Desktop/Screenshot 2023-06-27 at 6.20.50 PM.png)

ex

```dart

Widget activeScreen = const StartScreen(swithcScreen);

void switchScreen() {
  setState(() {
    activeScreen = const QuestionsScreen();
  });
}


```

ex. of function calls in widgets

`onPressed: () {startQuiz();}`
-or-
`onPressed: startQuiz`

init state
![](../../Desktop/Screenshot 2023-06-27 at 7.15.52 PM.png)

Deep Dive: FLutter's (Stateful) Widget Lifecycle
Every FLutter Widget has built-in lifecycle" A collection of methods that are automatically
executed by flutter(at certain points of time)

There are three extremely important(stateful) widget lifecycle methods you should be aware of:

- `iitState()`: Executed by flutter when the StatefulWidget's State object is initialized
- `build()`: Executed by Flutter when the Widget is built for the first time AND
after the `setState()` is called
- `dispose()`: Executed by Flutter right before the Widget will be deleted(e.g. because it was displayed conditionally)
