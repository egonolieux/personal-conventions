# C# conventions

In general, follow the official C# language conventions: <https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/inside-a-program/coding-conventions>. For static code analysis, Roslynator can be used.

- Accept the most general type possible and return the most specific (interface) type possible.
- Always use C#-style comment blocks.
- Avoid throwing exceptions from getters (unless the argument is invalid).
- Declare methods that don't reference instance members (`this`) as `static` (pure function).
- Namespace references cannot be used in-code (use `using` instead), unless there is a conflict.
- The API cannot expose specific implementations if an interface is available, unless private.
- Use lambda expressions for constructor, method, and property bodies if possible.
- Use named arguments if the meaning of the passed value is unclear or ambiguous.
- Write error/exception messages in the past tense, unless it describes a failed precondition or similar (present tense).

## Structure

- Declare classes as `sealed` by default, unless they are specifically designed to be inherited from.

- If a single argument is spread over multiple lines when using multi-line arguments, indent all lines following the first line.

    ```cs
    this.Method(
        parameter1: "someValue",
        parameter2: "otherValue",
        parameter3:
            "some very long string " +
            "that is" +
            "split over multiple lines."
    );
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

- Order class members by their type: constants, static readonly fields, (readonly) fields, static constructor, constructors, events, properties and methods. A blank line must be used between members. Constants, static readonly fields, readonly fields and fields can be declared without using blank lines, unless one or more members of the same type span multiple lines.

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
    private readonly Lazy<string> lazyName;

    //...
    ```

- Put calls to `base` (or `this`) constructors on a separate line with indentation.

- Put generic constraints on a separate line with indentation.

- Put parentheses around ternary operator expressions that contain 2 or more boolean expressions.

    ```cs
    // Correct.
    return (5 < 10) ? "a" : "b";

    // Correct.
    return isValid ? "yes" : "no";

    // Incorrect.
    return 5 < 10 ? "a" : "b";
    ```

- When inheriting from certain classes or interfaces, order their declarations alphabetically.

- When using multi-line arguments, put closing parentheses on the same indentation level as the opening statement.

    ```cs
    // Correct.
    this.Method(
        parameter1: "someValue",
        parameter2: "otherValue"
    );

    // Incorrect.
    this.Method(
        parameter1: "someValue",
        parameter2: "otherValue");
    ```
