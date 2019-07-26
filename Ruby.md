# Ruby

Turing-complete computer language. Optimized for the programmer and not the computer. It is designed to make the programmers happy. Vary inclusive community, beginner friendly. Great built in methods for manipulating data.

Ruby is not concurrent, rails provides ways of running concurrent tasks but it is not built into ruby.

> Parentacies are optional in ruby.

> Object oriented programming is a concept. It varies based on the language. Just a way someone has implimented object-oriented programming.

## Classes

You define objects using classes. Using the new keyword will give you an instance or the class. 

```ruby
class Student
end

student = Student.new
```

> Class names have to be constants. They have to start with a capital letter.

### Instance Variables
When you see an `@` in front of a variable it is an instance variable. The `@` allows the variable to exist inside of new instances of the method.

### Instance Methods
Defining a method on your class will assign any new instances the methods that you setup. These are different from class methods as they don't have a `self.method_name`. 

```ruby
# instance method
class Person
  def practice

  end
end

Person.new.practice

# class method
class Person
  def self.practice

  end
end

Person.practice
```

### Initialization
lets you set instance variables and setup the instance when you use new to create an instance.
```ruby
class Person
  def initialize
    @name = "Aaron"
    @age = 27
  end
end

person = Person.new
```
### Readers
`attr_reader` is a method for classes that takes arguments and they must be symbols with same name as the instance variables. It will create getter methods for your instance variables.

```ruby
class Person
  attr_reader :name, :age
  def initialize
    @name = "Aaron"
    @age = 27
  end

  def get_older
    @age += 1
  end
end
```

### Writers
`attr_writer` is a method that will create class methods for your setters for instance variables on a class.

### Accessors
`attr_accessor` is a method that will create both getter and setter for instance variables on a class.

### Inheritance
### Mixins
### Requiring Files
You can require other ruby files. You have to use the `./` to specify current folder
```ruby
require './speak.rb'
```

## Syntax Sugar

```ruby
1 + 1
# same as calling the + method on number
1.+(1)

print "Hello World!"
Kernel.print("Hello World!")

# Syntax suger will handle order of operations for you
1 + 2 * 2
# is not the same as
1.+(2).*(2)
```

## Variables

Variables are snake case, everything is lowercase use underscore to seperate words.

```ruby
num_people = 3
```

Only assign if its not already assigned.

```ruby
me ||= "tarzan"
```

Declare Constants in Ruby

```ruby
MY_CONST = 1
MY_CONST # 1
MY_CONST = 2
# Warning: already initialized
```

In ruby you can namespace variables using `::`

```ruby
Math::PI
```

### Blocked scoped Variables

What the variable is depends on what thing your inside.
```ruby
10.times do |n|
  puts "Hello #{n}"
end
```

## Data Types

Most popular ones.

- Integer
- Float
- String
- Array
- Nil
- True / False
- Hash
- Symbol
- Object

### Integers

https://ruby-doc.org/core-2.5.1/Integer.html#method-i-7C

If you do not provide a decimal with the numbers it will use whole numbers.

```ruby
3 / 2 # 1
```

```ruby
0 < 1
1 > 0
1 <= 1
1 >= 1
1 == 1
5 <=> 10 # -1
50 <=> 10 # 1
50 <=> 50 # 0
```

### Floats

https://ruby-doc.org/core-2.5.1/Float.html

To use floats you have to provide decimals.

```ruby
3.0 / 2.0 # 1.5
```

If you use a float with a integer it will use float.

```ruby
3.0 / 2 # 1.5
```

### Strings

https://ruby-doc.org/core-2.5.1/String.html

```ruby
"Hello".reverse
```

#### Interpolation

```ruby
my_age = 27
print "My age is #{my_age}" # My age is 27
# Cannot interpolate with single quote strings
print 'My age is #{my_age}' # My age is #{my_age}
```

### Arrays

https://ruby-doc.org/core-2.5.1/Array.html

```ruby
# Shovel something into array
[] << 1
# same as push
[].push(1)
```

### Nil

Ruby does not have an undefinded it has the Nil class. When something doesn't exist or you access something thats not there you will get nil.

```ruby
# You can use the .nil? method to check truthy or falsy
1.nil? # false
0.nil? # true
```

### Booleans

`&&` will return first false or last true. Order of operations matters.

```ruby
true && false # false
false || true # true
false && print("truthy") # false
nil && print("truthy") # nil
```

### Hash
https://ruby-doc.org/core-2.5.1/Hash.html

Key value storing. There is no dot notation since it treats dots as methods.

```ruby
{"hello" => "world"}.merge({"ok" => "go"})
```




## Naming Conventions

Methods that end in `?` marks return booleans.

```ruby
1.odd? # true
"".empty? #true
1.3.integer? #false
```

Methods that end in `!` will generally mutates their caller.

```ruby
x = "me"
x.upcase
x # "me"

x.upcase!
x # "ME
```

