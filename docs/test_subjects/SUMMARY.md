Examples of code for each Rubocop setting when enabled or disabled.

#### Style/RedundantSelf:
```ruby
# Enabled: false
class Array
  def my_each(&prc)
    self.length.times do |i| # keep self
      prc.call(self[i])
    end

    self
  end
end

# Enabled: true
class Array
  def my_each(&prc)
    length.times do |i| # omit self
      prc.call(self[i])  
    end

    self
  end
end
```

#### Performance/RedundantBlockCall:
```ruby
# Enabled: false
  class Array
    def my_each(&prc)
      self.length.times do |i|
        prc.call(self[i]) # okay to use prc.call
      end

      self
    end
  end

# Enabled: true
  class Array
    def my_each
      self.length.times do |i|
        yield(self[i]) # prefer yield over prc.call
      end

      self
    end
  end
```

#### Style/EmptyLinesAroundClassBody:
```ruby
# Enabled: false
  class Array
    # extra space OKAY
    def my_each(&prc)
      self.length.times do |i|
        prc.call(self[i])
      end

      self
    end
    # extra space OKAY
  end

# Enabled: true
  class Array
    def my_each(&prc) # extra space NOT okay
      self.length.times do |i|
        prc.call(self[i])
      end

      self
    end  # extra space NOT okay
  end
```

#### Style/NumericPredicate:
```ruby
# Enabled: false
  puts 3 == 0    # '==' operator okay

# Enabled: true
  puts 3.zero?   # prefer '.zero?' over '==' operator
```

#### Style/PredicateName:
```ruby
# Enabled: false
  def is_word?(fragment)
    dictionary.include?(fragment)
  end

# Enabled: true
  def word?(fragment)  # prefer 'word?' over 'is_word?' for method name
    dictionary.include?(fragment)
  end
```

#### Style/TrailingUnderscoreVariable:
```ruby
# Enabled: false
  def winner
    (player, _) = losses.find { |_, losses| losses < MAX_LOSS_COUNT }
    player
  end

# Enabled: true
  def winner
    player, = losses.find { |_, losses| losses < MAX_LOSS_COUNT }
    player
  end
```

#### Style/CollectionMethods:
```.yml
  Style/CollectionMethods:
    Enabled: true
    PreferredMethods:
      find: detect        # prefer detect over find
      inject: reduce      # prefer reduce over inject
      collect: map        # prefer map over collect
      find_all: select    # prefer select over find_all
```

#### Style/EmptyLinesAroundModuleBody:
```ruby
# Enabled: false
module MazeClasses
  # extra space OKAY
  class Maze
    # code #
  end

  class MazeSolver
    # code #
  end
  # extra space OKAY
end

# Enabled: true
module MazeClasses
  class Maze # extra space NOT okay
    # code #
  end

  class MazeSolver
    # code #
  end # extra space NOT okay
end
```

#### Style/TrailingWhitespace:
*For this explanation, assume floating dot ( `·` ) is an empty space.*
```ruby
# Enabled: false
  def load_map(filename)
  end
·· # <-- trailing space OKAY
  def is_wall?(point)
  end
# Enabled: true
  def load_map(filename)
    ...
  end
# <-- trailing space NOT okay
  def is_wall?(point)
  end
```

#### Style/LeadingCommentSpace:
```ruby
# Enabled: false
  #comment

# Enabled: true
  # comment
```

#### Style/MutableConstant:
```ruby
# Enabled: false
  DELTAS = [[1, 0], [0, 1], [-1, 0], [0, -1]] # okay
# Enabled: true
  DELTAS = [[1, 0], [0, 1], [-1, 0], [0, -1]] # not okay
```

#### Style/SpaceAroundOperators:
```ruby
# Enabled: false
  x=1+2
# Enabled: true
  x = 1 + 2
```

#### Style/StringLiteralsInInterpolation:
```ruby
# Enabled: false
  puts "  #{(0...size).to_a.join(" ")}" # double quotes in interpolation okay
# Enabled: true
  puts "  #{(0...size).to_a.join(' ')}" # prefer single quotes in interpolation
```

#### Style/SymbolProc:
```ruby
# Enabled: false
  def won?
    rows.all? do |row|
      row.all? { |card| card.revealed? }
    end
  end
# Enabled: true
  def won?
    rows.all? do |row|
      row.all?(&:revealed?)
    end
  end
```

#### Style/EmptyLinesAroundAccessModifier:
```ruby
# Enabled: false
  private
  attr_reader :rows
# Enabled: true
  private

  attr_reader :rows
```

#### Style/EmptyLines:
adjust settings
```ruby
# Enabled: false
  def method_name
    ...
  end

  # more than 1 empty line okay

  def method_name
    ...
  end
# Enabled: true
  def method_name
    ...
  end
  # 1 empty line only
  def method_name
    ...
  end
```

#### Style/ParallelAssignment:
```ruby
# Enabled: false
  x, y = 0, 1     # parallel assignment is OKAY
# Enabled: true
  x = 0           # parallel assignment NOT okay
  y = 0
```

#### Style/BlockComments:
```ruby
  # Enabled: false
    # =begin/=end  is OKAY
  # Enabled: true
    # =begin/=end  NOT okay
```

