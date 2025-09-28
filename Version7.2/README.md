# C# Version 7.2

Veröffentlicht im November 2017.

Mit C# 7.2 wurden einige kleine, aber nützliche Sprachfeatures hinzugefügt:

## Neue Features

### Initialisierer für stackalloc-Arrays
Direkte Initialisierung von Arrays auf dem Stack.

```csharp
Span<int> zahlen = stackalloc int[] { 1, 2, 3 };
```

### fixed-Anweisung für beliebige Typen
`fixed` kann mit jedem Typ verwendet werden, der ein Muster unterstützt.

### Zugriff auf feste Felder ohne Anheften
Erlaubt den Zugriff auf Felder, ohne sie explizit zu fixieren.

### Neuzuweisung lokaler ref-Variablen
Ref-Variablen können neu zugewiesen werden.

```csharp
ref int r = ref arr[0];
r = ref arr[1];
```

### readonly struct-Typen
Strukturen können als unveränderlich deklariert werden.

```csharp
public readonly struct Punkt
{
    public int X { get; }
    public int Y { get; }
}
```

### in-Parameter
Argumente werden als Referenz übergeben, aber nicht verändert.

```csharp
void Print(in int x)
{
    Console.WriteLine(x);
}
```

### ref readonly-Rückgaben
Methoden können einen Wert als Referenz zurückgeben, ohne Schreibzugriff zu erlauben.

```csharp
public ref readonly int GetValue() => ref value;
```

### ref struct-Typen
Strukturen, die direkt auf verwalteten Speicher zugreifen und nur auf dem Stack liegen dürfen.

```csharp
ref struct Buffer { /* ... */ }
```

### Allgemeinere Beschränkungen
Mehr Flexibilität bei Generics.

### Nicht schließende benannte Argumente
Positionale Argumente können auf benannte Argumente folgen.

```csharp
Print("Hallo", times: 3);
```

### Führende Unterstriche in numerischen Literalen
Numerische Literale dürfen mit Unterstrichen beginnen.

```csharp
int zahl = _1_000_000;
```

### private protected-Zugriffsmodifizierer
Zugriff für abgeleitete Klassen innerhalb derselben Assembly.

```csharp
private protected int Wert;
```

### Bedingte ref-Ausdrücke
Das Ergebnis eines bedingten Ausdrucks kann ein Verweis sein.

```csharp
ref int r = ref (a > b ? ref x : ref y);
```

---

C# 7.2 brachte viele kleine Verbesserungen für Performance, Lesbarkeit und Sicherheit.