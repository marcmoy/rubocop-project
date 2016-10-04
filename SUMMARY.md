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
```yml
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

# Enabled: true

```

#### Style/TrailingWhitespace:
```ruby
# Enabled: false

# Enabled: true

```

#### Style/LeadingCommentSpace:
```ruby
# Enabled: false

# Enabled: true

```

#### Style/MutableConstant:
```ruby
# Enabled: false

# Enabled: true

```

#### Style/SpaceAroundOperators:
```ruby
# Enabled: false

# Enabled: true

```

#### Style/StringLiteralsInInterpolation:
```ruby
# Enabled: false

# Enabled: true

```

#### Style/SymbolProc:
```ruby
# Enabled: false

# Enabled: true

```

#### Style/EmptyLinesAroundAccessModifier:
```ruby
# Enabled: false

# Enabled: true

```

#### Style/StringLiterals:
```ruby
# Enabled: false

# Enabled: true

```

#### Style/EmptyLines:
```ruby
# Enabled: false

# Enabled: true

```

#### Style/ParallelAssignment:
```ruby
# Enabled: false

# Enabled: true

```

#### Style/BlockComments:
```ruby
# Enabled: false

# Enabled: true

```

#### Style/PreferredHashMethods:
```ruby
# Enabled: false

# Enabled: true

```

#### Style/SpaceInsideBrackets:
```ruby
# Enabled: false

# Enabled: true

```

#### Style/TrailingCommaInLiteral:
```ruby
# Enabled: false

# Enabled: true

```

#### Style/HashSyntax:
```ruby
# Enabled: false

# Enabled: true

```

#### Style/DotPosition:
```ruby
# Enabled: false

# Enabled: true

```
