# No boolean literal compare

![Has auto-fix](https://img.shields.io/badge/-has%20auto--fix-success)


## Rule id
no-boolean-literal-compare

## Description
Warns on comparison to a boolean literal, as in `x == true`. Comparing boolean values to boolean literals is unnecessary, as those expressions will result in booleans too. Just use the boolean values directly or negate them.

### Unnecessary comparing
Bad:
```dart
  var b = x == true;
  var c = x != true;

  if (x == true) {
    ...
  }

  if (x != false) {
    ...
  }

  if (x?.isNotEmpty == true) {
    ...
  }
```

Good:
```dart
  var b = x;
  var c = !x;

  if (x) {
    ...
  }

  if (!x) {
    ...
  }

  if (x?.isNotEmpty ?? false) {
    ...
  }
```
