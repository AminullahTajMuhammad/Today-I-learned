# Playing with AppBar in Flutter

Here is the full code and its output
````Dart
AppBar(
  title: Text("Hello Appbar"),
  leading: GestureDetector(
    onTap: () {},
    child: Icon(
      Icons.menu,
    ),
  ),
  actions: <Widget>[
    Padding(
      padding: EdgeInsets.only(right: 20.0),
      child: GestureDetector(
        onTap: () {},
          child: Icon(
            Icons.search
          ),
        ),
     ),

     Padding(
       padding: EdgeInsets.only(right: 20.0),
       child: GestureDetector(
         onTap: () {},
           child: Icon(
             Icons.more_vert
           ),
       ),
    ),
  ],

  actionsIconTheme: IconThemeData(
    color: Colors.black,
      size: 30.0
  ),
),
`````
## Here is the output

![Image](https://raw.githubusercontent.com/AminullahTajMuhammad/Today-I-learned/master/flutter/Icons%20Theme.png)
