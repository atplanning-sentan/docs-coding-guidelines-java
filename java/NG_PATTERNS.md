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
