# Coding principles
___
### Pointers
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