#### Style/StringLiterals:
```ruby
# Enabled: false
  str = 'abc'     # single quotes okay
# Enabled: true
  str = "abc"     # prefer only double quotes
```

#### Style/PreferredHashMethods:
```ruby
# Enabled: false
  # OKAY to use
  Hash#has_key?
  Hash#has_value?

# Enabled: true
  # Preferred to use instead
  Hash#key?
  Hash#value?
```

#### Style/SpaceInsideBrackets:
```ruby
# Enabled: false
  DELTAS = [
    [-1, -1],
    [-1,  0],
    [-1,  1],
    [ 0, -1], # extra space OKAY
    [ 0,  1],
    [ 1, -1],
    [ 1,  0],
    [ 1,  1]
  ]
# Enabled: true
  DELTAS = [
    [-1, -1],
    [-1,  0],
    [-1,  1],
    [0, -1], # extra spaces NOT okay
    [0,  1],
    [1, -1],
    [1,  0],
    [1,  1]
  ]
```

#### Style/TrailingCommaInLiteral:
```ruby
# Enabled: false
  DELTAS = [
    [-1, -1],
    [-1,  0],
    [-1,  1],
    [ 0, -1],
    [ 0,  1],
    [ 1, -1],
    [ 1,  0],
    [ 1,  1]  # <-- trailing comma NOT required
  ]
# Enabled: true
  DELTAS = [
    [-1, -1],
    [-1,  0],
    [-1,  1],
    [ 0, -1],
    [ 0,  1],
    [ 1, -1],
    [ 1,  0],
    [ 1,  1], # <-- trailing comma REQUIRED
  ]
```

#### Style/HashSyntax:
```ruby
# Enabled: false
  hash = { :key => 'value' }
# Enabled: true
  hash = { key: 'value' } # use Ruby 1.9 hash syntax instead
```

#### Style/DotPosition:
```ruby
# Enabled: false
  trace_path_back(end_node) # dot method call position does not matter
    .reverse
    .map(&:value)
# Enabled: true
  trace_path_back(end_node).reverse.map(&:value)  # dot method calls on same line
```

#### Style/EmptyLinesAroundMethodBody:
All empty lines make more leniant
```ruby
  #Enabled: false
    def method_name
      # empty line at beginning okay
      ...
      # empty line at end okay
    end
  #Enabled: true
    def method_name
      ... # empty lines at beginning or end NOT okay
    end
```

#### Performance/RangeInclude:
```ruby
  #Enabled: false
    (0..10).include?(3)
  #Enabled: true
    (0..10).cover?(3) # Use Range#cover? instead of Range#include?
```

#### Style/TrailingCommaInArguments:
```ruby
  # always bad
  method(1, 2,)

  # good if EnforcedStyleForMultiline is consistent_comma
  method(
    1, 2,
    3,
  )

  # good if EnforcedStyleForMultiline is comma or consistent_comma
  method(
    1,
    2,
  )

  # good if EnforcedStyleForMultiline is no_comma
  method(
    1,
    2
  )
```
##### Style/MultilineIfThen:
```ruby
  # This is considered bad practice:
  if cond then
  end

  # If statements can contain `then` on the same line:
  if cond then a
  elsif cond then b
  end

  # Basically, do not use 'then' for multi-line 'if'
```
#### Style/MultilineOperationIndentation:
```ruby
  #Enabled: false
    def one_side_empty?
      @cups.take(6).all? { |cup| cup.empty? } ||
      @cups[7..12].all? { |cup| cup.empty? }
    end
  #Enabled: true
    def one_side_empty?
      @cups.take(6).all? { |cup| cup.empty? } ||
        @cups[7..12].all? { |cup| cup.empty? }
    end
```
#### Style/ConditionalAssignment:
```ruby
  'http://www.rubydoc.info/github/bbatsov/RuboCop/RuboCop/Cop/Style/ConditionalAssignment'
  # see w2/w2d1/chess/display.rb
```
#### Metrics/PerceivedComplexity:
make this more leniant
```ruby
  'http://www.rubydoc.info/gems/rubocop/RuboCop/Cop/Metrics/PerceivedComplexity'
  # Measures how complex a method is written
  # see homework/mancala/lib/board.rb
```
#### Lint/RescueException:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/SpaceInsideParens:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/IndentArray:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/RedundantBegin:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/EmptyLinesAroundBlockBody:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/VariableNumber:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/BracesAroundHashParameters:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/IndentHash:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/SpaceInsideHashLiteralBraces:
```ruby
  #Enabled: false

  #Enabled: true
```
Metrics/LineLength:
  Max: 100
  Exclude:
    - '**/db/seeds.rb'
    - '**/db/schema.rb'

#### Style/ZeroLengthPredicate:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/SpaceInsideBlockBraces:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/Tab:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/MultilineMethodCallIndentation:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/NestedParenthesizedCalls:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/MultilineMethodCallBraceLayout:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/ClassAndModuleChildren:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/AlignHash:
```ruby
  #Enabled: false

  #Enabled: true
```
#### Style/AlignParameters:
```ruby
  #Enabled: false
    has_many :child_comments,
      class_name: "Comment",
      foreign_key: :parent_comment_id,
      primary_key: :id
  #Enabled: true
    has_many  :child_comments,
              class_name: "Comment",
              foreign_key: :parent_comment_id,
              primary_key: :id
```
