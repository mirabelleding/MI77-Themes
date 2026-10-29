# VS Code Color Settings

## Preview
| Themes |  |
|----------------|----------------|
|[MI77_palette_000](themes/palette_000.json)| <img src="pics/palette_000.png" width="300"> |
|[MI77_palette_001](themes/palette_001.json)| <img src="pics/palette_001.png" width="300"> |

## Setup

```text
Command Palette
→ Preferences: Open User Settings (JSON)
```

## UI / Editor

```text
editor.background                 → code editor background
sideBar.background                → Explorer / Search sidebar background
activityBar.background            → activity bar background
panel.background                  → bottom panel background
terminal.background               → terminal background
titleBar.activeBackground         → title bar background
statusBar.background              → status bar background

editor.foreground                 → default editor text
editorLineNumber.foreground       → normal line numbers
editorLineNumber.activeForeground → current line number
editorCursor.foreground           → cursor
editor.selectionBackground        → selected text background
editor.lineHighlightBackground    → current line background
```

## Python Syntax Colors

Under:

```json
"editor.semanticTokenColorCustomizations": {
    "enabled": true,
    "rules": {
        ...
    }
}
```

use:

```text
module:python        → imported Python modules/packages
namespace            → namespaces used by other supported languages

class                → class names
type                 → type names
typeParameter        → generic type parameters

function             → functions
member               → object/class members and many method usages
property             → object properties / attributes

parameter            → function/method parameters
selfParameter        → self
clsParameter         → cls

variable             → normal variables

keyword              → def, class, return, if, for, import, etc.
operator             → operators

string               → strings when semantically classified
number               → numbers when semantically classified
comment              → comments

*.decorator:python   → Python decorator names
```

## TextMate / Fallback Colors

```text
comment                              → comments
string                               → strings
keyword                              → keywords
constant.numeric                     → numbers

support.function.builtin             → built-in functions such as print(), len()
support.type.python                  → built-in Python types such as str, list, dict

punctuation.definition.decorator.python
                                     → @ symbol in decorators
```

## Quick Lookup

```text
Imported Python module    → module:python
Class                     → class
Type                      → type
Function                  → function
Method/member usage       → member
Property/attribute        → property

Parameter                 → parameter
self                      → selfParameter
cls                       → clsParameter
Variable                  → variable

Keyword                   → keyword
Operator                  → operator

Decorator name            → *.decorator:python
Decorator @               → punctuation.definition.decorator.python

String                    → string / TextMate string
Number                    → number / constant.numeric
Comment                   → comment

Built-in function         → support.function.builtin
Built-in Python type      → support.type.python
```

If a color does not change as expected:

```text
Command Palette
→ Developer: Inspect Editor Tokens and Scopes
```