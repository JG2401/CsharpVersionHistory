# Version 2

## [Generics](https://learn.microsoft.com/de-de/dotnet/csharp/fundamentals/types/generics)

Nicht definiert für einen bestimmten Datentyp. Verwendbar für Klassen, Methoden, Felder, etc.

## [Partial](https://learn.microsoft.com/de-de/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods#partial-classes)

- Ohne Verwendung von „partial“ tritt folgender Fehler auf wenn zwei gleichnamige Klassen in einem Namespace enthalten sind: Der Namespace enthält bereits eine Definition für „“.
- Anwendbar für Klassen, Strukturen, Interfaces oder Methoden.
- Alle Teile müssen das Schlüsselwort „partial“ und die gleiche Zugriffsebene beinhalten.
- Wenn ein Teil abstrakt definiert wird oder von einer Klasse erbt wirkt sich das auf alle Teile aus. Attribute oder Vererbungen werden zusammengefasst.

### Methoden

Partielle Methoden können nur in partiellen Klassen verwendet werden. Dafür muss die Methode in einem Teil deklariert werden.

```csharp
internal partial class Employee
{
    partial void DoSomething();
}
```

In einem anderen Teil kann die Methode initialisiert werden.

```csharp
internal partial class Employee
{
    partial void DoSomething()
    {
 
    }
}
```

> [!WARNING]  
> Eine partielle Methode darf nicht über mehrere implementierte Deklarationen verfügen. → Es darf nur eine Deklaration und eine Initialisierung in der gesamten partiellen Klasse.

## [Sealed](https://learn.microsoft.com/de-de/dotnet/csharp/language-reference/keywords/sealed)

- Der Modifizierer „sealed“ verhindert, dass von dieser Klasse geerbt werden kann ??????????
- Anwendbar für Klassen, Methoden und Eigenschaften
- Der Modifizierer sealed muss immer mit override verwendet werden, wenn er auf eine Methode oder Eigenschaft angewendet wird.
- Fehlermeldung beim Versuch von einer sealed Klasse zu erben: Vom versiegelten Typ „“ kann nicht abgeleitet werden.

## Extern

## [Nullable](https://learn.microsoft.com/de-de/dotnet/csharp/language-reference/builtin-types/nullable-value-types)

Nullable ermöglicht Werttypen einen zusätzlichen Wert „null“. Das ist über „Nullable<Werttyp>“ oder „Werttyp?“ möglich.

### Beispiele

#### Deklaration

```csharp
Nullable<int> NullableIntV1 = null;
int? NullableIntV2 = null;
int?[] NullableIntV3 = new int?[1];
```

#### Prüfung auf null

```csharp
//HasValue
if (value.HasValue)
 
//is
if (value is int valueOfCount)
```

#### Ausgabe der Werte

```csharp
Console.WriteLine(value);
Console.WriteLine(value.Value); //Fehler wenn value == null
```

#### Konvertierung in Ursprungstyp

```csharp
int intValue = value ?? 0; //Wenn value == null -> intValue = 0
int intValue2 = value.GetValueOrDefault(); //Wenn value == null -> intValue = 0
int intValue3 = (int)value; // Fehler wenn value == null
```

## [Is](https://learn.microsoft.com/de-de/dotnet/csharp/language-reference/operators/is)

### Beschreibung

Is ist geeignet für Prüfung nach dem Typ, Null oder um ein bestimmtes Muster abzugleichen.

### Beispiele

```csharp
int? count = 0;
DateTime dt = DateTime.Now;
 
if (count is null)
    Console.WriteLine("count is null");
 
if (count is not null)
    Console.WriteLine("count is not null");
 
if (count is int valueOfCount)
    Console.WriteLine($"count is {valueOfCount}");
 
if (dt is { Day: 17, Month: 04, Year: 2023 })
{
    Console.WriteLine("dt is true");
}
```

weiteres Beispiel in [typeof](#typeof)

## As

### Beschreibung

- Konvertiert in einen anderen Datentyp.
- Unterschied zu Cast: Wenn die Konvertierung nicht möglich ist → kein Fehler (Rückgabewert ist NULL)

## Cast

### Beschreibung

- Konvertiert in einen anderen Datentyp.
- Unterschied zu As: Wenn die Konvertierung nicht möglich ist → Fehler

## [Typeof](https://learn.microsoft.com/de-de/dotnet/csharp/language-reference/operators/type-testing-and-cast#typeof-operator)

### Beschreibung

Dient zur Prüfung um welchen Objekttyp es sich handelt.

```csharp
public class Animal { }
public class Giraffe : Animal { }
 
object b = new Giraffe();
Console.WriteLine($"is Animal:      {b is Animal}");                    // output: True
Console.WriteLine($"typeof Animal:  {b.GetType() == typeof(Animal)}");  // output: False
 
Console.WriteLine($"is Giraffe:     {b is Giraffe}");                   // output: True
Console.WriteLine($"typeof Giraffe: {b.GetType() == typeof(Giraffe)}"); // output: True
```

## [Const](https://learn.microsoft.com/de-de/dotnet/csharp/language-reference/keywords/const)

### Beschreibung

- Konstanten werden für Variablen verwendet die beim deklarieren direkt initialisiert und danach nie mehr verändert werden.
- Konstanten können nicht [static](/Basics/#static) sein

### Beispiel

```csharp
int value = 15;
value = 20; // überschreibbar
Console.WriteLine(value);
 
const int value2 = 15;
value2 = 20; // Nicht überrschreibar
Console.WriteLine(value2);
 
const int value3; // Konstanten müssen direkt initialisiert werden
```
