# Version 1.0

- [German](https://learn.microsoft.com/de-de/dotnet/csharp/whats-new/csharp-version-history?source=recommendations#c-version-10-1)
- [Englisch](https://learn.microsoft.com/en-us/dotnet/csharp/whats-new/csharp-version-history?source=recommendations#c-version-10-1)

## [Struct](https://learn.microsoft.com/de-de/dotnet/csharp/language-reference/builtin-types/struct)

## [Interface](https://learn.microsoft.com/de-de/dotnet/csharp/fundamentals/types/interfaces)


### IEnumerable

Ermöglicht das Iterieren durch ein Objekt, was ohne IEnumerable nicht möglich wäre (Siehe 1).
Zudem ermöglicht es die Verwendung von Funktionen wie z.B.: First()(Siehe 2)

## [Delegate](https://learn.microsoft.com/de-de/dotnet/csharp/delegates-overview)

Delegate sind [Referenztypen](/Basics/#referenztyp)

## fixed

Fixed verhindert das der Garbage Collector eine bewegliche Variable ordnet, und deklariert einen Zeiger auf diese Variable.

## lock

## Operatoren (operators)

## Ausdrücke (expressions)

### Interpolierte Zeichenfolgenausdrücke (Interpolated string expressions)

```csharp
var r = 2.3;
var message = $"The area of a circle with radius {r} is {Math.PI * r * r:F3}.";
Console.WriteLine(message);
// Output:
// The area of a circle with radius 2.3 is 16.619.
```

### Lambdaausdrücke (Lambda expressions)

```csharp
int[] numbers = { 2, 3, 4, 5 };
var maximumSquare = numbers.Max(x => x * x);
Console.WriteLine(maximumSquare);
// Output:
// 25
```

### Abfrageausdrücke (Query expressions)

```csharp
var scores = new[] { 90, 97, 78, 68, 85 };
IEnumerable<int> highScoresQuery =
    from score in scores
    where score > 80
    orderby score descending
    select score;
Console.WriteLine(string.Join(" ", highScoresQuery));
// Output:
// 97 90 85
```
