# C# Version 12.0

Veröffentlicht im November 2023.

## Neue Features

### Primäre Konstruktoren
Erstellen Sie Konstruktoren direkt in der Klassen- oder Strukturdefinition.

```csharp
public class Person(string name, int alter)
{
    public string Name { get; } = name;
    public int Alter { get; } = alter;
}
```

### Sammlungsausdrücke
Neue Syntax für die Erstellung und Erweiterung von Sammlungen.

```csharp
int[] zahlen = [1, 2, 3];
int[] mehrZahlen = [..zahlen, 4, 5];
```

### Inlinearrays
Arrays mit fester Größe direkt in einem `struct`.

```csharp
public struct Buffer
{
    private inline int[8] data;
}
```

### Optionale Parameter in Lambdaausdrücken
Lambda-Parameter können Standardwerte haben.

```csharp
Func<int, int, int> addiere = (a, b = 1) => a + b;
```

### ref readonly-Parameter
Mehr Klarheit für APIs mit `ref`- oder `in`-Parametern.

```csharp
void Print(ref readonly int x)
{
    Console.WriteLine(x);
}
```

### Alias eines beliebigen Typs
`using` kann für jeden Typ als Alias verwendet werden.

```csharp
using Ganzzahl = System.Int32;
Ganzzahl x = 5;
```

### Experimentattribute
Kennzeichnen Sie experimentelle Features.

```csharp
[Experimental]
void NeueFunktion() { }
```

### Interceptors (Preview)
Erlauben das Abfangen und Modifizieren von Methodenaufrufen (nur als Preview verfügbar).

---

C# 12.0 bringt neue Syntax und Features für produktiveren und konsistenteren Code.