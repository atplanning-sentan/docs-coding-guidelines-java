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

## BigDecimal（誤差が許されない計算）
```java
var rate = new java.math.BigDecimal("0.07");
return java.math.BigDecimal.ONE.subtract(rate);
```
