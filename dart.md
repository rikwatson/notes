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


```dart
int fib(int n) => (n > 2) ? (fib(n - 1) + fib(n - 2)) : 1;

void main() {
  print('fib(20) = ${fib(20)}');
}
```

