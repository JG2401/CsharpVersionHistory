# C# Version 8.0

Veröffentlicht im September 2019.

C# 8.0 ist das erste Hauptrelease, das speziell auf .NET Core ausgerichtet ist. Viele Features benötigen neue CLR-Funktionen oder Bibliothekstypen aus .NET Core 3.0.

## Neue Features

### Readonly-Member
Mit `readonly` können Member als unveränderlich markiert werden.

```csharp
readonly struct Punkt
{
    public int X { get; }
    public int Y { get; }
    public readonly int Abstand() => X * X + Y * Y;
}
```

### Standardschnittstellenmethoden
Interfaces können nun Implementierungen für Methoden enthalten.

```csharp
public interface IBeispiel
{
    void Methode() => Console.WriteLine("Standardimplementierung");
}
```

### Verbesserungen am Musterabgleich

- **Switch-Ausdrücke**

    ```csharp
    string ergebnis = wert switch
    {
        1 => "eins",
        2 => "zwei",
        _ => "anderes"
    };
    ```

- **Eigenschafts-, Tupel- und Positionsmuster**

    ```csharp
    if (person is { Name: "Jonas", Alter: 30 }) { /* ... */ }
    if ((x, y) is (0, 0)) { /* Ursprung */ }
    ```

### using-Deklarationen
Ressourcen werden automatisch am Ende des Blocks freigegeben.

```csharp
using var stream = File.OpenRead("datei.txt");
```

### Statische lokale Funktionen
Lokale Funktionen können als `static` deklariert werden.

```csharp
void Methode()
{
    static int Add(int a, int b) => a + b;
}
```

### Verwerfbare Referenzstrukturen
Strukturen können `IDisposable` implementieren.

### Nullwerte zulassende Verweistypen
Erlaubt die explizite Angabe, ob ein Verweistyp `null` sein darf.

```csharp
string? text = null;
```

### Asynchrone Streams
Daten können asynchron gestreamt werden.

```csharp
async IAsyncEnumerable<int> Zahlen()
{
    for (int i = 0; i < 5; i++)
        yield return i;
}
```

### Indizes und Bereiche
Einfacher Zugriff auf Teile von Arrays und Listen.

```csharp
int[] zahlen = { 1, 2, 3, 4, 5 };
int letzter = zahlen[^1]; // 5
int[] teil = zahlen[1..3]; // {2, 3}
```

### NULL-Coalescing-Zuweisung
Weist einen Wert nur zu, wenn die Variable `null` ist.

```csharp
text ??= "Standardwert";
```

---

C# 8.0 bringt viele moderne Features, die vor allem mit .NET Core 3.0 optimal genutzt werden können.