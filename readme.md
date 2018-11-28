## Overview

Syntax for the Go programming language for the Sublime Text editor. Intended to replace Sublime's built-in. Pending pull request: https://github.com/sublimehq/Packages/pull/1662.

Differences from Sublime's built-in:

  * Contextual types. Types are scoped where types are expected. There's no whitelist of "known" types.

  * Better understands the language and its syntax. Better at handling whitespace and comments inside complex forms. Better at handling other nuances. Unlikely to be confused by unusual code style.

  * Vars and consts in the root scope are added to the symbol index and searchable by ⌘R, ⌘⇪R, and `goto_definition`.

  * Supports parenthesized `type (...)` groups, not just `const (...)` and `var (...)`.

  * The first argument to `new` and `make` is scoped as a type.

  * Methods declared inside an `interface` are added to the symbol index, reflecting the fact that they're actually accessible as methods on the interface type.

  * Supports embedded structs.

  * Supports inherited interfaces.

  * Supports imaginary number literals.

  * Variable declarations are scoped differently from other variable occurrences.

  * `iota` is scoped only in constant initialization expressions.

  * Symbols in ⌘R are annotated with their origin: `var`, `const`, `type` or `func`.

  * Auto-pairing of backticks.

  * Much more comprehensive tests.

  * All keywords and predeclared identifiers are added to auto-completions by default.

  * Fewer and better snippets that don't mess with the typing flow or regular auto-completions.

  * Slightly better indentation rules, optimized for typing.

  * Type keywords (`type`, `interface`, etc.) are scoped differently from type names.

Current shortcomings (?):

  * Fewer meta scopes: needs feedback.

  * No support for block labels: needs feedback.

Screenshot before-after:

![screen shot 2018-07-28 at 10 54 50](https://user-images.githubusercontent.com/4263831/43354424-09f502be-9255-11e8-9d6f-8c0b37e98809.jpg)

Screenshot of symbol index before-after:

![screen shot 2018-07-28 at 10 54 55](https://user-images.githubusercontent.com/4263831/43354428-260781ac-9255-11e8-9631-4920b6473e3b.jpg)

(Many other differences didn't fit into the screenshots. This uses my Cloud color scheme, available at https://github.com/mitranim/sublime-themes.)


## Installation and Usage

`cd` into Sublime Text's Packages directory. On MacOS, this is usually `"/Users/<user>/Library/Application Support/Sublime Text 3/Packages"`. Find it using Sublime's menu → Preferences → Browse Packages.

Once there, clone the repo:

```sh
cd <package dir>
git clone https://github.com/mitranim/sublime-gox.git Go
```

Note: the syntax is called `Go`, exactly the same as the default. Disable the default Go package to avoid conflicts: ⌘⇪P → `Package Control: Disable Package`, or `Preferences: Settings` → `"ignored_packages": ["Go"]`.

Enjoy!


## Scopes

This syntax differentiates variable declarations from normal variable occurrences. Declarations receive these non-standard scopes:

  * `variable.declaration.go`
  * `variable.other.constant.declaration`

To make full use of this feature, extend your color scheme, adding support for these scopes. Alternatively, check out my custom color schemes. Feel free to use them as-is, or as reference for implementing your own: https://github.com/mitranim/sublime-themes.


## TODO

* type switch

* support for `text/template` and `html/template` templates?

* detect data structure literals

  * detect type names preceding a data literal
  * a data literal is recursive: `{}` without a type name is another literal
  * detect field names

* outside of data structure literals, detect block labels

## Misc

License: https://en.wikipedia.org/wiki/WTFPL

I'm receptive to suggestions. If this package _almost_ satisfies you but needs changes, open an issue or chat me up. Contacts: https://mitranim.com/#contacts
