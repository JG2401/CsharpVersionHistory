# C# Version 9.0

Veröffentlicht im November 2020 mit .NET 5.

## Neue Features

### Datensätze (`record`)
Kompakte Syntax für unveränderliche Datencontainer mit Wertsemantik.

```csharp
public record Person(string Name, int Alter);
var p1 = new Person("Jonas", 30);
var p2 = p1 with { Alter = 31 };
```

### init-only-Setter
Eigenschaften können nur bei der Initialisierung gesetzt werden.

```csharp
public class Auto
{
    public string Marke { get; init; }
}
```

### Top-Level-Anweisungen
Kein `Main`-Methoden- oder Klassen-Wrapper nötig.

```csharp
Console.WriteLine("Hallo Welt!");
```

### Verbesserter Musterabgleich
- **Relationale Muster:** `<`, `>`, `<=`, `>=`
- **Logische Muster:** `and`, `or`, `not`

```csharp
if (wert is >= 0 and <= 10) { /* ... */ }
if (obj is not null) { /* ... */ }
```

### Integerwerte mit nativer Größe
`nint` und `nuint` für CPU-native Integer.

```csharp
nint x = 42;
```

### Funktionszeiger
Direkte Zeiger auf Funktionen.

```csharp
delegate*<int, int, int> addPtr = &Add;
```

### Modulinitialisierer
Methoden, die beim Laden einer Assembly ausgeführt werden.

```csharp
[ModuleInitializer]
public static void Init() { /* ... */ }
```

### Weitere Features
- Zieltypisierte `new`-Ausdrücke: `List<int> zahlen = new();`
- Anonyme `static`-Funktionen: `static () => 42`
- Lambda-Parameter verwerfen: `_ => ...`
- Attribute auf lokale Funktionen
- Erweiterung von `GetEnumerator()` für `foreach`
- Partielle Methoden mit Rückgabewert und Zugriffsmodifizierer

---

C# 9.0 bringt viele moderne Features für produktiven, kompakten und sicheren Code.