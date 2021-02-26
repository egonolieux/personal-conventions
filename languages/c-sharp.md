# C# coding conventions

## Todo

- Always use C#-style comment blocks.
- C#8-style methods.
- No namespace references in code (use `using` instead).

## Repository guidelines

- **Never** store credentials of any kind in the repository. Always refer to them externally.
- **Never** commit code that does not build to the repository.
- For work in process (generally code that does not build), a separate branch using the `-wip` suffix can be used.

## Coding standards

In general, follow the official C# language conventions: <https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/inside-a-program/coding-conventions>. C# related issues are checked by StyleCop at build-time. Below is a summary of general rules and rules that are not covered by StyleCop that you should aim to follow. In case of uncertainty, you can look at the existing code for guidance.

### Best practices

- Avoid throwing exceptions from getters (unless the argument is invalid).
- Methods that do not reference instance members (`this`) should be declared as `static` (pure function).

### Naming

- Boolean naming should always reflect a question to which `true` or `false` can be answered; e.g., `hasValue` and `isValid`.
- Hash maps (dictionaries) should indicate which values are being mapped, and should have a `Map` suffix, e.g., `expansionNameToCardsMap`.
- Use descriptive names. Variable names like `res`, `x` or `temp` are meaningless and lack any context.

### Structure

- Class members should be ordered by their type: constants, static readonly fields, readonly fields, fields, static constructor, constructors, events, properties and methods. A blank line should be used between members. Constants, static readonly fields, readonly fields and fields can be declared without using blank lines, unless one or more members of the same type span multiple lines.

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

- Classes should be declared as `sealed` by default, unless they are specifically designed to be inherited from.

- Closing parentheses should not have preceding whitespace (SA1009), unless the parenthesis is used to close a multi-line expression.

    ```cs
    // Allowed.

    var dateTime = new DateTime(
        year: 1,
        month: 5,
        day: 2
    );

    var dateTime = new DateTime(1, 2, 3);

    // Not allowed.

    var dateTime = new DateTime(1, 2, 3 );
    ```

- If a single argument is spread over multiple lines when using multi-line arguments, all lines following the first line should be indented.

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

- Multi-line constructor signatures, method signatures and `if` statements should have its closing parenthesis at the end of the last line.

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

- Parentheses should be put around ternary operator expressions that contain 2 or more boolean expressions.

    ```cs
    // Allowed.
    return (5 < 10) ? "a" : "b";

    // Allowed.
    return isValid ? "yes" : "no";

    // Not allowed.
    return 5 < 10 ? "a" : "b";
    ```

- When inheriting from certain classes or interfaces, their declarations should be ordered alphabetically.

- When using multi-line arguments for method or constructor calls, named arguments should be used.

- When using multi-line arguments, the closing parenthesis should be on the same indentation level as the opening statement.

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
