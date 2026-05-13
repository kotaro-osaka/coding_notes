# Coding principles
___
### Pointers
```cpp
AMyActor* TargetActor; // ⚠️ Just reserves space for an address (holds bytes that happen to be at that location)

// 🔧 Fix:
AMyActor
```