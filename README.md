FXThreads
=========

Switching main and background threads in JavaFX made easy.

This project consists of a single class, thus the easiest way of integrating it is by copying it to your project and maybe rename the package.

## Example 1
``` java
// get some string from a remote server:
Future<String> futureBookName = runOnBackgroundThread(restResource::getBookName);

// when done, update text label:
runOnMainThreadWhenFinished(futureBookName, (bookName) -> {
  myLabel.setText(bookName);
});
```

## Example 2
``` java
// get some string from a remote server:
Future<String> futureBookName = runOnBackgroundThread(restResource::getBookName);

// when done, update text label:
runOnMainThreadWhenFinished(futureBookName, (bookName) -> {
  myLabel.setText(bookName);
}, (exception) -> {
  myLabel.setText("An exception occured: " + exception.getMessage());
});
```

## License
Distributed under the MIT license. See the LICENSE file for more info.
