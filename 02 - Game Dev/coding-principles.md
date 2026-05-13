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
