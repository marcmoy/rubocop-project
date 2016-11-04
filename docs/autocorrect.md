# Autocorrector

Rubocop comes with the following command line tool that can autocorrect offenses:
```
$ rubocop -a
```
This tool can be combined with `--only` to work for a single cop if needed. For example,
```
$ rubocop --only Style/StringLiterals -a
```

## Cops Autocorrected
The Rubocop Documentation advises to use this autocorrector tool ***with caution*** as it can be very destructive depending on the offense.

*NOTE:* The use of this autocorrector needs to be carefully thought out before applying to the existing code base. Some variables needs to be worked out, such as:

- Which cops are safe to use
- What order should the autocorrect script run these cops
- How to split up git commits for this huge change

## Tested Autocorrect Cops

Here the following Rubocop rules that were tested and determined to be safe to use with the autocorrector tool:

##### Cops with more than 20 offenses
- [x] Style/SpaceAroundOperators
- [x] Style/SpaceInsideHashLiteralBraces
- [x] Style/Tab
- [x] Style/HashSyntax
- [x] Style/SpaceInsideBlockBraces
- [x] Style/IndentationWidth
- [x] Style/BracesAroundHashParameters
- [x] Style/ExtraSpacing
- [x] Style/EmptyLinesAroundAccessModifier
- [x] Style/SymbolProc
- [x] Style/SpaceInsideParens
- [x] Style/MutableConstant
- [x] Style/IndentationConsistency
- [x] Style/SpaceAfterComma
- [x] Style/AlignParameters
- [x] Style/SpaceBeforeBlockBraces
- [x] Style/SpaceAfterComma
- [x] Style/AlignHash
- [x] Style/TernaryParentheses

##### Cops with less than 20 offenses
- [x] Style/BlockEndNewline
- [x] Lint/BlockAlignment
- [x] Style/CommentIndentation
- [x] Style/ClosingParenthesisIndentation
- [x] Style/Semicolon (doesn't fix all offenses, two needs to be changed manually)
- [x] Style/StringLiteralsInInterpolation
- [x] Style/SpaceAfterColon
- [x] Performance/RangeInclude
- [x] Style/MethodCallParentheses
- [x] Style/NestedParenthesizedCalls
- [x] Style/ParenthesesAroundCondition
- [x] Style/RedundantParentheses
- [x] Lint/UnifiedInteger
- [x] Style/InfiniteLoop
- [x] Style/MethodDefParentheses
- [x] Style/SpaceInsideStringInterpolation
- [x] Style/UnneededInterpolation
- [x] Style/EmptyLineBetweenDefs
- [x] Style/MultilineArrayBraceLayout
- [x] Style/MultilineIfThen
- [x] Style/RedundantReturn
- [x] Style/SpaceAfterMethodName
- [x] Style/SpaceAroundKeyword
- [x] Style/SpaceInsideRangeLiteral
- [x] Style/ZeroLengthPredicate
- [x] Style/AccessModifierIndentation
- [x] Style/AndOr
- [x] Style/PreferredHashMethods
- [x] Style/RedundantBegin

## Cops Not Autocorrected
This a list of cops that were determined to be destructive that should not be autocorrected and would need to be fixed manually:

- [ ] Metrics/LineLength
- [ ] Lint/UselessAssignment
- [ ] Lint/UnusedMethodArgument
- [ ] Lint/UnusedBlockArgument
- [ ] Style/BlockDelimiters
- [ ] Style/MultilineBlockLayout
- [ ] Lint/ShadowingOuterLocalVariable
- [ ] Metrics/PerceivedComplexity
- [ ] Style/BarePercentLiterals
- [ ] Style/ClassAndModuleCamelCase
- [ ] Style/MethodName
- [ ] Style/UnlessElse
- [ ] Lint/DuplicateMethods
- [ ] Performance/FixedSize
- [ ] Style/MethodMissing
- [ ] Lint/UselessAccessModifier
- [ ] Lint/UselessComparison
- [ ] Metrics/PerceivedComplexity
- [ ] Lint/RescueException
- [ ] Style/IdenticalConditionalBranches
- [ ] Lint/IneffectiveAccessModifier
