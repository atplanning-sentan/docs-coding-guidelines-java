# OKパターン集

## コレクション返却は空コレクション
```java
return java.util.Collections.emptyList();
```

## Optionalで「無い」を表現
```java
public java.util.Optional<String> findName(...) {
    if (...) {
        return java.util.Optional.of(name);
    }
    return java.util.Optional.empty();
}
```

## try-with-resources
```java
try (var in = openStream()) {
    return read(in);
}
```
