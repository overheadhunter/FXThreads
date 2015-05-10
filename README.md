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

## Usage

FXThreads is available via (JitPack)[https://jitpack.io/#totalvoidness/FXThreads/1.0]:

``` xml
<repository>
  <id>jitpack.io</id>
  <url>https://jitpack.io</url>
</repository>
<!-- ... -->
<dependency>
  <groupId>com.github.totalvoidness</groupId>
  <artifactId>FXThreads</artifactId>
  <version>1.0</version>
</dependency>
```

## License
Distributed under the MIT license. See the LICENSE file for more info.
