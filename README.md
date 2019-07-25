# Ruby Logic and Conditionals

### Flatiron School Fast Track Program

 ## SWBATs

 * Recognize methods that will return boolean values
 * Use logical operators to manipulate true and false values
 * Define control flow
 * Recognize which ruby values are truthy and falsy
 * Use the double bang operator to determine truthiness in Ruby
 * Write an if / else statement

 ## Outline

 ```text
 5m Introduce topic
 10m Booleans and equality checking
 10m Conditionals and Control flow
 5m 'truthy' and 'falsy' values
 5m CLI input

 ===
 35m Total
 ```

![](https://media.giphy.com/media/QJvwBSGaoc4eI/giphy.gif)

### Booleans

- We need to be able to represent if something is true or false
- Ruby gives us values `true` and `false` that represent what they say

```ruby
> true
=> true
> false
=> false
```

- We can operate on those values with _logical operators_
- `&&` (and) means 'both the left and the right must be true'
- `||` (or) means 'either the left or the right are true'
- `!` (not) means 'the opposite of this value - true if false, false if true'

```ruby
> true && true
=> true
> true && false
=> false
> false && true
=> false
> false && false
=> false
> true || true
=> true
> true || false
=> true
> false || true
=> true
> false || false
=> false
> !true
=> false
> !false
=> true
```

- This is pretty convenient, but we want to be able to actually check something real!
- Ruby gives us conditional methods that will check some condition and return `true` or `false`
- `==` (equals) checks if the left and right are equal
- `!=` (not equal) checks if the left and right are not equal
- `<` (less than) checks if the left is less than the right
- `>` (greater than) checks if the left is greater than the right

```ruby
> 7 == 6
=> false
> 100 == 100
=> true
> 7 != 6
=> true
> 100 != 100
=> false
> 7 > 6
=> true
> 7 < 6
=> false
> "Cat" == "Cat"
=> true
> "cat" == "Cat"
=> false
```

> NOTE: A common mistake is to mix up the `=` and `==` operators. `=` is for assignment, `==` is for equality checking.

- There are lots of other operators that will check some condition and return a boolean
- For instance, `.even?` and `.odd?` check if something is even or odd

```ruby
> 4.even?
=> true
> 5.even?
=> false
> 12.odd?
false
> 101.odd?
=> true
```

 ### Conditionals
 * Sometimes, we want to do one thing. Sometimes, we want to do another.
 * We can write _conditional statements_ that execute only when some condition is met

 ```ruby
 if x > 5
   puts "greater"
 end
```
 * We can use `else` if we want to do something...else

```ruby
 if x < 10
   puts "less"
 else
   puts "ooh, what a big number"
 end
 ```

 * _Example_: For example, if I am tired, then I will take a nap. Otherwise, I will keep reading this insightful and informative readme. You could also invert the perspective like in this example:
  * _If it is true that I am tired, then I will take a nap._
  * _If it is false that I am tired, then I won't take a nap._
  * We understand that if something is true we will do one thing, if it is false we will do another, great lets break this down, first we need to understand what makes something true or false

### Conditionals and Control Flow

> "_A control flow construct is a language feature which disrupts the normal progression to the next statement and conditionally or unconditionally branches to another location in source code._"

> -– Robert Klemme

* Control flow is an important part of Ruby programming and web development.
* Example: functionality on a website you've visited that is only available to a user __if__ that user is _logged in_.

#### if statments

```ruby
if 5 > 2
  print "5 is greater than 2"
end

if 6 + 3 == 9
  puts "Giraffes have no vocal cords."
end
```

#### else statments

```ruby
if false
   puts "This will never get printed because the above
     statement evaluates to false."
else
   puts "This will get printed!"
end
```

#### elsif statments

```ruby
dog = "thirsty"

if dog == "hungry"
  puts "Refilling food bowl."
elsif dog == "thirsty"
  puts "Refilling water bowl."
else
  puts "Reading newspaper."
end
```

### truthy and falsy values
 * truthy and falsy: Flow control is predicated on true-or-false boolean values.
 * But what about values that aren't literally `true` or `false`? Is a String `true`?
 * Ruby has an opinion! It thinks that everything is "truthy" - except for `false` and `nil`
 * _falsy values in ruby_: In Ruby only false and nil are falsy. Everything else is truthy (yes, even 0 is truthy).

|       value      | truthy? |
|:----------------:|---------|
|         0        |   yes   |
|        ""        |   yes   |
|      "hello"     |   yes   |
|        6.7       |   yes   |
|       true       |   yes   |
|       TRUE       |   yes   |
|       [1, 2]     |   yes   |
| {hello: "world"} |   yes   |
|       (3 - 4)    |   yes   |
|        nil       |    no   |
|       false      |   no    |
|       FALSE      |   no    |
|                  |         |

* The `!` "single-bang" operator represents "NOT"

```ruby
!true #=> false

!false #=> true
```

* double bang operator (!!) flips twice:

```ruby
!!true #=> true
!!"hi" #=> true
word = "hi"
!!word #=> true
```

* Helpful for checking whether something is truthy or falsy
* Do booleans quiz on boolean learn lab


## Command Line Applications

- So far, the programs we've written do the same thing every time they're run.
- We want to be able to write programs that do different things based on some user input
- Just like we can print some information to the screen with `puts`, ruby also gives us a way to get user input
- The method `gets` will wait for the user to type something, and give back a string

```ruby
puts "Enter your name: "
name = gets
puts "Hello, " + name
```

- When we get the input from the user, it's got a weird bonus character - `\n`
- This is a newline character - it represents a line break
- We can get rid of it with `.chomp` or `.strip`, which remove 'whitespace' characters from the string

```ruby
> "Chomped!\n".chomp
=> "Chomped"
> input = gets.chomp
Chomped!
=> "Chomped!"
```

* You can combine what we know about booleans with our newfound ability to get user input to write programs that do different things based on the user's input!


### Labs
- [gets CLI Input](https://learn.co/tracks/full-stack-web-development-v6/intro-to-ruby-development/command-line-applications/gets-cli-input)
- [Greeting CLI Lab](https://learn.co/tracks/full-stack-web-development-v6/intro-to-ruby-development/command-line-applications/greeting-cli-lab)
- [Tic Tac Toe Move](https://learn.co/tracks/full-stack-web-development-v6/intro-to-ruby-development/command-line-applications/tic-tac-toe-move)
- [Tic Tac Toe Position Taken](https://learn.co/tracks/full-stack-web-development-v6/intro-to-ruby-development/logic-and-conditions/tic-tac-toe-position-taken)
- [Valid Tic Tac Toe Move](https://learn.co/tracks/full-stack-web-development-v6/intro-to-ruby-development/logic-and-conditions/valid-tic-tac-toe-move)
