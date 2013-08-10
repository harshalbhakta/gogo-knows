All About Ruby
====

- Use two spaces per indent. Never use tabs for indent.

- Anything following a # in the code is a comment. 

- Ruby also supports multiline comments delimited by =begin and =end, but # comments are more commonly used.

- Use lowercase_words_separated_by_underscores for methods, arguments, and variables, including instance variables.

- Use CamelCase for class names.

- Use ALL_UPPERCASE for constants.

- If you are defining—or calling—a method with no parameters, leave the parentheses off.

```ruby

  # Defining
  def words
    @content.split
  end

  # Calling
  words

```

- Generally leave off paranthesis for conditional statements.

```ruby

  if words.size < 100
    puts 'The document is not very long.'
  end

```

- If your block consists of a single statement, fold the whole statement into a single line and delimit the block with braces.

```ruby

  10.times { |n| puts "The number is #{n}" }

```

- For a multistatement block, spread the block out over a number of lines, and use the do/end form.

```ruby

  10.times do |n|
    puts "The number is #{n}"
    puts "Twice the number is #{n*2}"
  end

```

- Getting used to 'unless' might take some time.

```ruby

  def title=( new_title )
    # if not this then do that
    if not new_title.blank?
      @title = new_title
    end
  end

  def title=( new_title )
    # do this unless that.
    unless new_title.blank?
      @title = new_title
    end
  end

```

- 'while' & 'until' works similar to how 'if' & 'unless' work.

```ruby

  while ! document.is_printed?
    document.print_next_page
  end

  # keeps going until its conditional part becomes true. 
  until document.printed?
    document.print_next_page
  end

```

- Single line 'if', 'unless', 'while' & 'until'

```ruby

  @title = new_title unless new_title.blank?

  @title = new_title if new_title.changed?

  document.print_next_page while document.pages_available?

  document.print_next_page until document.printed?

```

- for actually calls the each function internally.

```ruby

  for font in fonts do
    puts font
  end

  # Use this instead
  fonts.each do |font|
    puts font
  end

  Note: 'for' does not introduce a new scope, while 'each' does.

```

- 'case' statement in Ruby

```ruby

  author = case title
    when 'War And Peace' then 'Tolstoy'
    when 'Romeo And Juliet' then 'Shakespeare'
  end

  # 'case' uses '===' operator for comparison.
  # Classes also use '===' operator for comparison,
  # which makes below snippet quite handy.
  case doc
  when Document
    puts "It's a document!"
  when String
    puts "It's a string!"
  else
    puts "Don't know what it is!"

```

- Understanding false in ruby.

```ruby

  # Only false & nil are treated as false. Everything else is true.

  - 0 is true, as it is neither false or nil.

  - String "false" is also true.

```

- Assign variable is if does not exist

```ruby

  @name = '' unless @name

  # Better way is
  @name ||= ''          	# name  = name || ''

  # This is same as
  count += 10  				# count = count + 1

  Note: 

  ||= will assign value if the varialbe is false. Avoid using ||= for assigning boolean values to avoid false/nil disasters.

```

- Ways to create an array of strings without spaces.

```ruby

  # Contains a lot of ' & ,
  words = [ 'how', 'you', 'doing', '!' ]

  # Easier way is
  words = %w{ how you doing ! }

```

- Ways to create an hash of strings without spaces.

```ruby

  # all are valid ways of creating a hash

  freq = { "I" => 1, "don't" => 1, "like" => 1, "spam" => 963 }

  book_info = { :first_name => 'Russ', :last_name => 'Olsen' }

  book_info = { first_name: 'Russ', last_name: 'Olsen' }

```

- Arguments of a method can be omitted if defaults are specified.

```ruby

  def load_font(name, size = 10, new_size = 12)
    puts "name = #{name} & size = #{size} & new_size = #{new_size}"
  end

  # Both are valid calls to the above method
  load_font('Times')              # name = Times & size = 10 & new_size = 12
  load_font('Times',14)           # name = Times & size = 14 & new_size = 12

  Note: Using above technique there is no way to call the method to default value for 2nd argument and specifying the 3rd argument. load_font('Times',nil,14) will take size = nil.

  # Alternative way to handle it would be.
  def load_font(name,size = nil, new_size = nil)
    size     ||= 10
    new_size ||= 12
    
    puts "name = #{name} & size = #{size} & new_size = #{new_size}"
  end

  load_font('Times',nil,14)       # name = Times & size = 10 & new_size = 14

```

- Arbitary number of arguments in ruby.

```ruby

  def echo_all( *args )
    args.each { |arg| puts arg }
  end

  # Expects minimum of 2 arguments. All arguments betweer
  # the first and the last go to middle_args.
  def echo_at_least_two( first_arg, *middle_args, last_arg )
	puts "The first argument is #{first_arg}"
	middle_args.each { |arg| puts "A middle argument is #{arg}" }
	puts "The last argument is #{last_arg}"
  end

```

- Arbitary arguments can make method calls simpler in some cases.

```ruby

  def add_authors( names )
    @author += " #{names.join(' ')}"
  end

  add_authors( [ 'Strunk', 'White' ] )

  # If we use arbitary arguments

  def add_authors( *names )
    @author += " #{names.join(' ')}"
  end

  add_authors( 'Strunk', 'White' )

```

- Hash arguments

```ruby

  def load_font( specification_hash )
    # Load a font according to specification_hash[:name] etc.
  end	

  load_font( { :name => 'times roman', :size => 12 })

  # Can also be called by ommiting the { }, if hash argument comes last.

  load_font( :name => 'times roman', :size => 12 )

```

