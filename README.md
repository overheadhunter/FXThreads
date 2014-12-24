FXThreads
=========

Switching main and background threads in JavaFX made easy.

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
