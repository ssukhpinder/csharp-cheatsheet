The comprehensive C# Cheat Sheet is designed to aid developers in mastering key syntax and concepts related to C# programming.

## Contents

 1. Basic Structure

 2. Data Types

 3. Variables

 4. Constants

 5. Conditional Statements

 6. Loops

 7. Arrays

 8. Lists

 9. Dictionaries

 10. Methods

 11. Classes & Objects

 12. Exception Handling

 13. Delegates, Events & Lambdas

 14. LINQ (Language-Integrated Query)

 15. Attributes

 16. Async/Await

 17. Miscellaneous

 18. String Manipulation

 19. File I/O

 20. Date & Time

 21. Generics

 22. Nullables

 23. Attributes & Reflection

 24. Extension Methods

 25. Dependency Injection

 26. Partial Classes

 27. Interoperability

 28. Anonymous Types

 29. Tuples

 30. Pattern Matching

 31. Local Functions

 32. Records

 33. with Expressions

 34. Indexers and Ranges

 35. using Declaration

 36. Nullable Reference Types (NRTs)

 37. Pattern-Based Using

 38. Property Patterns

 39. Default Interface Implementations

 40. Dynamic Binding

## 1. Basic Structure

All C# programs follow a fundamental structure, outlined below:
```
    using System;
    
    public class HelloWorld
    {
        public static void Main(string[] args)
        {
            Console.WriteLine("Hello, World!");
        }
    }
```
Starting with .NET 5, top-level statements simplify the Program.cs content:
```
    Console.WriteLine("Hello, World");
```
## 2. Data Types

C# supports various data types such as:

* Value Types: int, char, float

* Reference Types: string, class, array

## 3. Variables

Variables are symbolic names for values:
```
    int age = 30; // integer variable
    string name = "John"; // string variable
    double PI = 3.14159; // double for floating-point numbers
    bool isLoggedIn = true; // boolean variable
```
Use ‘var’ for type inference:
```
    var number = 5; // compiler infers type as int
    var message = "This is a message"; // compiler infers type as string
```
## 4. Constants

Constants hold immutable values:
```
    const double GRAVITY = 9.81; // constant for gravitational acceleration
    const string COMPANY_NAME = "MyCompany"; // constant company name
```
## 5. Conditional Statements

Control program flow based on conditions:
```
    int age = 20;
    
    if (age >= 18)
    {
        Console.WriteLine("You are eligible to vote.");
    }
    else
    {
        Console.WriteLine("You are not eligible to vote.");
    }
    
    switch (variable) { /*...*/ } // Switch statement
```
## 6. Loops

Execute code repeatedly:
```
    for (int i = 1; i <= 5; i++)
    {
        Console.WriteLine(i);
    }
    
    foreach (var item in collection) { /*...*/ } // Foreach loop
    
    while (condition) { /*...*/ } // While loop
    
    do { /*...*/ } while (condition); // Do-while loop
```
## 7. Arrays

Fixed-size collections of elements:
```
    string[] names = new string[3] { "Alice", "Bob", "Charlie" };
    Console.WriteLine(names[1]); // Output: Bob (accessing element at index 1)
```
## 8. Lists

Dynamic collections similar to arrays:
```
    List<int> numbers = new List<int>();
    numbers.Add(1);
    numbers.Add(2);
    numbers.Add(3);
    
    foreach (var number in numbers)
    {
        Console.WriteLine(number);
    }
```
## 9. Dictionaries

Key-value pairs for data association:
```
    Dictionary<string, string> phonebook = new Dictionary<string, string>();
    phonebook.Add("John Doe", "123-456-7890");
    phonebook.Add("Jane Doe", "987-654-3210");
    
    Console.WriteLine(phonebook["John Doe"]); // Output: 123-456-7890
```
## 10. Methods

Encapsulate reusable logic:
```
    public class Rectangle
    {
        public double Width { get; set; }
        public double Height { get; set; }
    
        public double GetArea()
        {
            return Width * Height;
        }
    }
    
    public class Program
    {
        public static void Main(string[] args)
        {
            Rectangle rect = new Rectangle();
            rect.Width = 5;
            rect.Height = 10;
    
            double area = rect.GetArea();
            Console.WriteLine($"Area of rectangle: {area}");
        }
    }
```
## 11. Classes & Objects

Classes define blueprints for objects:
```
    public class MyClass // Class definition
    {
        public string PropertyName { get; set; } // Properties store data
        public void MethodName() { /*...*/ } // Methods define actions
    }
    
    MyClass obj = new MyClass(); // Object creation
```
## 12. Exception Handling

Manage runtime errors gracefully:
```
    public static int GetNumberInput()
    {
      while (true)
      {
        try
        {
          Console.WriteLine("Enter a number: ");
          string input = Console.ReadLine();
          return int.Parse(input);
        }
        catch (FormatException)
        {
          Console.WriteLine("Invalid input. Please enter a number.");
        }
      }
    }
    
    public static void Main(string[] args)
    {
      int number = GetNumberInput();
      Console.WriteLine($"You entered: {number}");
    }
```
## 13. Delegates, Events & Lambda

