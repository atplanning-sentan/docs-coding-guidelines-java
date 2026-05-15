# NGパターン集

## コレクションでnull返却
```java
return null;
```

## try-catchを条件分岐に使用
```java
try {
    service.find(...);
    return true;
} catch (NotFoundException e) {
    return false;
}
```

## フィールドを一時変数に使用
```java
private java.util.List<String> temp;

public String build(...) {
    this.temp = new java.util.ArrayList<>();
    ...
}
```
