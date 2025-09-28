# C# Version 11.0

Veröffentlicht im November 2022.

## Neue Features

### Unformatierte Zeichenfolgenliterale
Mehrzeilige Strings ohne Escape-Zeichen.

```csharp
string text = """
    Zeile 1
    Zeile 2
    """;
```

### Generische Mathematik
Numerische Algorithmen können für alle Zahlentypen geschrieben werden.

```csharp
static T Add<T>(T a, T b) where T : INumber<T> => a + b;
```

### Generische Attribute
Attribute können generisch sein.

```csharp
[MyAttribute<int>]
public class Beispiel { }
```

### UTF-8-Zeichenfolgenliterale
Direkte UTF-8-Strings.

```csharp
ReadOnlySpan<byte> utf8 = "Hallo"u8;
```

### Zeilenvorschübe in Zeichenfolgeninterpolation
Zeilenumbrüche sind in interpolierten Strings erlaubt.

```csharp
string info = $"Name: {name}
Alter: {alter}";
```

### Listenmuster
Vergleich von Listenstrukturen mit Mustern.

```csharp
if (arr is [1, 2, ..])
{
    // Beginnt mit 1, 2
}
```

### Dateilokale Typen
Typen können nur innerhalb einer Datei sichtbar sein.

```csharp
file class Helper { }
```

### Erforderliche Member
Member müssen beim Initialisieren gesetzt werden.

```csharp
public class Person
{
    public required string Name { get; set; }
}
```

### Automatische Standardstrukturen
Strukturen erhalten automatisch einen Standardwert.

### Musterabgleich Span<char> für string
Vergleich von `Span<char>` mit konstanten Strings.

### Erweiterter nameof-Bereich
`nameof` kann in mehr Kontexten verwendet werden.

### Numerisches IntPtr
`IntPtr` unterstützt numerische Operationen.

### ref-Felder und scoped ref
Mehr Kontrolle über Referenzen und Lebensdauer.

### Verbesserte Methodengruppenkonvertierung zu Delegaten

### Warnungswelle 7

---

C# 11.0 bringt viele Features für moderne, sichere und flexible Programmierung.