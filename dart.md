# Dart & Flutter

## Macos installation

```bash
brew tap dart-lang/dart
brew install dart --with-content-shell --with-dartium
```

## Updating

```bash
brew update
brew upgrade dart
brew cleanup dart
```

# Flutter

See [here](https://flutter.io/setup-macos/) to install.

```bash
git clone -b alpha https://github.com/flutter/flutter.git
export PATH=`pwd`/flutter/bin:$PATH
flutter doctor
```


```dart
int fib(int n) => (n > 2) ? (fib(n - 1) + fib(n - 2)) : 1;

void main() {
  print('fib(20) = ${fib(20)}');
}
```

https://www.youtube.com/watch?v=OLjyCy-7U2U

http://www.newthinktank.com/2015/09/learn-dart-one-video/

A two part Flutter overview:

 * [One](https://medium.com/dartlang/zero-to-one-with-flutter-43b13fd7b354)
 * [Two](https://medium.com/dartlang/zero-to-one-with-flutter-part-two-5aa2f06655cb)