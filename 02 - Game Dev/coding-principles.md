# Coding principles
___
### Pointers

```cpp
// POINTER: GO TO THAT ADDRESS FIRST, THEN ACCESS THE MEMBER THERE

MyVector->X = 5.0f;
// is exactly the same as:
(*MyVector).X = 5.0f;
```


**Declaring without assigning yet:**
```cpp
AMyActor* TargetActor;  // Just reserves space for an address (bytes that happen to be at that location) 
						// ⚠️ Reading/Writing crashes Program

// 🔧 Fix:
AMyActor* TargetActor = nullptr; // Reserved, explicitly pointing at nothing

// Check:
if (TargetActor) {
	TargetActor->DoSomething();
}
```

### Primitive types
```cpp
float X = 1.0f;   // correct
float X = 1.0;    // compiles but it's a double, implicit conversion
```

### Macros
```cpp
TEXT() // Macro, wraps string to ensure its stored as wide chars (2-byte UNI) instead of 1-byte ASCII
// without, strings are converted anyway (OVERHEAD)
```

### Classes
```cpp
// You never do this — UObjects can't be stack-allocated
AMyActor Actor;          // wrong, won't compile or will cause problems

// Always a pointer, always spawned through UE's system
AMyActor* Actor = SpawnActor<AMyActor>(...);
```

### Templates
```cpp
template<typename T>
T Add(T A, T B) {
    return A + B;
}

Add<int>(1, 2);       // compiler generates an int version
Add<float>(1.5f, 2.5f); // compiler generates a float version
```
## Concepts
___
- `C++` for systems and performance critical code, `Blueprint` for 

### Access specifiers
```cpp
public // accessible from anywhere
private // only within same class
protected // class and all subclasses
```

### Referencing
```cpp
void BadFunction(FVector Location) {  // Location is COPIED into the function
    Location.X = 999;  // modifies the copy, not the original
}

void GoodFunction(FVector& Location) { // & means "reference to the original"
    Location.X = 999;  // modifies the original
}

void ReadOnlyFunction(const FVector& Location) { // const ref — no copy, no modify
    // can read Location, can't modify it
}
```

