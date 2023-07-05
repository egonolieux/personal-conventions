# Conventions to be classified

This document contains various personal conventions that have been established, but still need to be properly classified.

- Front end: `offset` in variable names is reserved for `top`/`right`/`bottom`/`left`.
- Front end: `rem` vs `em`: Only use `em` for text (and inline elements in general).
- Front end: `spacing` in variable names is reserved for the concept of spacing, if `margin`, `padding` or `top`/`right`/`bottom`/`left` are not an exact fit.
- General: *Title* vs *heading*: *Title* is specific, while *heading* is more generic. A title is a heading that uniquely belongs to a single piece of content, while multiple headings can be used within the same context. For example, a modal has a title, and a dropdown can have multiple headings within the list of options.
- General: Code in comments: Use backticks and use full class paths. For functions and methods append `()` regardless of the parameters. For example, `Class::method()`.
- General: Convention regarding PHPDoc/JSDoc variable order: `string|number|float|bool|...etc`.
- General: Keep `try` blocks as small as possible and only catch specific exceptions if possible.
- General: Optional boolean parameters should be named in such a way that the default value can be set to `false`, unless the naming for a default value of `true` is more natural from a language point of view.
- General: String interpolation: Only if literal string besides interpolated variables, otherwise simple concat
- General: Wrap multi-line function rules: Only recommended for chained/fluent api, or if readability improved. Also if the intermediate getter has a lot of arguments.
- General: `get()` vs `find()`: `get()` generally means immediately available (also applies to lazy loaded value getters). `find()` takes time.
- HTML: Plain text in templates: Let text naturally wrap; don't insert new lines, unless `<a>` tag.
- JavaScript: Component guidelines: Constructor should perform DOM read operations, other methods only dom write operations. This is to ensure DOM batching.
- Less (or any other language?): No `and` or `or` in class names, reserved for variables only.
- PHP/Twig: Use string interpolation, then sprintf/format, then concat.
- PHP: Attributes: Don't leave out the first parameter name if each on new line.
- PHP: Constructor promotion rules: Only mixed if passing to parent constructor, no promotion if other fields, unless lazy/cached.
- PHP: Hash set convention: Use an array with the value as key that maps to a `true` boolean: For example `cardNumberToBoolMap`.
- PHP: Maps to self convention: For example `cardNumberSelfMap`.
- PHP: PHPDoc rules: Only strictly necessary, if no type hint possible or to extend on existing types like array.
- SQL: JOIN alias comparison/equality order: *from* alias => *to* alias.
- SQL: JOIN order: Work from the FROM alias inwards, following the column order, for example: `card`, `card.expansion`, `expansion.series`, `card.variants`, ...
