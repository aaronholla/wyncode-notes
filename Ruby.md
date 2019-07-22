# Ruby

Turing-complete computer language. Optimized for the programmer and not the computer. It is designed to make the programmers happy. Vary inclusive community, beginner friendly. Great built in methods for manipulating data.

Ruby is not concurrent, rails provides ways of running concurrent tasks but it is not built into ruby.

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

## Function

> Parentacies are optional in ruby when running functions.
