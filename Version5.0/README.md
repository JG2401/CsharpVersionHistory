# C# Version 5.0

Veröffentlicht im August 2012 mit Visual Studio 2012.

## Neue Features

### Asynchrone Member (`async` und `await`)
Ermöglichen die einfache und übersichtliche asynchrone Programmierung.

```csharp
public async Task<int> GetDataAsync()
{
    await Task.Delay(1000);
    return 42;
}
```

### CallerInfo-Attribute
Erlauben den Zugriff auf Informationen über den Aufrufer einer Methode, z.B. Dateiname, Methodenname oder Zeilennummer.

```csharp
void Log(string message,
    [CallerMemberName] string memberName = "",
    [CallerFilePath] string filePath = "",
    [CallerLineNumber] int lineNumber = 0)
{
    Console.WriteLine($"{message} in {memberName} ({filePath}:{lineNumber})");
}
```

---

Das Highlight dieser Version sind die Schlüsselwörter `async` und `await`, die Asynchronität zum festen Bestandteil der Sprache machen.