## Methods

Almost everything has methods. Ask something questions. and you can chain them.

```ruby
1.class # Integer
1.class.ancestors
###
[Integer,
 JSON::Ext::Generator::GeneratorMethods::Integer,
 Numeric,
 Comparable,
 Object, # South of Object is mostly just internal to Ruby
 JSON::Ext::Generator::GeneratorMethods::Object,
 PP::ObjectMixin,
 Kernel,
 BasicObject]
###
```

> You can call `.methods` on anything in ruby to get back a list of all the methods that you can call.

### Defining Methods
```ruby
def add_two(number)
  return number + 2
end
 
puts add_two(2)
```

> Ruby has implicit return. It will return the result of the last line of the function if there is no return keyword.

```ruby
def add_two(number)
  number + 2
end
 
puts add_two(2)
```

> Returning early in loops inside methods is faster because it will not have to loop through the entire array.

```ruby
def found?(needle, haystack)
  for item in haystack
    return true if item == needle
  end
  false
end
 
puts found?("c", ["a", "b", "c", "d", "e", "f"])
```

> Its common to not put the return keyword at the last line.


You can set default values for arguments by setting them equal.

```ruby
def add_two(number = 0)
  number + 2
end
 
answer = add_two
 
puts answer
```

You can grab all arguments using the `*rest` as an argument.
It will put them into an array called rest.

```ruby
def add_two(number = 0, *rest)
  number + 2
end
 
answer = add_two
 
puts answer

# can also grab *rest as all arguments
def add_two(*rest)
  rest.sum + 2
end
```

Optional Aruments
```ruby
def add_two(number, options={})
  answer = number + 2
  answer
end

puts add_two(5.3)
```

> If you use a hash as an argument you don't need to put the `{}` around it.

```ruby
def add_two(number, options={})
  answer = number + 2
  answer = answer.ceil if options[:round] == :up
  answer = answer.floor if options[:round] == :down
  answer
end

puts add_two(5.3, round: :up )
# same as
puts add_two(5.3, {round: :up})
```


## Control flow

### IF Else
```ruby
in_stock = ["Chocolate", "Vanilla", "Strawberry"]
out_of_stock = ["Caramel", "Cookies and Cream"]
 
customer_request = "Caramel"
 
if in_stock.include?(customer_request)
  puts "Sure, we have #{customer_request}."
elsif out_of_stock.include?(customer_request)
  puts "Sorry, we're all out of #{customer_request}."
else
  puts "We don't even carry #{customer_request}."
end

# Short
if 1 + 1 == 2 then puts "of course" else puts "no way" end

# Turnaries
message = "team".include?("i") ? "be a ball hog" : "be a team player"

# one liner
puts "duh" if 1 + 1 == 2

# unless
puts "We don't even carry" unless 1 + 2 === 5
```

### Case statements
Using when you can pass a single case or multiple.
```ruby
case season
when "spring"
  puts "April showers bring May flowers."
when "summer"
  puts "And the livin's easy."
when "fall"
  puts "The leaves are just starting to turn."
when "winter"
  puts "The most wonderful time of the year."
end
```

```ruby
season = ["spring", "summer", "winter", "fall"].sample
 
case season
when "spring", "summer", "fall"
  puts "It's intolerably hot in Miami in the #{season}."
else
  puts "It's actually quite pleasant in Miami in the #{season}."
end

season = ["spring", "summer", "winter", "fall"].sample
 
puts "it's #{season}!"
```

### Loops

Infinite loop.
```ruby
loop do
  print "Loop de loop!"
end
```

If single line use `{}` for the block.
```ruby
loop { print "Loop de loop!" }
```

While Loop - Will run while something is true. Will not run at all if the starting state is false.
```ruby
num = 1
while num <= 10
  puts num
  num += 1
end
```


Until loop - same thing as while but will run until something is true.
```ruby
until num <= 10
  puts num
  num += 1
end
```

For loop

```ruby
beatles = ["John", "Paul", "Ringo", "George"]
 
for name in beatles
  puts "My name is #{name} and I'm a Beatle."
end
```

Times
```ruby
10.times{puts "Hello"}
```

Each - Most Common way to loop
```ruby
["John", "Paul", "Ringo", "George"].each do |name|
  puts "My name is #{name} and I'm a Beatle."
end

#same thing
beatles = ["John", "Paul", "Ringo", "George"]
beatles.each{ |name| puts "My name is #{name} and I'm a Beatle." }
```

Map - map over array and change each item in the array

```ruby
nums = [1,2,3,4].map do |num|
  num ** 2
end
 
puts nums
```

There is a special syntax for map. It only works if you are going to call a single method on each
```ruby
nums.map{&:capitalize}
```

## Range
```ruby
(1..1000).each{|n| puts n}
```
You can also use `_` underscore as a comma in numbers to make large number easier to read
```ruby
(1..1_000).each{|n| puts n}
```
