# SOLID Principles

- Single Responsibility
- Open / Closed
- Liskov Substitution
- Interface Segregation
- Dependency Inversion


Sandi Metz:
https://www.youtube.com/watch?v=8STtzjyDTTQ 


## 1. Single Responsibility (SRP)

“There should never be more than one reason for a class to change”

## 2. Open / Closed

“A module should be open for extension but closed for modification”

## 3. Liskov Substitution

“Subclasses should be substitutable for their base classes”

e.g.

```ruby
class Foo
end

class Fooish < Foo
end
```

Any place you use a Fooish you should be able to substitute in a Foo.

If you need to check is_kind_of?(Foo) then you’ve failed.

Note: mostly won’t use this in Ruby as you normally inherit from a Rails superclass instead of your own superclass.

## 4. Interface Segregation

“Many client specific interfaces are better than one general purpose interface”

## 5. Dependency Inversion

“Depend upon abstractions. Do not depend upon concretions”

In a statically-typed language (e.g. Java) you need to create interfaces to deal with instances of another class.

This principle is not a concern in a dynamically-typed language (e.g. Ruby) as you depend on the signature of the method you are calling when interacting with another class. Dynamically typed languages already obey this principle in the most extreme way possible.
