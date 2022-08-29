# How to create cubit file template to save time.

In this tutoial we will learnt how to create any file template to avoid write reuseable code everytime.

Open Android Studio. Click File -> New -> Edit File Template.

Goto Files tab on that dialog and click on + button and add a name of the file whatever you want but keep in mind that add file extension and write this code in it.

````
import 'package:bloc/bloc.dart';
import 'package:dartz/dartz.dart';

class ${cubit_name}Cubit extends Cubit<${states_name}States> {
  ${cubit_name}Cubit(this.appRepository) : super(${states_name}Initial());
  AppRepository appRepository;
  
  void function() async {
    emit(${states_name}Loading());
    final Either<AppError, LoginResponse> eitherResponse = await appRepository.function();
    emit(
      eitherResponse.fold((left) {
        var message = getErrorMessage(left.appErrorType);
        return ${states_name}Error(message);
      }, (right) {
        return ${states_name}Success(right);
      },),
    );
  }
}
````