- Running through a collection

```ruby

  # Array

  words = %w{ how you doing }
  words.each { |word| puts word }

  # Hash

  student =  { name: 'raj', age: 21, class: 9 }

  # If only one argument is passed to the block, it will be an 
  # array of length 2 => [ key, value]
  student.each { |entry| pp entry }	 [:name, 'raj'] [:age, 21] [:class, 9]

  # 2 arguments works as below.
  student.each { |key,value| puts "#{key} => #{value}" }

```

- Finding index of an entry in an array.

```ruby

  word = 'how'
  index = words.find_index { |this_word| word == this_word }

```

- Using 'map' to return everything that the block returned

```ruby

  words = %w { How You Doing }

  words.map { |word| word.size }        # [3, 3, 5]

  words.map { |word| word.downcase }    # ['how', 'you', 'doing']

```

- Using 'inject' to pass 2 arguments, first of it is the result returned by the block.

```ruby

  numbers = [1, 2, 3, 4, 5]

  sum = numbers.inject(0) { |result,number| number + result }		# 15

  # Without passing the argument to inject, inject will skip block call for 1st element.
  sum = numbers.inject { |result,number| number + result }		# 15

```

- 'hash' is ordered.

```ruby

  demo_hash = { :first => "how", :second => "you", :third => "doing" }   # [:first,:second,:third]

  # Order is the same even after below statement.
  demo_hash[:first] = "How"												 # [:first,:second,:third]

  # Order is preserved if we add a element to hash. New element goes to the end.
  demo_hash[:fourth] = "!"												 # [:first,:second,:third,:fourth]

```

- Be careful when using collections. If you modify the collection from withing the block, you might get some unexpected results.

- Different types of string literals.

```ruby

name = "Harshal"

# Single quote strings can only handle \' delimeter operations.
puts 'Hello \nworld\'s #{name}'  # Hello \nworld's #{name}

# Double quote strings can handle a lot of things
puts 'Hello \nworld\'s #{name}' 

Hello 
world's Harshal

# For strings with lots of ' & ", we have %q & %Q

# %q behaves as a single quote for computation
puts 'name = #{name}'		     # name = #{name}
puts %q{name = #{name}}		     # name = #{name}

# %Q behaves as a double quote for computation
puts "name = #{name}"		     # name = Harshal
puts %Q{name = #{name}}		     # name = Harshal

# %q & %Q can be used with other delimiters too.

%q { ... }
%q ( ... )
%q $ ... $

```

- Multiline strings

```ruby

  puts "a multi-line
  string with newline"

  puts %q{another multi-line
  string with new line}

  puts %Q{another multi-line string with \
  no newline}

  puts <<EOF
  This is the beginning of my here document.
  And this is the end.
  EOF

```

- String manipulations

```ruby

  chomp: Removes one trailing newline chars
  chop: Removes one char from end.
  "".chop  => ""
  "".chop! => nil

  "Hello".upcase   => HELLO
  "Hello".downcase => hello
  "Hello".swapcase => hELLO

  "It is warm warm outside".sub("warm","cold")  => "It is cold warm outside"
  "It is warm warm outside".gsub("warm","cold") => "It is cold cold outside"

  "how you doing".split => ["how", "you", "doing"]
  "1:2:3".split(':')    => ["1", "2", "3"]

  @author.each_char {|c| puts c}
  @author.each_byte { |b| puts b }
  @content.each_line { |line| puts line }

```

- Regular Expressions

```ruby

  regular expression in ruby is between / /

  . matches a single character

  [aeiou] will match any single lowercase vowel
  
  [0–9] will match exactly any decimal digit
  
  [a-z] will match any lowercase letter
  
  \d will match any digit, so that \d\d will match any two digit number
  
  \w, where the w stands for “word character,” will match any letter, number or the underscore.

  \s will match any white space character including the vanilla space, the tab, and the newline.

  AM|PM will match either AM or PM

  The (car|boat) is red - Will match both The car is red as well as The boat is red.

  * matches zero or more of the thing that came just before it.

  puts /\d\d:\d\d (AM|PM)/ =~ '10:24 PM' # 0

  puts /PM/ =~ '10:24 PM'  				 # 6

  puts "It matches!" if /AM/i =~ 'am'

  /\AOnce upon a time/ =~ "abc Once upon a time" 		   # nil : \A indicates search at start of string
  /\AOnce upon a time/ =~ "Once upon a time in Mumbai"     # 0
  /Once upon a time/ =~ "abc Once upon a time"   		   # 4
  /Once upon a time\z/ =~ "abc Once upon a time"   		   # 4 : \z indicates string ending with
  /Once upon a time\z/ =~ "Once upon a time abc"		   # nil

  ^. Circumflex character matches two things: beginning of string or beginning of any line within string.

  n $ matches the end of the string or the end of any line within the string,

  .* indicates any number of any characters. Matches anything.

  /.*/  : won't match beyond newline

  /.*/m : will match beyond newline

  ? : matches zero or one of the things that came

```

- Symbols

```ruby

	# Cannot be changed. Only one instance of a symbol is created. Ex. :all referenced from anywhere is the same :all instance.

	# When using strings as hash keys, if the string passed is changed, the string key in hash is preserved.
	# Which is why it makes sense to use symbols as hash keys.

	str = "hello"
	hsh = { str => "world" }
	str = "xyz"
	puts hsh["hello"] # world

```

- Use map function to call another method on all the elements of an arrary.

```ruby

> "hello,world,test".split(",").map(&:length)       # [5,5,4]

> ["Hello","World","Test"].map(&:length)	    # [5,5,4]

```

