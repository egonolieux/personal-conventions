# C# conventions

- Always use C#-style comment blocks.
- Use lambda expressions for method and property bodies if possible.
- No namespace references must be used in-code (use `using` instead), unless there is a conflict.
- Named arguments must be used if the meaning of the passed value is unclear or ambiguous.
- Put generic constraints on a separate line with indentation.
- Put calls to `base` (or `this`) constructors on a separate line with indentation.
- Accept the most general type possible and return the most specific type possible.
- The API cannot expose specific implementations if an interface is available, unless private.
- Error/exception messages must be written in the past tense, unless it describes a failed precondition or similar (present tense).
- Prefer making a safe copy of readonly collections when passed as an argument to a class. This prevents mutations to the collection from the side of the caller. Optional for records.

## Coding standards

In general, follow the official C# language conventions: <https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/inside-a-program/coding-conventions>. 

### Best practices

- Avoid throwing exceptions from getters (unless the argument is invalid).
- Methods that do not reference instance members (`this`) must be declared as `static` (pure function).

### Structure

- Class members must be ordered by their type: constants, static readonly fields, readonly fields, fields, static constructor, constructors, events, properties and methods. A blank line must be used between members. Constants, static readonly fields, readonly fields and fields can be declared without using blank lines, unless one or more members of the same type span multiple lines.

    ```cs
    public const int Age = 25;
    public const string Name = "Foo";

    public static readonly List<int> Numbers = new List<int> { 1, 2, 3 };

    public static readonly List<int> Titles = new List<string>
    {
        "Some title",
        "Another title",
        "Yet another title",
    };

    private readonly int readonlyField;
    private readonly string otherReadonlyField;
    private int field;
    private string otherField;

    //...
    ```

- Declare classes as `sealed` by default, unless they are specifically designed to be inherited from.

- If a single argument is spread over multiple lines when using multi-line arguments, all lines following the first line must be indented.

    ```cs
    this.Method(
        parameter1: "someValue",
        parameter2: "otherValue",
        parameter3:
            "some very long string " +
            "that is" +
            "split over multiple lines."
    )
    ```

- Multi-line constructor signatures, method signatures and `if` statements must have their closing parentheses at the end of the last line.

    ```cs
    public ClassConstructor(
        string name,
        int age,
        string address,
        string postalCode)
    {
        // ...
    }

    public SomeMethod(
        string parameter1,
        string parameter2,
        string parameter3)
    {
        // ...
    }

    if (
        someCondition &&
        someOtherCondition)
    {
        // ...
    }
    ```

- Put parentheses around ternary operator expressions that contain 2 or more boolean expressions.

    ```cs
    // Allowed.
    return (5 < 10) ? "a" : "b";

    // Allowed.
    return isValid ? "yes" : "no";

    // Not allowed.
    return 5 < 10 ? "a" : "b";
    ```

- When inheriting from certain classes or interfaces, their declarations must be ordered alphabetically.

- When using multi-line arguments, the closing parenthesis must be on the same indentation level as the opening statement.

    ```cs
    // Allowed.
    this.Method(
        parameter1: "someValue",
        parameter2: "otherValue"
    );

    // Not Allowed.
    this.Method(
        parameter1: "someValue",
        parameter2: "otherValue");
    ```
