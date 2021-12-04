# General language conventions

## Capitalization

- When using camel or pascal case, only capitalize the first letter of acronyms for readability, e.g., `HtmlNode` instead of `HTMLNode`.

## Variable naming

- For "regular" variable names, the conventions for specific categories of variables (see below) cannot be used.
- Variable names must be as descriptive as possible.

### Booleans

Boolean variable names must either be prefixed by a conjugated verb such as `is`, `has` or `can`, or be written in imperative form such as `enable` or `doWork`. The imperative form can only be used over the conjugated verb form if the boolean variable indicates a command of some kind and does not relate to a property. An example of such case is an `enable` variable of a function/method called `toggle`.

The imperative form might conflict with function/method names. For cases where the conventions regarding (first-class) function naming conflicts cannot be applied, a `Var` suffix must be used, e.g., `enableVar`.

### First-class functions

A function implies an action, which means that a verb must be used for the variable name, such as `calculateSomething` or `doSomeAction`. If the function variable name conflicts with a boolean variable name, the `Fn` suffix must be used, e.g., `doSomeActionFn`.

Notable exceptions to these rules are:

- Callback functions, which are suffixed by `Callback`, e.g., `successCallback`.
- Event listeners, which are prefixed by `on`, e.g., `onButtonClick`.

### Arrays, lists and sets

Array, list and set variable names must be written in plural form, e.g., `items` and `stringValues`. If the same values are used within the same scope for different collection types (an array, list or set), an `As<Type>` suffix must be used, e.g., `itemsAsSet` and `itemsAsList`.

### Hash maps

Hash map variable names must indicate which values are being mapped, and must have a `Map` suffix, e.g., `someValueToOtherValueMap`.