For event-driven programming and method handling:
```
    public delegate void MyDelegate(); // Delegate declaration
    
    event MyDelegate MyEvent; // Event declaration
    
    public class Person
    {
      public string Name { get; set; }
      public int Age { get; set; }
    }
    
    public static void Main(string[] args)
    {
      List<Person> people = new List<Person>()
      {
        new Person { Name = "Alice", Age = 30 },
        new Person { Name = "Bob", Age = 25 },
        new Person { Name = "Charlie", Age = 40 },
      };
    
      people.Sort((p1, p2) => p1.Name.CompareTo(p2.Name));
    
      foreach (var person in people)
      {
        Console.WriteLine(person.Name); // Output: Alice, Bob, Charlie (sorted by name)
      }
    }
```
## 14. LINQ (Language-Integrated Query)

Query capabilities for data manipulation:
```
    using System.Linq;
    
    public static void Main(string[] args)
    {
      List<int> numbers = new List<int>() { 1, 2, 3, 4, 5, 6 };
      var evenNumbers = numbers.Where(x => x % 2 == 0);
    
      foreach (var number in evenNumbers)
      {
        Console.WriteLine(number); // Output: 2, 4, 6
      }
    }
```
## 15. Attributes

Add metadata to code elements:
```
    [Obsolete("Use the new DoSomethingV2 method instead.")]
    public void DoSomething()
    {
      // Implementation here
    }
    
    public void DoSomethingV2()
    {
      // New and improved implementation
    }
```
## 16. Async/Await

For non-blocking code execution:
```
    using System.Threading.Tasks;
    
    public static async Task DownloadFileAsync(string url, string filePath)
    {
      // Simulate downloading data asynchronously
      await Task.Delay(2000); // Simulate a 2-second download
    
      // Write downloaded data to the file
      File.WriteAllText(filePath, "Downloaded content");
      Console.WriteLine($"File downloaded to: {filePath}");
    }
    
    public static void Main(string[] args)
    {
      string url = "https://example.com/data.txt";
      string filePath = "downloaded_data.txt";
    
      DownloadFileAsync(url, filePath);
    
      // Continue program execution while download happens in the background
      Console.WriteLine("Downloading file...");
      Console.WriteLine("Meanwhile, you can do other things...");
    }
```
## 17. Miscellaneous

Additional language features:

* enum, interface, class, record, struct

* dynamic, is, as, var, nameof

## 18. String Manipulation

Powerful string handling methods:
```
    string.Concat(); // Combine strings
    string.Join(); // Join elements
    str.Split(); // Split string
    str.ToUpper(); // Convert to uppercase
    str.ToLower(); // Convert to lowercase
```
## 19. File I/O

Operations with files:
```
    using System.IO; // Required for File I/O
    
    File.ReadAllText(path); // Read file content
    File.WriteAllText(path, content); // Write to file
    File.Exists(path); // Check file existence
```
## 20. Date & Time

Date and time manipulation:
```
    using System;
    
    public static void Main(string[] args)
    {
      DateTime startDate = DateTime.Parse("2024-03-10");
      DateTime endDate = DateTime.Now;
    
      TimeSpan difference = endDate - startDate;
      Console.WriteLine($"Time difference: {difference.Days} days, {difference.Hours} hours");
    }
```
## 21. Generics

Type-safe data structures:
```
    public class Stack<T>
    {
      private List<T> items = new List<T>();
    
      public void Push(T item)
      {
        items.Add(item);
      }
    
      public T Pop()
      {
        T item = items[items.Count - 1];
        items.RemoveAt(items.Count - 1);
        return item;
      }
    }
    
    public static void Main(string[] args)
    {
      Stack<string> messages = new Stack<string>();
      messages.Push("Hello");
      messages.Push("World");
    
      string message = messages.Pop();
      Console.WriteLine(message); // Output: World
    }
```
## 22. Nullables

Allow value types to be null:
```
    int? nullableInt = null; // Nullable integer
```
## 23. Attributes & Reflection

Metadata and type introspection:
```
    public class Person
    {
      public string Name { get; set; }
      public int Age { get; set; }
    }
    
    public static void Main(string[] args)
    {
      Type personType = typeof(Person);
      PropertyInfo[] properties = personType.GetProperties();
    
      foreach (PropertyInfo property in properties)
      {
        Console.WriteLine(property.Name); // Output: Name, Age
      }
    }
```
## 24. Extension Methods

Add methods to existing types:
```
    public static class StringExtensions
    {
      public static string ToUppercase(this string str)
      {
        return str.ToUpper();
      }
    }
    
    public static void Main(string[] args)
    {
      string message = "Hello, world!";
      string uppercased = message.ToUppercase(); // Using the extension method
      Console.WriteLine(uppercased); // Output: HELLO, WORLD!
    }
```
## 25. Dependency Injection

