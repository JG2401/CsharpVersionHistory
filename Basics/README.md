# Basics

## Exception

## Finalizer (Destruktoren)

```csharp
class Car
{
    ~Car()  // finalizer
    {
        // cleanup statements...
    }
}
```

## Virtual

## Override

## Stack & Heap

Datenstrukturen sind wichtig um Daten schnell und effizient zu speichern, zu verwalten und zu organisieren Dazu gehören Stack (Stapel) & Heap (Haufen). Diese sind Teile des Arbeitsspeichers.

### Stack

Stack beinhaltet [Wertetypen](#wertetypen) und ist sehr schnell da Stack eine feste Struktur hat.

#### Eigenschaften

- begrenzte Größe
- LIFO (Last in, First out) Datenstruktur
- Größe ändert sich mit Programmverlauf
- Verwendung: lokale Variablen & Funktionsparameter
- Kein explizites Freigeben des Speichers nötig
- sehr effizient

### Heap

Heap beinhaltet [Referenztypen](#referenztyp) und ist weniger strukturiert und dadurch langsamer.

#### Eigenschaften

- beliebige Größe (abhängig von Prozessgrenze / Speichergrenze)
- Im Vergleich zu Stack langsam
- Heap Objekte können global sein
- In Programmiersprachen ohne Garbage Collector muss der Speicher manuell freigegeben werden, wenn er nicht mehr benötigt wird.

## Wertetypen & Referenztypen

### Wertetypen

```csharp
int i = 0;
```

### Referenztyp

Referenzypten sind alle Typen, deren Objekte mit dem „new“-Schlüsselwort instanziiert werden.
Es besteht ein Verweis auf einen Wert eines Objekts im Speicher.

```csharp
Person p1 = new Person("Jonas", 23);
Person p2 = p1 //Verweis auf das erste Objekt. Es wird keine zweite Person erstellt
```

## Mehrere Variablen in einer Zeile deklarieren/initialisieren

Es ist möglich mehrere Variablen in einer Zeile zu deklarieren/initialisieren.

```csharp
string A, B, C;
double X = 1.0, Y = 2.0, Z = 3.0;
```

## [Static](https://learn.microsoft.com/de-de/dotnet/csharp/language-reference/keywords/static)

### Beschreibung

Statisch bedeutet, dass dieser Typ nicht instanziiert werden kann. Es ist somit nicht möglich ein Objekt einer statischen Klasse zu erstellen oder über ein Objekt auf einen statischen Member zuzugreifen (Felder, Eigenschaften, usw.)

#### Anwendbar für:

- Klassen
- Felder
- Methoden
- Eigenschaften (Properties)
- Operatoren
- Ereignisse (Events)
- Konstruktoren

### Anwendungsfallbeispiel: Labeldruck

2 Klassen: Label & Print

Die Klasse Label wird nicht-static definiert weil sich die Daten des Labels bei jedem Druck unterscheiden können.

```csharp
internal class Label
{
    internal string Wert1 { get; set; }
    internal string Wert2 { get; set;}
}
```

Die Klasse Print wird static definiert. Da diese z.B.: unterschiedliche Drucken-Funktionen beinhaltet, welche aber einmal definiert wurden und danach immer das gleiche machen.

```csharp
internal static class Print
{
    internal static void IpPrint(Label label)
    {
        Console.WriteLine("IpPrint");
    }
 
    internal static void UsbPrint(Label label)
    {
        Console.WriteLine("UsbPrint");
    }
}
```

#### Aufruf

```csharp
Label label1 = new Label();
label1.Wert1 = "Test1";
label1.Wert2 = "Test2";
Print.IpPrint(label1);
 
Label label2 = new Label();
label2.Wert1 = "Test3";
label2.Wert2 = "Test4";
Print.UsbPrint(label2);
```

## [String-Interpolation ( $ )](https://learn.microsoft.com/de-de/dotnet/csharp/language-reference/tokens/interpolated)

String-Interpolation ist eine Möglichkeit um Variablen in einem String einzubetten.

```csharp
string value = "World";
Console.WriteLine($"Hello {value}");
//Output: Hello World
```

## [Verbatim-Text ( @ )](https://learn.microsoft.com/de-de/dotnet/csharp/language-reference/tokens/verbatim)

```csharp
string filename1 = "c:\\documents\\files\\test.txt";
//Verbatim-Text
string filename2 = @"c:\documents\files\test.txt";
 
Console.WriteLine(filename1);
Console.WriteLine(filename2);
 
//Output: c:\documents\files\test.txt
```

Es kann auch Bezeichner verwendet werden damit Schlüsselwörter wie z.B.: for, class, usw. als Bezeichner anerkannt werden → @for

## [abstract](https://learn.microsoft.com/de-de/dotnet/csharp/language-reference/keywords/abstract)

Abstrakte Klassen können nicht instanziiert werden. Sie werden verwendet um davon zu erben.
Abstrakte Methoden, Eigenschaften, Indexer und Ereignisse können nur in abstrakten Klassen verwendet werden.

#### Anwendbar für

- Klassen
- Methoden
- Eigenschaften (Properties)
- Indexer
- Ereignisse (Events)

## Kovarianz

Kovarianz ermöglicht es ein Objekt einer erbenden Klasse in eine Variable der Basisklasse zuzuweisen.

```csharp
class Anton { }
class Berta : Anton { }
class Caesar : Anton { }
 
public void Kovarianz()
{
   Anton berta = new Berta();
}
```

## Kontravarianz

```csharp
public void Kontravarianz() 
{
   Anton[] berta = new Berta[10];
   berta[3] = new Caesar();    //Fehler: System.ArrayTypeMismatchException: "Attempted to access an element as a type incompatible with the array."
}
```

## new

### [operator](https://learn.microsoft.com/de-de/dotnet/csharp/language-reference/operators/new-operator)


„new“ kann zur Instanziierung eines Typs angewendet werden.

#### Beispiel

```csharp
Anton a = new Anton();
 
//Alternativ
Anton a = new();
```

```csharp
List<int> ints = new List<int>();
ints.Add(0);
Console.Write(ints[0] + Environment.NewLine);
 
//Alternativ
List<int> ints2 = new();
ints2.Add(1);
Console.Write(ints2[0] + Environment.NewLine);
```

```csharp
int[] ints = new int[1];
ints[0] = 0;
Console.Write(ints[0] + Environment.NewLine);
 
//Alternativ
int[] ints2 = new[] { 0 };
Console.Write(ints2[0] + Environment.NewLine);
```


### [modifier](https://learn.microsoft.com/de-de/dotnet/csharp/language-reference/keywords/new-modifier)

Es kann auch als Deklarationsmodifizierer genutzt werden.

#### Beispiel

```csharp
class BaseClass
{
   public static int x = 100;
}
 
class SubClass : BaseClass
{
   new public static int x = 50;
}
```

## [readonly](https://learn.microsoft.com/de-de/dotnet/csharp/language-reference/keywords/readonly)

Readonly definiert, dass die Variable nur zugewiesen werden kann

- durch die Deklaration
- im Konstruktor

### readonly vs. const

#### const

- Standardmäßig static
- Kann innerhalb Methoden deklariert werden

## volatile

Das Schlüsselwort volatile gibt an, dass ein Feld von mehreren Threads geändert werden kann, die zur gleichen Zeit ausgeführt werden.

## Indexer

Indexer ermöglichen, dass Instanzen einer Klasse oder Struktur wie Arrays indiziert werden.

### Beispiel

#### Klasse

```csharp
internal class Spieler
{
	public string Name { get; set; }
}
 
internal class TeamOhneIndexer
{
	private List<Spieler> spielerListe = new List<Spieler>();
 
	public TeamOhneIndexer()
	{
		spielerListe.Add(new Spieler { Name = "Horst" });
		spielerListe.Add(new Spieler { Name = "Peter" });
	}
}
 
internal class TeamMitIndexer
{
	private List<Spieler> spielerListe = new List<Spieler>();
 
	public TeamMitIndexer()
	{
		spielerListe.Add(new Spieler { Name = "Horst" });
		spielerListe.Add(new Spieler { Name = "Peter" });
	}
 
	public Spieler this[int index]
	{
		get { return spielerListe[index]; }
		set { spielerListe[index] = value; }
	}
}
```

#### Aufruf

```csharp
Allgemein.IndexerFolder.TeamOhneIndexer teamOhneIndexer = new Allgemein.IndexerFolder.TeamOhneIndexer();
Console.WriteLine(teamOhneIndexer[1].Name); //Fehler: Eine Indizierung mit [] kann nicht auf einen Ausdruck vom Typ "Team" angewendet werden
 
Allgemein.IndexerFolder.TeamMitIndexer teamMitIndexer = new Allgemein.IndexerFolder.TeamMitIndexer();
Console.WriteLine(teamMitIndexer[1].Name);
```
