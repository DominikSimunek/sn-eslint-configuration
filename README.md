# ESLint configuration for ServiceNow
This configuration of ESLint system properties within ServiceNow extends the baseline configuration with additional ESLint rules that help improve and standardize scripting style within the instance.

The configuration is expanded based on my experience with a goal to keep it well aligned with the most widely adopted style guides for JavaScript, like Prettier and Airbnb coding style guides.
It is not 100% aligned as scripting in ServiceNow is in some aspects specific (for example, wide usage of undeclared, global variables and script include classes).

## Installation
Locate the ESLint system properties in your ServiceNow instance:
- Type "sys_properties.list" in the application filter and press Enter.
- Search for a name containing "eslint".
- Update the properties with the JSON configuration as per the respective file (EcmaScript 5 vs. EcmaScript 12).

## List of custom Rules
### array-bracket-spacing
Enforces no spaces inside array brackets. Improves consistency and readability. Aligned with Prettier and Airbnb.

### brace-style
Enforces consistent brace style (e.g., one true brace style). Makes code blocks easier to scan visually.
