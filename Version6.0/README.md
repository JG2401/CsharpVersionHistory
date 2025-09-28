# C# Version 6.0

Veröffentlicht im Juli 2015 mit Visual Studio 2015.

## Neue Features

### Statische Importe
Erlaubt das direkte Verwenden von statischen Methoden ohne Klassennamen.

```csharp
using static System.Console;
WriteLine("Hallo Welt!");
```

### Ausnahmefilter
Ermöglicht das Filtern von Exceptions mit Bedingungen.

```csharp
try { /* ... */ }
catch (Exception ex) when (ex.Message.Contains("kritisch"))
{
    // Nur bei bestimmten Fehlern
}
```

### Initialisierer für automatische Eigenschaften
Automatische Eigenschaften können direkt initialisiert werden.

```csharp
public int Zahl { get; set; } = 42;
```

### Ausdruckskörpermember
Kürzere Syntax für Methoden und Eigenschaften.

```csharp
public int Quadrat(int x) => x * x;
```

### Nullpropagator
Vereinfacht den Umgang mit null-Werten.

```csharp
int? länge = text?.Length;
```

### Zeichenfolgeninterpolation
Einfaches Einfügen von Variablen in Strings.

```csharp
string name = "Jonas";
string begruessung = $"Hallo, {name}!";
```

### `nameof`-Operator
Gibt den Namen eines Symbols als String zurück.

```csharp
Console.WriteLine(nameof(name)); // "name"
```

### Weitere Features
- Indexinitialisierer
- `await` in `catch`- und `finally`-Blöcken
- Standardwerte für Getter-exklusive Eigenschaften

---

C# 6.0 machte den Code kompakter und lesbarer. Außerdem wurde der Roslyn-Compiler als Dienst veröffentlicht, der nun selbst in C# geschrieben ist.