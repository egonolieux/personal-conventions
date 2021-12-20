# General language conventions

## Structure

- Avoid nesting `if` statements; prefer to return early when a precondition fails.
- Use trailing commas if the language supports it.
- Insert a blank line between a `return` statement and other statements or expressions.

## Naming

- For "regular" variable names, the conventions for specific categories of variables (see below) cannot be used.
- Variable names must be as descriptive as possible.
- When using camel or pascal case, only capitalize the first letter of acronyms for readability, e.g., `HtmlNode` instead of `HTMLNode`.

### Functions

A function implies an action, which means that a verb must be used for its name, such as `calculateSomething` or `doSomeAction`.

#### Special cases

- **Event listeners**: Use an `on` suffix, e.g., `onButtonClick`. The general verb form is not required.
- **Callbacks**: Use a `callback` suffix, e.g., `successCallback`. The general verb form is not required.
- **General prefixes and suffixes**: General prefixes and suffixes are allowed as long as the function name also uses the general verb form, e.g., `innerShowDialog` and `doSomeActionWrapper`.

#### Naming conflicts

In some cases, the function name might conflict with other variable names, such as imperative booleans. In such cases, the `fn` suffix must be used, e.g., `doSomeActionFn` in contrast to the `doSomeAction` boolean.

### Boolean variables

Boolean variable names must either be prefixed by a conjugated verb such as `is`, `has` or `can`, or be written in the imperative form such as `enable` or `doWork`. The imperative form can only be used over the conjugated verb form if the boolean variable indicates a command of some kind, and does not relate to a property. An example of such case is an `enable` variable of a function called `toggle`.

#### Naming conflicts

In some cases, the imperative form might conflict with function names. See the *Functions* section on how to resolve these conflicts.

### Arrays, list and set variables

Array, list and set variable names must be written in plural form, e.g., `items` and `stringValues`. If the same values are used within the same scope for different collection types (an array, list or set), an `as<type>` suffix must be used, e.g., `itemsAsSet` and `itemsAsList`.

### Hash map variables

Hash map variable names must indicate which values are being mapped, and must have a `map` suffix, e.g., `someValueToOtherValueMap`.
