### Objective
Develop a Ruby linter to help guide students and teachers to write Ruby code with best coding practices in mind.

# Study
The [`appacademy/curriculum`](https://github.com/appacademy/curriculum) repository was analyzed in this study. Rubocop offenses can be counted using the following `rubocop` command line tool:
```
rubocop --format offenses
```

## Default Rubocop
Before installing any `.rubocop.yml` file, the `default` rubocop settings were first tested against the current entire code base.

Here are the results:
```
25080  Style/StringLiterals
5078   Metrics/LineLength
2407   Style/SpaceAroundOperators
915    Style/SpaceInsideHashLiteralBraces
775    Style/Documentation
614    Style/Tab
454    Style/HashSyntax
364    Style/TrailingWhitespace
361    Style/IndentArray
337    Style/WordArray
278    Style/NumericLiterals
250    Style/TrailingCommaInLiteral
202    Style/RedundantSelf
154    Style/SpaceInsideBlockBraces
135    Style/EmptyLinesAroundBlockBody
122    Metrics/MethodLength
112    Style/IndentationWidth
111    Style/ExtraSpacing
104    Style/BracesAroundHashParameters
88     Style/EmptyLines
79     Lint/UselessAssignment
75     Style/ClassAndModuleChildren
68     Style/FirstParameterIndentation
67     Style/EmptyLinesAroundAccessModifier
58     Style/EmptyLinesAroundClassBody
56     Style/TrailingBlankLines
51     Style/MultilineMethodCallBraceLayout
47     Style/SpaceBeforeBlockBraces
37     Metrics/AbcSize
36     Style/MultilineMethodCallIndentation
33     Style/SymbolProc
32     Style/SpaceInsideParens
31     Style/LeadingCommentSpace
31     Style/ParallelAssignment
30     Style/MutableConstant
29     Style/IndentationConsistency
29     Style/Proc
28     Lint/HandleExceptions
27     Style/SpaceAfterComma
25     Style/EmptyLinesAroundMethodBody
22     Style/NumericPredicate
21     Style/GlobalVars
20     Style/BlockDelimiters
20     Style/PredicateName
20     Style/SpaceInsideBrackets
19     Lint/DeprecatedClassMethods
18     Style/GuardClause
17     Style/AccessorMethodName
15     Lint/UnusedMethodArgument
14     Lint/AssignmentInCondition
13     Style/AlignParameters
12     Lint/ParenthesesAsGroupedExpression
12     Lint/UnusedBlockArgument
12     Style/EmptyLiteral
11     Style/BlockEndNewline
11     Style/CommentIndentation
11     Style/MultilineBlockLayout
11     Style/TernaryParentheses
10     Lint/ShadowingOuterLocalVariable
10     Style/ColonMethodCall
9      Style/BlockComments
9      Style/ClosingParenthesisIndentation
8      Metrics/CyclomaticComplexity
8      Style/LineEndConcatenation
8      Style/OpMethod
7      Lint/IneffectiveAccessModifier
7      Style/Alias
7      Style/DoubleNegation
7      Style/IfUnlessModifier
7      Style/VariableNumber
6      Lint/UselessAccessModifier
6      Style/AlignHash
6      Style/Semicolon
6      Style/StringLiteralsInInterpolation
6      Style/TrailingCommaInArguments
6      Style/WhileUntilModifier
5      Lint/BlockAlignment
5      Performance/RedundantBlockCall
5      Style/ClassVars
5      Style/ConditionalAssignment
5      Style/IdenticalConditionalBranches
5      Style/LambdaCall
5      Style/RedundantParentheses
5      Style/SpaceAfterColon
4      Performance/RangeInclude
4      Style/DotPosition
4      Style/IndentHash
4      Style/MethodCallParentheses
4      Style/NestedParenthesizedCalls
4      Style/ParenthesesAroundCondition
4      Style/RescueModifier
4      Style/SingleLineMethods
3      Lint/LiteralInCondition
3      Lint/RescueException
3      Lint/UnifiedInteger
3      Metrics/PerceivedComplexity
3      Style/AccessModifierIndentation
3      Style/InfiniteLoop
3      Style/MethodDefParentheses
3      Style/SpaceInsideStringInterpolation
3      Style/TrailingUnderscoreVariable
3      Style/UnneededInterpolation
2      Lint/UselessComparison
2      Metrics/ClassLength
2      Style/EachWithObject
2      Style/EmptyLineBetweenDefs
2      Style/EmptyLinesAroundModuleBody
2      Style/FileName
2      Style/MethodMissing
2      Style/MultilineArrayBraceLayout
2      Style/MultilineIfThen
2      Style/MultilineOperationIndentation
2      Style/RedundantReturn
2      Style/RegexpLiteral
2      Style/SpaceAfterMethodName
2      Style/SpaceAroundKeyword
2      Style/SpaceInsideRangeLiteral
2      Style/ZeroLengthPredicate
1      Lint/DuplicateMethods
1      Lint/EndAlignment
1      Lint/NonLocalExitFromIterator
1      Performance/FixedSize
1      Style/AndOr
1      Style/BarePercentLiterals
1      Style/ClassAndModuleCamelCase
1      Style/ElseAlignment
1      Style/MethodName
1      Style/MultilineBlockChain
1      Style/NegatedIf
1      Style/NilComparison
1      Style/Not
1      Style/PercentLiteralDelimiters
1      Style/PerlBackrefs
1      Style/PreferredHashMethods
1      Style/RaiseArgs
1      Style/RedundantBegin
1      Style/SelfAssignment
1      Style/TrivialAccessors
1      Style/UnlessElse
--
39377  Total
```

### ThoughtBot Rubocop
Next, the current code base was tested using the `.rubocop.yml` file from the [ThoughBot Style Guide](https://github.com/thoughtbot/guides). The raw file that was downloaded for this study can be found [here](somewhere).

```
5078   Metrics/LineLength
3653   Style/StringLiterals
2407   Style/SpaceAroundOperators
915    Style/SpaceInsideHashLiteralBraces
614    Style/Tab
454    Style/HashSyntax
367    Style/TrailingCommaInLiteral
364    Style/TrailingWhitespace
361    Style/IndentArray
202    Style/RedundantSelf
197    Style/TrailingCommaInArguments
154    Style/SpaceInsideBlockBraces
135    Style/EmptyLinesAroundBlockBody
112    Style/IndentationWidth
104    Style/BracesAroundHashParameters
88     Style/EmptyLines
81     Style/ExtraSpacing
79     Lint/UselessAssignment
75     Style/ClassAndModuleChildren
74     Style/DotPosition
68     Style/FirstParameterIndentation
67     Style/EmptyLinesAroundAccessModifier
58     Style/EmptyLinesAroundClassBody
56     Style/TrailingBlankLines
51     Style/MultilineMethodCallBraceLayout
47     Style/SpaceBeforeBlockBraces
33     Style/SymbolProc
32     Style/SpaceInsideParens
31     Style/LeadingCommentSpace
31     Style/ParallelAssignment
30     Style/MutableConstant
29     Style/IndentationConsistency
27     Style/SpaceAfterComma
25     Style/EmptyLinesAroundMethodBody
23     Style/CollectionMethods
22     Style/NumericPredicate
20     Style/BlockDelimiters
20     Style/SpaceInsideBrackets
17     Style/PredicateName
15     Lint/UnusedMethodArgument
13     Style/AlignParameters
12     Lint/UnusedBlockArgument
11     Style/BlockEndNewline
11     Style/CommentIndentation
11     Style/MultilineBlockLayout
11     Style/TernaryParentheses
10     Lint/ShadowingOuterLocalVariable
9      Style/BlockComments
9      Style/ClosingParenthesisIndentation
8      Style/MultilineMethodCallIndentation
7      Lint/IneffectiveAccessModifier
7      Style/VariableNumber
6      Lint/UselessAccessModifier
6      Style/AlignHash
6      Style/Semicolon
6      Style/StringLiteralsInInterpolation
5      Lint/BlockAlignment
5      Performance/RedundantBlockCall
5      Style/ConditionalAssignment
5      Style/IdenticalConditionalBranches
5      Style/RedundantParentheses
5      Style/SpaceAfterColon
4      Performance/RangeInclude
4      Style/IndentHash
4      Style/MethodCallParentheses
4      Style/MultilineOperationIndentation
4      Style/NestedParenthesizedCalls
4      Style/ParenthesesAroundCondition
4      Style/RescueModifier
3      Lint/RescueException
3      Lint/UnifiedInteger
3      Metrics/PerceivedComplexity
3      Style/AccessModifierIndentation
3      Style/InfiniteLoop
3      Style/MethodDefParentheses
3      Style/SpaceInsideStringInterpolation
3      Style/TrailingUnderscoreVariable
3      Style/UnneededInterpolation
2      Lint/UselessComparison
2      Style/EmptyLineBetweenDefs
2      Style/EmptyLinesAroundModuleBody
2      Style/MethodMissing
2      Style/MultilineArrayBraceLayout
2      Style/MultilineIfThen
2      Style/RedundantReturn
2      Style/SpaceAfterMethodName
2      Style/SpaceAroundKeyword
2      Style/SpaceInsideRangeLiteral
2      Style/ZeroLengthPredicate
1      Lint/DuplicateMethods
1      Lint/EndAlignment
1      Performance/FixedSize
1      Style/AndOr
1      Style/BarePercentLiterals
1      Style/ClassAndModuleCamelCase
1      Style/ElseAlignment
1      Style/MethodName
1      Style/PreferredHashMethods
1      Style/RedundantBegin
1      Style/UnlessElse
--
16477  Total
```

## Summary

| Directory Name | default | thoughtbot |
|:--------------:|:-------:|:----------:|
|      Ruby      |    2150 |       1199 |
|       SQL      |   26980 |       8291 |
|      Rails     |    3435 |       2921 |
|    HTML/CSS    |     124 |         95 |
|   Javascript   |     558 |        429 |
|      React     |    6130 |       3542 |
|        -       |    -    |      -     |
| Total Offenses |   39377 |      16477 |
