# How to create states file template to save time.

In this tutorial we will learnt how to create any file template to avoid write reuseable code everytime.

Open Android Studio. Click File -> New -> Edit File Template.

Goto Files tab on that dialog and click on + button and add a name of the file whatever you want but keep in mind that add file extension and write this code in it.

````
abstract class ${states_name}States {}

class ${states_name}Initial extends ${states_name}States {}

class ${states_name}Loading extends ${states_name}States {}

class ${states_name}Success extends ${states_name}States {
  final ${states_name}Response response;
  ${states_name}Success(this.response);
}

class ${states_name}Error extends ${states_name}States {
  final String message;
  ${states_name}Error(this.message);
}
````
