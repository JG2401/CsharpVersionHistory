# C# Version 7.0

Veröffentlicht im März 2017 mit Visual Studio 2017.

## Neue Features

### Out-Variablen
Direkte Deklaration von Variablen im `out`-Parameter.

```csharp
if (int.TryParse("123", out int zahl))
{
    Console.WriteLine(zahl);
}
```

### Tupel und Dekonstruktionen
Mehrere Werte einfach zurückgeben und zerlegen.

```csharp
(string Name, int Alter) GetPerson() => ("Jonas", 30);
var (name, alter) = GetPerson();
```

### Mustervergleich
Vergleiche mit Mustern für mehr Lesbarkeit.

```csharp
if (obj is string s)
{
    Console.WriteLine($"String: {s}");
}
```

### Lokale Funktionen
Funktionen innerhalb von Methoden definieren.

```csharp
void Hauptfunktion()
{
    int Addiere(int a, int b) => a + b;
    Console.WriteLine(Addiere(2, 3));
}
```

### Erweiterte Ausdruckskörpermember
Mehr Möglichkeiten für kurze Methoden und Eigenschaften.

```csharp
public int Quadrat(int x) => x * x;
```

### Lokale ref-Variablen und Ref-Rückgaben
Direkter Zugriff und Rückgabe von Referenzen.

```csharp
ref int Suche(int[] arr, int wert)
{
    for (int i = 0; i < arr.Length; i++)
        if (arr[i] == wert) return ref arr[i];
    throw new Exception("Nicht gefunden");
}
```

### Weitere Features
- Verwerfen mit `_`
- Binäre Literale (`0b1010`) und Zahlentrennzeichen (`1_000_000`)
- Throw-Ausdrücke (`throw new Exception()` direkt in Ausdrücken)

---

Diese Features machen den Code noch kompakter und lesbarer. .NET Core unterstützt nun alle Betriebssysteme und fokussiert sich auf Cloud und Portabilität.