# C# Version 7.3

Veröffentlicht im Mai 2018.

C# 7.3 bringt zwei Hauptdesigns: bessere Performance für sicheren Code und inkrementelle Verbesserungen vorhandener Features. Es wurden auch neue Compileroptionen hinzugefügt.

## Neue Features für sicheren Code

- Zugriff auf feste Felder ohne Anheften
- Neuzuweisung lokaler ref-Variablen
- Initialisierer für stackalloc-Arrays
- `fixed`-Anweisungen mit jedem Typ, der ein Muster unterstützt
- Generischere Einschränkungen bei Generics

## Verbesserungen vorhandener Features

- Vergleich von Tupeltypen mit `==` und `!=`

    ```csharp
    (int, int) a = (1, 2);
    (int, int) b = (1, 2);
    bool gleich = a == b; // true
    ```

- Ausdrucksvariablen an mehreren Standorten verwenden

    ```csharp
    if (int.TryParse("123", out int x) || int.TryParse("456", out x))
        Console.WriteLine(x);
    ```

- Attribute für Sicherungsfelder von automatisch implementierten Eigenschaften

    ```csharp
    [field: NonSerialized]
    public int Wert { get; set; }
    ```

- Verbesserte Methodenauflösung bei `in`-Parametern und Überladungen

## Neue Compileroptionen

- `-publicsign`: Ermöglicht das Signieren von Assemblys für OSS
- `-pathmap`: Bietet Zuordnung für Quellverzeichnisse

---

C# 7.3 macht sicheren Code leistungsfähiger und verbessert bestehende Sprachfeatures.