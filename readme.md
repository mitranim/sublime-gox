## Overview

Syntax for the Go programming language for the Sublime Text editor.

Differences from Sublime's built-in Go syntax:

  * Contextual types. Types are scoped where types are expected. There's no whitelist of "known" types.

  * Better understands the language and its syntax. Better at handling whitespace and comments inside complex forms. Better at handling other nuances. Unlikely to be confused by unusual code style.

  * Vars and consts in the root scope are added to the symbol index and searchable by ⌘R, ⌘⇪R, and `goto_definition`.

  * Supports parenthesized `type (...)` groups, not just `const (...)` and `var (...)`.

  * The first argument to `new` and `make` is scoped as a type.

  * Methods declared inside an `interface` are added to the symbol index, reflecting the fact that they actually exist as functions.

  * Supports embedded structs.

  * Supports inherited interfaces.

  * Supports imaginary number literals.

  * Variable declarations are scoped differently from other variable occurrences.

  * `iota` is scoped only in constant initialization expressions.

  * Symbols in ⌘R are annotated with their origin: `var`, `const`, `type` or `func`.

  * Auto-pairing of backticks.

  * Much more comprehensive tests.

  * All keywords and predeclared identifiers are added to auto-completions by default.

  * Better snippets that don't mess with auto-completion.

Current shortcomings (?):

  * No support for block labels: needs feedback.

  * Fewer meta scopes: needs feedback.

  * No fancy indentation rules.


## Installation

`cd` into Sublime Text's Packages directory. On MacOS, this is usually `"/Users/<user>/Library/Application Support/Sublime Text 3/Packages"`. Find it using Sublime's menu → Preferences → Browse Packages.

Once there, clone the repo:

```sh
cd <package dir>
git clone https://github.com/Mitranim/sublime-gox.git Gox
```


## Usage

Set Sublime to open all Go files as `Gox` (window bottom right → language picker).

Disable the standard Go package to avoid conflicts (⌘⇪P → `Package Control: Disable Package`, or `Preferences: Settings` → `"ignored_packages": ["Go"]`).

Enjoy!


## Pretty Colors

This syntax has some non-standard scopes:

  * `variable.declaration.go`
  * `variable.other.constant.declaration`
  * `constant.numeric.rune.go`
  * `constant.numeric.rune.escape.go`

To make the most out of this syntax, customize your color scheme by adding support for these scopes. For example, in many color schemes, declarations are _italic_ and escapes are **bold**.

I use fairly rich color schemes that support these scopes and more. Feel free to use as a reference or wholesale: https://github.com/Mitranim/sublime-themes.


## TODO

* type switch

* support for `text/template` and `html/template` templates?


## Misc

License: https://en.wikipedia.org/wiki/WTFPL

I'm receptive to suggestions. If this package _almost_ satisfies you but needs changes, open an issue or chat me up. Contacts: https://mitranim.com/#contacts
