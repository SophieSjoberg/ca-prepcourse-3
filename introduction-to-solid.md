##SOLID Principles with ruby examples
S.O.L.I.D is an acronym for the first five object-oriented design(OOD) principles. 
These principles, when combined together, make it easy for a programmer to develop software that are easy to maintain and extend. They also make it easy for developers to avoid code smells, easily refactor code, and are also a part of the agile or adaptive software development.

###Single responsibility principle - SRP
####A class should have only a single responsibility.

Every class should have a single responsibility, and that responsibility should be entirely encapsulated. All its services should be narrowly aligned with that responsibility, this embrace the high cohesion.

###Open/closed principle - OCP
####Software entities should be open for extension, but closed for modification. 
An entity can allow its behaviour to be extended without modifying its source code.

###Liskov substitution principle - LSP
####Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program.

It states that, in a computer program, if S is a subtype of T, then objects of type T may be replaced with objects of type S (i.e., objects of type S may substitute objects of type T) without altering any of the desirable properties of that program (correctness, task performed, etc.)

###Interface segregation principle - ISP 
####Many client-specific interfaces are better than one general-purpose interface.

States that no client should be forced to depend on methods it does not use. ISP splits interfaces which are very large into smaller and more specific ones so that clients will only have to know about the methods that are of interest to them. Such shrunken interfaces are also called role interfaces. ISP is intended to keep a system decoupled and thus easier to refactor, change, and redeploy.

###Dependency inversion principle - DIP
####Abstractions should not depend upon details. Details should depend upon abstractions.

Refers to a specific form of decoupling software modules. When following this principle, the conventional dependency relationships established from high-level, policy-setting modules to low-level, dependency modules are inverted (i.e. reversed), thus rendering high-level modules independent of the low-level module implementation details.


```ruby
class Report
  def body
     generate_reporty_stuff
  end

  def print
     JSONFormatter.new.format(body)
  end
end

class JSONFormatter
  def format(body)
     ...
  end
end
```
