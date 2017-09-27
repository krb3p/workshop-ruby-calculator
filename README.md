# Build a Ruby Calculator

#### 3-hour Workshop

## The Why

What's your favorite way to learn?

At Upperline, we like to learn by doing. We go swimming in the deep end. We take on challenges that we don't quite know how to complete. We get lost in our code and start over and have to ask for help. We do all this because we'd rather be experimenting and failing and learning than just sitting in our comfort zones.

Code opens doors, but it's also intimidating. You're learning something for the first time, and the best way to learn something is to just start doing that thing, but if you don't know how to do it yet, you can expect to make tons of mistakes. We need to start viewing making mistakes as an act of courage and a sign of learning - so even though our gut reaction when we make mistakes is to feel a little embarrassed, the first thing we do today is actually going to be about getting comfortable feeling a little foolish.

That said, vulnerability like this is a two-way street. We need to be comfortable making mistakes, but we also need to be grateful when someone else is willing to make mistakes in front of us, because making a mistake in front of people is an act of courage. It says "I trust you to respect where I'm at in my progress as a developer, because even if it feels like a stupid mistake, it's something I'm just learning. I trust you to understand and respect that, and to react to my mistakes with kindness and gratitude."

#### Play the name game, and one other (RPS Evolution is a good one, because no one is the center of attention)

With small tools, you can actually build something super powerful. We're going to learn simple versions of five major computer programming concepts, and from those five concepts, you'll have the power to build anything from a basic calculator all the way up to a choose-your-own-adventure story in the style of the original Oregon Trail.

1. Printing information to the screen
2. Getting information from your user
3. Storing information in variables
4. Converting data from one type to another (as well as reasons why that might be useful)
5. Using conditional control flow statements to only run the code the user wants to run

So sure, we're building a calculator, but with these five tools, you can actually build some really impressive programs. Even if we limit ourselves to Calculators, there are dozens of different types of calculators out there.

For example:

* A unit conversion calculator (that converts miles to kilometers or minutes to hours)
* A tip calculator (that tells you how much to add to your bill based on price and quality of service)
* A BMI calculator (that tells you about the relationship between your weight and height)

That's three, but there are dozens more. We're going to take 3 minutes for you and your table to brainstorm and **write down** as many types of calculators as you can think of - some that exist already, and others that maybe don't exist yet.

When we brainstorm, we have two rules: "yes, and" and "Cool! Next?"

This means even if someone says something that seems crazy at first, like "Makeup Calculator!", we let that idea live. We can choose not to implement it later if we think of something better, but there's no point in killing the idea. Killing an idea just means that this is the sort of space where ideas die, and that's not what brainstorming is for. Save that pessimism for later.

## Setup

Assume going into this that your students don't have any experience. We're going to remove every barrier to entry we can. Use a simplified IDE like <a href="https://repl.it/languages/ruby">repl.it ruby</a> that doesn't require account creation or login to get started - make a shortened URL to get students there faster. If you want to use that exact IDE, you can use the bit.ly link http://bit.ly/rubyPlayground to get all your students there really quickly.

## OUTLINE:

1. Hello World
2. Variables and Interpolation
3. Ruby Math and Datatypes (conversion / casting)
4. User Input
5. Control Flow

#### Extensions

* Custom Methods

## Hello World

You're going to write your first program - this is the first program that any developer ever writes.

Your screen has two parts: on the left is a Ruby File. On the right is the console, which is also running a REPL - a read-evaluate-print loop. So on the left, you can write an entire program, and on the right, you can see your program run, and you can test out small bits of code.

Let's write the foundation for our program on the left.

Type this line:

```ruby
puts "Hello world!"
```

Then press `run ->` up at the top.

## Variables and Interpolation

This is great, but if we're going to build a calculator, we'll need more than just printing out information. For example, we know we'll be printing out an answer eventually, but we won't know what the answer is until after the user as asked us a question.

That means we'll need to create a variable to store our answer in, and then we can print out the answer later once we know the variable. We'll pretend that we're

```ruby
my_answer = 17
puts "Your answer is: #{my_answer}"
```

This means we can build a sort of fill-in-the-blank sentence, and we can figure out what goes in the blank while the program is halfway done running.

## Ruby Math and Datatypes (conversion / casting)

Obviously, you can't just make up an answer and store it - you'll need to actually do some math.

This means you'll want to make sure you understand how built-in Ruby math functions work. We'll run some tests on the right side of the screen (using the REPL), because a REPL **reads** a line of code, **evaluates** that line of code, then **prints** the result, and repeats this **loop** endlessly, waiting each time for you to type something new.

Here are some lines of code you can ask your computer to read, evaluate, and print by typing them into the right side of the screen.

```ruby
3 + 10
"3" + "10"
"Three" + "Ten"
10 - 7
33 - "3"
3 * 3
10 * 7
3 ** 2
5 ** 2
10 / 5
10 / 4
10 / 4.0
10.0 / 4
10.0 / 4.0
```

Debrief questions:
1. How does the computer add when there are no quotation marks? How does the computer add when there ARE quotation marks?
2. What is the difference between `*` and `**` ?
3. Does Ruby follow the order of operations?
4. What else did you try? What theories / hypotheses did you form based on your results.

