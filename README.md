# Horizontal Stepper
Horizontal stepper consist top and bottom type with buttons at the end. It holds the stepper validation state as well.

## Demo
<img src="https://github.com/khadkarajesh/stepper/blob/master/media/top_stepper.jpg" height="500px" width="300px" />     <img src="https://github.com/khadkarajesh/stepper/blob/master/media/bottom_stepper.jpg" height="500px" width="300px" />

## Usage

```dart

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: MyHomePage(
        title: "Demo App",
      ),
    );
  }
}

class MyHomePage extends StatefulWidget {
  MyHomePage({Key key, this.title}) : super(key: key);

  final String title;

  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.title),
      ),
      body: Padding(
        padding: const EdgeInsets.only(
          left: 16,
          right: 16,
        ),
        child: HorizontalStepper(
            steps: [
              HorizontalStep(
                title: "Step 1",
                widget: Center(
                  child: Text("Step 1"),
                ),
                state: HorizontalStepState.SELECTED,
                isValid: true,
              ),
              HorizontalStep(
                title: "Step 2",
                widget: Center(
                  child: Text("Step 2"),
                ),
                isValid: true,
              ),
              HorizontalStep(
                title: "Step 3",
                widget: Center(
                  child: Text("Step 3"),
                ),
                isValid: true,
              ),
              HorizontalStep(
                title: "Step 4",
                widget: Center(
                  child: Text("Step 4"),
                ),
                isValid: true,
              )
            ],
            selectedColor: const Color(0xFF4FE2C0),
            unSelectedColor: Colors.grey.shade400,
            leftBtnColor: const Color(0xffEA7F8B),
            rightBtnColor: const Color(0xFF4FE2C0),
            selectedOuterCircleColor: const Color(0xFF40A8F4),
            type: Type.TOP,
            circleRadius: 30,
            onComplete: () {
              print("completed");
            },
            textStyle: TextStyle(
              fontSize: 14,
              fontWeight: FontWeight.bold,
              decoration: null,
            )),
      ),
    );
  }
}

```

# Type

```dart

Type.TOP, Type.BOTTOM

```

# Validation
Allowing boolean value isValid ```dart true or false ``` disables the next button in stepper