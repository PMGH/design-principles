# Design Principles

Aim: save development time by making your code robust and easier to test, maintain and extend.

---

## Table of Contents

- [Don't Repeat Yourself (DRY)](#dry)
- [Keep It Simple, Stupid (KISS)](#kiss)
- [SOLID](#solid)
- [You Ain't Gonna Need It (YAGNI)](#yagni)

---

## DRY

> "Don't Repeat Yourself"

https://dzone.com/articles/software-design-principles-dry-and-kiss

> "Every piece of knowledge or logic must have a single, unambiguous representation within a system."

Achieved by splitting the system up into small pieces. E.g. Classes and reusable modules.

Less code is good: It saves time and effort, is easy to maintain, and also reduces the chances of bugs.

---

## KISS

> "Keep It Simple, Stupid"

https://dzone.com/articles/software-design-principles-dry-and-kiss

> Keep the code simple and clear, making it easy to understand. Small methods (no more than 40-50 lines) that are responsible for solving one thing.

---

## SOLID

```
Single Responsibility
Open / Closed
Liskov Substitution
Interface Segregation
Dependency Inversion
```

**Sandi Metz:** https://www.youtube.com/watch?v=8STtzjyDTTQ 

### 1. Single Responsibility (SRP)

> “There should never be more than one reason for a class to change”

### 2. Open / Closed

> “A module should be open for extension but closed for modification”

### 3. Liskov Substitution

> “Subclasses should be substitutable for their base classes”

e.g.

```ruby
class Foo
end

class Fooish < Foo
end
```

Any place you use a Fooish you should be able to substitute in a Foo.

If you need to check is_kind_of?(Foo) then you’ve failed - liskov code smell.

Note: mostly won’t use this in Ruby as you normally inherit from a Rails superclass instead of your own superclass.

### 4. Interface Segregation

> “Many client specific interfaces are better than one general purpose interface”

### 5. Dependency Inversion

> “Depend upon abstractions. Do not depend upon concretions”

In a statically-typed language (e.g. Java) you need to create interfaces to deal with instances of another class.

This principle is not a concern in a dynamically-typed language (e.g. Ruby) as you depend on the signature of the method you are calling when interacting with another class. Dynamically typed languages already obey this principle in the most extreme way possible.

---

**In other words (Steve Freeman & Nat Pryce):**

- loosely coupled (inject dependencies)
- highly cohesive (class about one thing only i.e Single Repsponsibility)
- easily composable
- context independent (new behaviour from existing classes)


**Design is all about dependencies.**

- If you refer to something then you depend on it.
- When your dependencies change you must change. Rigid, fragile, immobile and viscous code.
- If you are entangled with another object and it changes then you have to change.

**Some questions to ask yourself**

- Is it DRY?
- Does it have one responsibility?
- Does everything in it change at the same rate?
- Does it depend on things that change less often than it does?

---

## YAGNI

> "You Ain't Gonna Need It"

https://deviq.com/yagni/


> “Always implement things when you actually need them, never when you just foresee that you may need them.”

A key principle of extreme programming. Wait for the customer to actually ask for it before implementing it.

---

**Resources:**

- DRY: https://dzone.com/articles/software-design-principles-dry-and-kiss
- KISS: https://dzone.com/articles/software-design-principles-dry-and-kiss
- SOLID: https://www.youtube.com/watch?v=8STtzjyDTTQ
- YAGNI: https://deviq.com/yagni/

---