# C# Version 13.0

Freigegeben im November 2024.

## Neue Features

### params Collections
Der `params`-Modifikator ist jetzt für beliebige Sammlungen wie `Span<T>` und Schnittstellentypen erlaubt.

```csharp
void PrintAll(params Span<int> zahlen) { /* ... */ }
```

### Neuer lock-Typ und Semantik
`lock` unterstützt jetzt `System.Threading.Lock` mit exklusivem Bereich und Dispose-Muster.

```csharp
lock (meinLock)
{
    // exklusiver Bereich
}
```

### Neue Escape-Sequenz: `\e`
Das Escape-Zeichen (Unicode U+001B) kann als `\e` verwendet werden.

```csharp
char esc = '\e';
```

### Optimierungen bei Methodengruppen-Überlastauflösung

### Impliziter Indexerzugriff in Objektinitialisierern
Der Indexoperator `^` ist jetzt in Objektinitialisierungen erlaubt.

```csharp
var arr = new int[] { 1, 2, 3, 4 };
var obj = new MyClass { Werte = { [^1] = 99 } };
```

### ref in Iteratoren und asynchronen Methoden
`ref` kann in nativen und unsicheren Kontexten in Iteratoren und async-Methoden verwendet werden.

### ref struct-Typen implementieren Schnittstellen
`ref struct`-Typen können Schnittstellen implementieren.

```csharp
ref struct Buffer : IBuffer { /* ... */ }
```

### ref struct als Typargument in Generika
`ref struct`-Typen sind als Typargumente für Generika erlaubt.

### Partielle Eigenschaften und Indexer
Teilweise deklarierte Eigenschaften und Indexer sind in `partial`-Typen möglich.

### Überlastauflösung mit Priorität
Bibliotheksautoren können Überladungen als bevorzugt kennzeichnen.

### Vorschau: `field`-Schlüsselwort
Das kontextbezogene Schlüsselwort `field` erlaubt Zugriff auf das Backing-Feld einer automatisch implementierten Eigenschaft.

---

C# 13.0 bringt neue Möglichkeiten für Sammlungen, Locking, Typen und Initialisierungen sowie weitere Optimierungen.