# Autocorrector

Rubocop comes with the following command line tool that can autocorrect offenses:
```
$ rubocop -a
```
This tool can be combined with `--only` to work for a single cop if needed. For example,
```
$ rubocop --only Style/StringLiterals -a
```

## Using Autocorrector
The Rubocop Documentation advises to use this autocorrector tool ***with caution*** as it can be very destructive depending on the offense.

Here the following Rubocop rules that were tested and determined to be safe to use with the autocorrector tool:

- Style/StringLiterals
- Style/SpaceAroundOperators
- Style/SpaceInsideHashLiteralBraces
- Style/Tab
- Style/HashSyntax
- Style/SpaceInsideBlockBraces
- Style/IndentationWidth
- Style/BracesAroundHashParameters
- Style/ExtraSpacing
- Style/EmptyLinesAroundAccessModifier
- Style/SymbolProc
- Style/SpaceInsideParens
- Style/MutableConstant
- Style/IndentationConsistency
- Style/SpaceAfterComma
- Style/AlignParameters
- Style/SpaceBeforeBlockBraces
- Style/SpaceAfterComma
- Style/AlignHash
- Style/TernaryParentheses
