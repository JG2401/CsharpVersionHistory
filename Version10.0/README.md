# C# Version 10.0

Veröffentlicht im November 2021 mit .NET 6.

## Neue Features

### Datensatzstrukturen
Records können jetzt auch als Strukturen (`record struct`) definiert werden.

```csharp
public record struct Punkt(int X, int Y);
```

### Verbesserungen von Strukturtypen
Strukturen und anonyme Typen unterstützen jetzt `with`-Ausdrücke.

```csharp
var p1 = new Punkt(1, 2);
var p2 = p1 with { X = 3 };
```

### Handler für interpolierte Zeichenfolgen
Optimierte Verarbeitung von interpolierten Strings für bessere Performance.

```csharp
Console.WriteLine($"Wert: {wert}");
```

### global using-Direktiven
Globale `using`-Anweisungen für das gesamte Projekt.

```csharp
// global using System;
```

### Dateibezogene Namespacedeklaration
Einfachere Namespace-Deklaration am Dateianfang.

```csharp
namespace MeinProjekt;
```

### Erweiterte Eigenschaftenmuster
Präzisere Muster für Eigenschaften.

```csharp
if (person is { Adresse.Stadt: "Berlin" }) { /* ... */ }
```

### Verbesserungen bei Lambda-Ausdrücken
- Natürlicher Typ für Lambdas
- Rückgabetyp deklarierbar
- Attribute auf Lambdas möglich

```csharp
Func<int, int> quad = x => x * x;
[Obsolete] Func<int, int> alt = x => x + 1;
```

### Zeichenfolgeninterpolation für const-Strings
Konstante Strings können interpoliert werden, wenn alle Platzhalter konstant sind.

```csharp
const string Name = "Jonas";
const string Begruessung = $"Hallo, {Name}!";
```

### sealed ToString in records
`ToString` kann in record-Typen als `sealed` überschrieben werden.

### Verbesserte Warnungen für Null-Status und Zuweisungen

### Dekonstruktion: Zuweisung und Deklaration gleichzeitig möglich

### AsyncMethodBuilder-Attribut für Methoden

### CallerArgumentExpression-Attribut

### Neues Format für #line-Pragma

### Vorschaufeatures (nur mit `<LangVersion>preview</LangVersion>`)
- Generische Attribute
- Statische abstrakte Member in Schnittstellen

---

C# 10.0 bringt viele Verbesserungen für kompakteren, präziseren und leistungsfähigeren Code.