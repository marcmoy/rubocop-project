#App Academy Ruby Linter

##How to install

###Step 1
`gem install rubocop`

###Step 2
`apm install linter-rubocop`

###Step 3
Run `rbenv which rubocop` to get your *executable path*.

###Step 4
Open your Atom config file (`~/.atom/config.cson`) through the Atom navigation bar:
*Atom* -> *Config...*

###Step 5
Add the following setting to your config file:
```cson
'linter-rubocop':
  'executablePath': '/Users/Marc/.rbenv/versions/2.3.1/bin/rubocop' # your executable path from step 3
```

###Step 6
[Download](.rubocop.yml) the `.rubocop.yml` file and add to your root directory ( i.e. `/Users/Marc` )
