# ESLint configuration for ServiceNow
This configuration of ESLint system properties within ServiceNow extends the baseline configuration with additional ESLint rules that help improve and standardize scripting style within the instance.

The configuration is expanded based on my experience with a goal to keep it well aligned with the most widely adopted style guides for JavaScript, like Prettier and Airbnb coding style guides.
It is not 100% aligned as scripting in ServiceNow is in some aspects specific (for example, wide usage of undeclared, global variables and script include classes).

## Installation
Locate the ESLint system properties in your ServiceNow instance:
- Type "sys_properties.list" in the application filter and press Enter.
- Search for a name containing "eslint".
- Update the properties with the JSON configuration as per the respective file (EcmaScript 5 vs. EcmaScript 12).

# List of custom Rules

## Spacing & Style Rules

### "array-bracket-spacing": ["warn", "never"]
Enforces no spaces inside array brackets. Improves consistency and readability. Aligned with Prettier and Airbnb.

### "brace-style": "warn"
Enforces consistent brace style (e.g., one true brace style). Makes code blocks easier to scan visually.

### "camelcase": ["warn", {...}]
Enforces camelCase variable names with exceptions. Encourages consistent naming and improves code readability. The exceptions are for object properties, which are widely used in ServiceNow to access field values, and for global variables used in ServiceNow, like g_form.

### "comma-spacing": "warn"
Ensures a space after a comma. Helps avoid visual clutter.

### "comma-style": "warn"
Enforces comma position. Makes diffing and reading lists cleaner.

### "computed-property-spacing": "warn"
Enforces spacing in computed property brackets. Avoids inconsistent patterns.

### "curly": ["warn", "multi-line"]
Requires curly braces for multiline if, while statements. Reduces bugs from misinterpreted blocks.

### "func-call-spacing": ["warn", "never"]
Disallows space between function name and call. Matches standard JS style.

### "key-spacing": "warn"
Controls spacing around object literal keys. Improves alignment and readability in object declarations.

### "keyword-spacing": "warn"
Ensures space after keywords like if. Makes control structures more readable.

### "lines-around-comment": "warn"
Enforces empty lines around comments to separate them from code. Helps comments stand out.

### "space-before-blocks": "warn"
Requires space before { in functions and loops. Improves consistency and readability.

### "space-infix-ops": "warn"
Requires spaces around infix operations (a + b). Prevents visually dense code.

## Code Safety & Best Practices

### "new-cap": "error"
Requires capitalized names for constructor functions (new Person()). Avoids misuse of constructors.

### "new-parens": "error"
Requires () after "new" calls, even with no args (new Person()). Prevents confusion when omitting the parentheses is inconsistent with the rest of the language.

### "no-array-constructor": "error"
Disallows "new Array()" because it behaves inconsistently.

### "no-eval": "error"
Disallows "eval()", which is dangerous and can lead to injection or performance issues.

### "no-extend-native": "error"
Prevents changing native objects like "Array.prototype", which can break other code.

### "no-floating-decimal": "warn"
Warns about ".5" instead of "0.5". Reduces ambiguity and increases clarity.

### "no-implied-eval": "error"
Disallows setTimeout or similar that behaves like "eval".

### "no-with": "error"
"with" is disallowed in strict mode and leads to unpredictable scope. It should always be avoided.

## Code Readability & Maintainability
### "no-lonely-if": "warn"
Flags single "if" blocks inside "else" - suggest merging for cleaner logic.

### "no-multi-spaces": "warn"
Prevents unnecessary spacing. Keeps code compact and clean.

### "no-multiple-empty-lines": "warn"
Prevents too many blank lines, which can waste vertical space and obscure logic.


