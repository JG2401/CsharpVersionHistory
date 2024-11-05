# Version 3.0

## Anonyme Typen

Ermöglichen die definition von Variablen ohne den Typ anzugeben. Der Typ wird vom Compiler generiert.

```csharp
var v = new { Amount = 108, Message = "Hello" };
Console.WriteLine($"Amount: {v.Amount}, Message: {v.Message}");
```

### Linq

```csharp
public void LinqTest()
{
    //Initialization
    List<Product> products = new List<Product>();
    products.Add(new Product { Color = "Rot", Price = 5 });
    products.Add(new Product { Color = "Blau", Price = 10 });

    //LINQ
    var productQuery =
        from prod in products
        select new { prod.Color, prod.Price };

    //Output
    foreach (var v in productQuery)
    {
        Console.WriteLine("Color={0}, Price={1}", v.Color, v.Price);
    }
}

internal class Product
{
    public string Color { get; set; }
    public double Price { get; set; }
}
```

