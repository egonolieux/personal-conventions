# General language conventions

## Capitalization

- When using camel or pascal case, only capitalize the first letter of acronyms for readability, e.g., `HtmlNode` instead of `HTMLNode`.

## Variable naming

- For "regular" variable names, the conventions for specific categories of variables (see below) cannot be used.
- Variable names must be as descriptive as possible.

### Booleans

Boolean variable names must either be prefixed by a conjugated verb such as `is`, `has` or `can`, or be written in imperative form such as `enable` or `doWork`. The imperative form can only be used over the conjugated verb form if the boolean variable indicates a command of some kind and does not relate to a property. An example of such case is an `enable` variable of a function/method called `toggle`.

### Functions

A function/method implies an action, which means that a verb must be used for the variable name, such as `calculateSomething` or `doSomeAction`. If the function variable name conflicts with a boolean variable name, the `Fn` suffix must be used, e.g., `doSomeActionFn`.

A notable exception to these rules are callback functions in general, which can simply be suffixed by `Callback`, e.g., `successCallback`.

### Arrays, lists and sets

Array, list and set variable names must be written in plural form, e.g., `items` and `stringValues`. If the same values are used within the same scope for different collection types (an array, list or set), an `As<Type>` suffix must be used, e.g., `itemsAsSet` and `itemsAsList`.

### Hash maps

Hash map variable names must indicate which values are being mapped, and must have a `Map` suffix, e.g., `someValueToOtherValueMap`.
