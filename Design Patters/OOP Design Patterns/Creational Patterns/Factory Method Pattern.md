# 🏭 Factory Method Pattern (Scala)

## What it is
Say you have multiple classes that extend a common trait and use override its method for different usages

Factory Method Design Pattern is a way to centralize how objects are created from each of those classes.
You would typically have a companion object that has a method which returns one of those objects (using pattern matching)
And instead of calling `new` everywhere for every one of those classes, you call a single method (often `apply` in a companion object).  

---

## Why it’s useful
- **Decoupling** → You simply call the trait it self which would then call the class depending on the companion object's pattern march.  
- **Single point of change** → add or update an implementation in one place.  
- **Consistency** → logging, retries, validation can all be applied in the factory.  
- **Testability** → easy to swap in fake implementations for tests.  

---

---
## Chain of how its called
Usage → Trait (Parser) → Companion Object (apply) → Classes (Objects are created from) (CsvParser/TsvParser/etc.)


## How it looks in Scala
```scala
sealed trait Parser { def parse(s: String): List[String] } // Common Trait

final class CsvParser extends Parser { 
  def parse(s: String) = s.split(",").toList // First class to extend trait
}
final class TsvParser extends Parser {
  def parse(s: String) = s.split("\t").toList // Second class to extend trait
}

object Parser { // Companion Object responsible for pattern matching different classes and creating objects from them
  def apply(kind: String): Parser = kind match {
    case "csv" => new CsvParser
    case "tsv" => new TsvParser
    case _     => throw new IllegalArgumentException("Unknown parser")
  }
}

// Usage
val p: Parser = Parser("csv")   // factory decides which kind of class to create object from
p.parse("a,b,c")





