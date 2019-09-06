# Review checklist

Read this article http://javascript.info/ninja-code. If you find any of the patterns from the article then there is something to give feedback on!

## General
- [ ] Is everything indented properly.
- [ ] How is the folder structure of the application.
- [ ] How are the files named and does that make sense.

## HTML
- [ ] Are the class names and id’s semantic and do they describe the content of the tag?
- [ ] Has id’s and class names been used correctly.
- [ ] Has the correct tag been used. Fx is main, header, footer, section, nav used properly.
- [ ] Is the html correctly implemented. 
- [ ] Are there unnecessary wrappers?
- [ ] Has kebab-case been used?
- [ ] Has alt tags been written for images.

## CSS
- [ ] Is the css imported using the style tag.
- [ ] Are there unused selectors.
- [ ] Are there lots of fixed pixel values. This could affect responsive layouts.
- [ ] Try to avoid absolute positioning as this tends to break responsive layouts.
- [ ] Use flexbox over floats.
- [ ] Avoid using `!important` statements.
- [ ] Avoid inline styles
- [ ] Consistent naming and grouping of css-classes (see naming conventions below)
- [ ] CSS selectors are only as specific as they need to be

## Javascript

### Comments
 - [ ] Are comments written in an comprehensible english and are they free from spelling and grammar mistakes?
 - [ ] Are functions described with comments?
 - [ ] Avoid "stating the obvious" in comments - the "how?" (i.e. `const button; // This is a button`)
 - [ ] Focus on using comments to relay business logic that may not be obvious from reading the code - the "why?".
 - [ ] Break long comments onto multiple lines and only place short comments on the right side of code (and only if the agreed code style allows for it - if in doubt put all comments above the code)
 - [ ] Regular expressions are not obvious to read for even many experienced programmers. If you see a regular expression make sure there is a comment describing what the authors intention is.
 - [ ] Avoid committing commented out code.

### Variables
- [ ] Are variables declared at the top of the functions scope rather than scattered over the file?
- [ ] Have const and let been used instead of var? Remember to use const if variable is never re-assigned.
- [ ] Does the variable naming make sense? (see section below about naming conventions)
- [ ] Minimize the use of global variables and variables that are shared across functions. Instead, pass the variable from one function to the next.

### Functions
- [ ] Does the function name make sense? (see section below about naming conventions)
- [ ] Does the function do more than the name suggest? (solution: split into multiple functions)
- [ ] Do you see repeated code throughout the file? (solution: split into multiple functions)
- [ ] Is the function long and convoluted? Can it be simplified or split into multiple functions? Ideally functions should only have one responsibility.
- [ ] Does a function have any side effects (i.e. is it modifying state outside of its own local scope)?
- [ ] Are the inputs an outputs (parameters and return values) appropriate for what it does?

### Naming conventions
- [ ] All names should be in english and look out for spelling mistakes.
- [ ] Try to understand the domain language and pick names that reflect the domain.
- [ ] Variable and function names should be written in camelCase.
- [ ] Javascript classes should be written in PascalCase.
- [ ] CSS classes should be in kebab-case and cannot start with a number.
- [ ] Common practice is to prefix boolean names with `is` (i.e. `isSet`).
- [ ] Prioritize readability over writeability. Modern code editors and IDEs are generally good at autocompleting so you can be a bit more generous with the characters if it fosters readability (i.e. `mapStateToProps()` over `mapStProp()`)
- [ ] Never do single character functions like `y()` or `b()`. This is not algebra!
- [ ] Be consistent. If don't have one function spelled `setColour()` and another ` getColor()` (british and american spelling).
- [ ] Think ahead and try to generalize as much as possible. If a function is simply summing a list of numbers and you are planning to use it for a shopping cart, consider calling the function `sumNumbers()` rather than `calculateShoppingCartTotal()`. If it does other things strictly related to a shopping cart (i.e. calculate taxes and shipping), you should of course call it `calculateShoppingCartTotal()` so it is clear what it does.

### More things to look out for in Javascript...
- [ ] Is triple equality used?
- [ ] Avoid multiple nested if/else blocks.
- [ ] Are ES6/ES7 like `.map()`, `.filter()` and `.reduce()` used over regular `for()` and `while()` loops?
- [ ] Prefer destructuring assignments over trivial variable declarations.
- [ ] Remember to check that values are set before referencing them?
- [ ] Use template literals over `"hard" + " " + "to read" + " string concatenation"`.
- [ ] Is there any dead code?
- [ ] If npm packages are no longer used, are they being removed from `package.json`?
- [ ] Avoid committing code with `console.log()`-statements
- [ ] If external libraries are used, vet them thoroughly: Is the library maintained? Is the issues tab on github filled with unanswered questions? Does the library solve the problem well without adding unecessary overhead? Is it well documented?

### Git
- [ ] Make sure no sensitive information is published to git (i.e. API keys, passwords and similar). These should be stored in env variables and the `.env` file should be in `.gitignore`.
- [ ] Make sure no dist folders, editor/IDE files, database dumps or large pictures or videos are checked into git. 
- [ ] Commits are small and divided into logical parts.
- [ ] Commits messages are small and understandable.
- [ ] Use branches for new features.
