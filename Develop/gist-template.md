# Regex Tutorial: Understanding the Email Pattern

## Introduction

In this tutorial, I'll be breaking down a regex used to validate email addresses. Regex is tool helpful with matching and validating string patterns.
## Summary

The regex pattern we'll be looking at is used to validate whether a string is a valid email address format. This pattern matches email addresses of the format `username@domain.extension`. Each part has specific criteria:
- The **username** part allows letters, numbers, underscores, periods, and hyphens.
- The **domain** allows letters and numbers.
- The **extension** is between 2 and 6 characters long.

Here's the regex I'll be explaining: <br>

/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

## Regex Components

### Anchors

- **`^`** and **`$`** are called **anchors**. They specify that the regex should match the entire string from start to end.
  - `^` asserts that the match must start at the beginning of the string.
  - `$` asserts that the match must end at the end of the string.
  
  Together, `^` and `$` make sure the regex matches the entire input as a complete email address, with no extra characters before or after.

### Quantifiers

Quantifiers define the number of times an element in a regex should appear.

- **`+`** is a quantifier that means “one or more” of the preceding element.
  - In `([a-z0-9_\.-]+)`, the `+` applies to `[a-z0-9_\.-]`, meaning the username part of the email must have at least one character and can have many more.
- **`{2,6}`** specifies a range, meaning the preceding element should appear between 2 and 6 times.
  - In `([a-z\.]{2,6})`, `{2,6}` applies to `[a-z\.]`, meaning the email extension (like `.com`) must have between 2 and 6 characters.

### Character Classes

Character classes specify which characters are allowed in each part of the regex.

- **`[a-z0-9_\.-]`** allows lowercase letters (`a-z`), numbers (`0-9`), underscores (`_`), periods (`.`), and hyphens (`-`).
  - This character class is used in `([a-z0-9_\.-]+)`, allowing a variety of characters in the username.
- **`\d`** is shorthand for any digit (0–9). In `([\da-z\.-]+)`, `\d` allows numbers in the domain part.
- **`[a-z\.]`** allows only lowercase letters and periods.
  - In `([a-z\.]{2,6})`, this class restricts the email extension to letters and periods, like in “com” or “co.uk.”

### Grouping and Capturing

Parentheses `()` create **capturing groups**, which group parts of the regex for easier handling and allow us to capture specific parts of a match. This regex uses three capturing groups:

1. **`([a-z0-9_\.-]+)`**: The first capturing group matches the **username** part of the email. It allows letters, numbers, underscores, periods, and hyphens, as specified by `[a-z0-9_\.-]`.
2. **`([\da-z\.-]+)`**: The second capturing group matches the **domain** part of the email. This group allows letters, numbers, periods, and hyphens.
3. **`([a-z\.]{2,6})`**: The third capturing group matches the **extension** part of the email, such as "com" or "org". It allows letters and periods and restricts the length to 2-6 characters.

### Author

Created by Josh! [Github](github.com/authorixed)

