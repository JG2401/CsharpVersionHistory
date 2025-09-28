# C# Version 7.1

Veröffentlicht im August 2017.

Mit C# 7.1 wurden Punktreleases eingeführt. Diese Version brachte ein Konfigurationselement zur Auswahl der Sprachversion, drei neue Sprachfeatures und neues Compilerverhalten.

## Neue Features

### async Main-Methode
Der Einstiegspunkt einer Anwendung kann jetzt `async` sein.

```csharp
static async Task Main(string[] args)
{
    await Task.Delay(1000);
    Console.WriteLine("Async Main!");
}
```

### default-Literale Ausdrücke
Sie können `default` als Wert verwenden, wenn der Zieltyp bekannt ist.

```csharp
int x = default;
MyClass obj = default;
```

### Abgeleitete Tupelelementnamen
Tupelelementnamen werden aus der Initialisierung abgeleitet.

```csharp
var name = "Jonas";
var alter = 30;
var person = (name, alter); // person.name, person.alter
```

### Musterabgleich für generische Typparameter
Musterabgleich funktioniert jetzt auch mit generischen Typen.

```csharp
bool IstString<T>(T value) => value is string;
```

### Compileroptionen
Neue Optionen `-refout` und `-refonly` zur Steuerung der Referenzassembly-Generierung.

---

C# 7.1 brachte kleine, aber nützliche Verbesserungen für moderne und flexible Programmierung.