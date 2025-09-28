# C# Version 4.0

C# 4.0 wurde mit Visual Studio 2010 veröffentlicht und brachte folgende Neuerungen:

## Dynamische Bindung (`dynamic`)
Das `dynamic`-Schlüsselwort erlaubt es, den Typ einer Variable erst zur Laufzeit festzulegen. Dies ähnelt dynamisch typisierten Sprachen wie JavaScript.

```csharp
dynamic x = "Hallo";
Console.WriteLine(x.Length); // Funktioniert, da x zur Laufzeit ein string ist
```

## Benannte und optionale Argumente
Methodenparameter können beim Aufruf benannt und/oder weggelassen werden. Das vereinfacht Methodenüberladungen und erhöht die Flexibilität.

```csharp
void Print(string text, int times = 1)
{
    for (int i = 0; i < times; i++)
        Console.WriteLine(text);
}

Print("Hi", times: 3); // Benannter Parameter
Print("Hallo");        // Optionaler Parameter
```

## Generische Kovarianz und Kontravarianz
Erlaubt mehr Flexibilität beim Arbeiten mit Generics, besonders für Framework- und Bibliotheksautoren.

```csharp
IEnumerable<string> strings = new List<string>();
IEnumerable<object> objects = strings; // Kovarianz
```

## Eingebettete Interop-Typen
Vereinfacht die Bereitstellung von COM-Interopassemblys durch das Einbetten der benötigten Typen direkt in die Anwendung.

---

Das wichtigste Feature war die Einführung von `dynamic`, das mächtige, aber auch fehleranfällige Konstrukte ermöglicht.