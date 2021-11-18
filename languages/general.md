# General language conventions

## Capitalization

- Only capitalize the first letter of acronym variables for readability, e.g., `HtmlNode` instead of `HTMLNode`.

## Variable naming

- Variable names must be as descriptive as possible.
- For "regular" variable names, the conventions for boolean and function variable names cannot be used.

### Booleans

Boolean variable names must either be prefixed by a conjugated verb such as `is`, `has` or `can`, or be written in imperative form such as `enable` or `doWork`. The imperative form can only be used over the conjugated verb form if the boolean variable indicates a command of some kind and does not relate to a property. An example of such case is an `enable` variable of a function/method called `toggle`.

### Functions