Takeaways:
* To build this calculator, you'll need to know three major Datatypes:
    1. Integers: Just like in math class, an integer is a number without a decimal point. 3 is an integer. 3.5 is not an integer.
    2. Strings: Information in quotes are strings. We can think of them as words or sentences, so ruby sees `"3"` as a word or a character, not as a quantity.
    3. Floats: If a number is typed with a decimal point, ruby knows to treat the number not as an integer, but as a float.
* Ruby always does the math and gives you an answer based on the type of data you enter.
    1. That's why "adding" two strings just simply glues them together - a process called **concatenation**. Even if the strings contain numbers like `"3" + "10"`, the result will be `"310"`, which is the concatenation of those two numbers, not the sum.
    2. That's also why dividing two integers also returns an integer. We know that `10 / 4` should evaluate to 2.5, but it doesn't; it evaluates to 2 instead. You've probably figured out that it gets the 2 by rounding down, and most programming languages round ALL integer math **down** to the nearest integer.
    3. When you mix datatypes, Ruby will attempt to see if there are any obvious conversions (usually from integers to floats), but otherwise Ruby will throw you a type error. When that happens, it's up to you to figure out and clarify what datatypes you'd like Ruby to use.

This probably taught you that you may need to convert data back and forth. To do this, we use the built-in dot syntax of ruby type conversion methods. That's a lot of vocab, but don't stress. Test these out and see if you can predict what `.to_i`, `.to_f`, and `.to_s` do when you attach them to a piece of data.

```ruby
3 + "10"
3.to_s + "10"
3 + "10".to_i

10 / 4
10 / 4.to_f
```

#### Optional Content: Modulus Operator

###### Note to instructor: expect to cut this for time - in 3 hours, it's unlikely that a student will make it to this point.

A modulus is how a programming language computes remainders. That means that since 12 / 3 is a perfect 4, then `12 % 3` (pronounced "twelve mod three") would be 0, because there's no remainder. This probably won't come into play in our Ruby calculator, but it turns out to be surprisingly useful when writing algorithms and some types of encryptions.

Predict what these lines of code will evaluate to and then test them out in the REPL on the right side of your screen.

```ruby
20 % 2
20 % 3
15 % 4
0 % 5
100 % 99
4 % 0
```

## User Input

Now that you know how math works, you'll need to learn to get information FROM the user. Here's the simplest version of what that might look like:

```ruby
puts "Welcome to the Ruby calculator. What is your name?"
name = gets.chomp

puts "Welcome, #{name}!"
```

## Control Flow

The very last piece of the puzzle is coding out a program that does different things based on what the user inputs into the program.

We'll take multiple user inputs, store them in multiple variables, and then use "if-elsif-else" statements to only run the parts of the program the user wants to run.

```ruby
puts "Welcome to the Ruby Calculator"
puts "What would you like to do?"

choice = gets.chomp

if choice == "add"
  puts "What is your first number?"
  num1 = gets.chomp
  puts "What is your second number?"
  num2 = gets.chomp
  # Some other code to COMPUTE, STORE, and PRINT the answer.
elsif choice == "subtract"
  puts "Subtraction is under construction. Check back later."
  # Write a block of code to do what the addition block does, but subtracts instead.
else
  puts "Sorry, I haven't been programmed to do that yet!"
end
```

Read the code one line at a time and translate it into pseudocode:
* Prints out a greeting.
* Prints out a question.
* Gets an answer from the user in the form of a string, and stores it in a variable called choice.
* If the user's choice is "add", then the calculator will run the "add" codeblock.
    * Asks the user to type in a number.
    * Stores their answer as a string in a variable called num1.
    * Asks the user to type in another number.
    * Stores that answer as a string in a variable called num2.
    * A comment that doesn't do anything, but it DOES serve as a note to the developer about what needs to be built here.

Questions for discussion:
1. What's the difference between `=` and `==`?
2. What will happen if the user types "subtract" instead of "add"?
3. What will happen if the user types "multiply" instead of "add"?

Once students have made predictions, invite them to test it out.

###### Recommended Guided Practice
Use this as a jumping off point to talk about adding in branches. Call on a student to add in a "multiply" code block, but don't code it out. Simply add another "under construction" method.

###### Answer to question 1:
The `=` is the assignment operator. It means "take this variable and save inside it whatever comes next." This is a command - it means "make this line true," so if you write `name = "Keisha"` then the variable called name will have the string "Keisha" stored in it.
The `==` is a logical test, and it's a question. In other words if you've already assigned a string "Keisha" to a variable called name with the assignment operator like we did above, then we can use `==` to formulate a question. The expression `name == "Kevin"` is asking "is the name 'Kevin'?" and it will evaluate to **FALSE** because that's not the string stored in the variable called name. The expression `name == "Keisha"` is asking "is the name 'Keisha'?" and it will evaluate to **TRUE** because that IS the string assigned to that variable.

## The Challenge

Here's a series of incremental goals. When you hit one, you MUST celebrate it (by high-fiving a partner, by calling out "yo, I got it!" so the class can chant back "Get it! get it!", by coming to the board and adding to the room's score).

1. Make your calculator add two numbers.
2. Add in addition and subtraction functionality.
3. Add in division and exponents.
4. Add in the feature of your choice:
    * Select a feature from the brainstorm at the beginning of class
    * Debug your program to account for strange user choices, like if they type non-integers or capitalize the word "Add".