Loosely coupled code design:
```
    public interface ILogger
    {
      void LogMessage(string message);
    }
    
    public class MyService
    {
      private readonly ILogger _logger;
    
      public MyService(ILogger logger)
      {
        _logger = logger;
      }
    
      public void DoSomething()
      {
        _logger.LogMessage("Doing something...");
      }
    }
    
    // Implementing the ILogger interface (example)
    public class ConsoleLogger : ILogger
    {
      public void LogMessage(string message)
      {
        Console.WriteLine(message);
      }
    }
    
    public static void Main(string[] args)
    {
      ILogger logger = new ConsoleLogger();
      MyService service = new MyService(logger);
      service.DoSomething();
    }
```
## 26. Partial Classes

Splitting a single class definition:
```
    public partial class MyClass { /*...*/ } // Partial class definition
```
## 27. Interoperability

Interop with other languages:
```
    using System;
    using System.Runtime.InteropServices;
    
    [DllImport("user32.dll")]
    public static extern int MessageBox(IntPtr hWnd, string lpText, string lpCaption, uint uType);
    
    public static void Main(string[] args)
    {
      MessageBox(IntPtr.Zero, "Hello from C#!", "Interop Example", 0);
    }
```
## 28. Anonymous Types

Creating unnamed types:csharpCopy code
```
    var person = new { Name = "John", Age = 30 };
    Console.WriteLine($"Name: {person.Name}, Age: {person.Age}");
```
## 29. Tuple

Data structures with a specific number of elements:
```
    (string Name, int Age) person = ("Alice", 30);
    Console.WriteLine($"Name: {person.Name}, Age: {person.Age}"); // Accessing elements using Item1 and Item2
```
## 30. Pattern Matching

Simplifies certain programming tasks:
```
    object obj = new Person { Name = "Bob", Age = 25 };
    
    if (obj is Person { Name: "Bob", Age >= 18 })
    {
      Console.WriteLine("Bob is an adult.");
    }
```
## 31. Local Functions

Encapsulate logic within methods:
```
    public static int Calculate(int number)
    {
      int Factorial(int n)
      {
        if (n == 0) return 1;
        return n * Factorial(n - 1);
      }
    
      return Factorial(number);
    }
    
    public static void Main(string[] args)
    {
      int result = Calculate(5);
      Console.WriteLine($"5! = {result}");
    }
```
## 32. Records

Concise syntax for reference types:
```
    public record Person(string Name, int Age);
    
    public static void Main(string[] args)
    {
      Person person1 = new Person("Alice", 30);
      Person person2 = new Person("Alice", 30);
    
      // Records provide default equality comparison
      if (person1 == person2)
      {
        Console.WriteLine("People are equal");
      }
    }
```
## 33. with Expressions

Non-destructive mutation for records:
```
    var john = new Person("John", 30);
    var jane = john with { Name = "Jane" }; // Non-destructive mutation
```
## 34. Indexers and Ranges

Flexible data access:
```
    int[] arr = {0, 1, 2, 3, 4, 5};
    var subset = arr[1..^1]; // Indexer and range usage
```
## 35. using Declaration

Dispose of IDisposable objects:
```
    using var reader = new StreamReader("file.txt"); // using declaration
```
## 36. Nullable Reference Types (NRTs)

Avoid null reference exceptions:
```
    public class Person
    {
      public string Name { get; set; }
      public int Age { get; set; }
    }
    
    public static void Main(string[] args)
    {
      Person person = new Person() { Age = 30 };
    
      // NRTs require null checks before accessing properties
      if (person?.Name != null)
      {
        Console.WriteLine(person.Name);
      }
      else
      {
        Console.WriteLine("Name is null");
      }
    }
```
## 37. Pattern-Based Using

More patterns in the using statement:
```
    public ref struct ResourceWrapper { /*...*/ } // Resource wrapper
    
    using var resource = new ResourceWrapper(); // Pattern-based using
```
## 38. Property Patterns

Deconstruct objects in pattern matching:
```
    if (obj is Person { Name: "John", Age: var age }) { /*...*/ } // Property pattern matching
```
## 39. Default Interface Implementations

Interfaces with default method implementations:
```
    public interface IPerson { /*...*/ } // Interface with default method
    public class MyClass : IPerson { /*...*/ } // Class implementing interface
```
## 40. Dynamic Binding

Runtime type resolution:
```
    dynamic d = 5; // Dynamic binding
    d = "Hello"; // No compile-time type checking
```
## Conclusion

This structured C# Cheat Sheet concludes with advanced topics and techniques, providing a comprehensive reference for developers aiming to enhance their C# programming skills. For detailed examples and further exploration, refer to the specific sections outlined in this guide. Happy coding!

### Clap if you believe in unicorns & well-structured paragraphs! 🦄📝

### Socials: [C# Publication](https://medium.com/c-sharp-progarmming) | [LinkedIn](https://www.linkedin.com/in/sukhpinder-singh-532284a2/) | [Instagram](https://www.instagram.com/sukhpindersukh/) | [Twitter](https://twitter.com/sukhsukhpinder) | [Dev.to](https://dev.to/ssukhpinder)

![buymeacoffee](https://cdn-images-1.medium.com/max/2000/1*Dpw8-hNGI2fDmosV4E8DVQ.png)

**Inspired By:** [https://zerotomastery.io/cheatsheets/csharp-cheat-sheet/#constants](https://zerotomastery.io/cheatsheets/csharp-cheat-sheet/#constants)
