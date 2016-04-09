#Voter Simulation Project:  a REPL-driven voting simulation program

This is a program that allows a user to create a directory of politicians and voters. Users will be able to Create, List, Update and Delete both voters and politicians from the directory.

This is a common set of behaviour, and collectively are refered to as CRUD actions.

Voters and Politicians are both People with names. Voters however, have a *political affliliation* of either Liberal, Conservative, Tea Party, Socialist, or Neutral, while politicians have a *party affiliation* either Democrat or Republican.

Once the program starts, you will be greeted with a “main menu” that allows you to perform all the CRUD actions on either voter or politicians: (C )reate, (L)ist, (U)pdate, (D)elete.
The game will go back to the beggining when an action is completed.


##Outline
The game begins with a welcome message followed by a series of questions:

* The user's name (with audio)
* What would you like to do?
(C)reate, (L)ist, (U)pdate,  (D)elete, or (E)xit

* When type C:

A user can create a (P)olitician or a (V)oter.
When choosing to create a politician: 	
* He is givan a name
* He is given a party
* Politician is created

When choosing to create a voter:
* He is given a name
* He is given a party affiliation: (L)iberal, (C)onservative, (T)ea Party, (S)ocialist, or (N)eutral
* Voter is created
(S)ocialist, or (N)eutral
Then create a Voter with the collected input.


Tip! When asking a user for input, use abbreviated shortcuts when possible and if they make sense. Here, for example, we suggest allowing users to enter C instead of typing out Create. Not only does it reduce the likelihood of mistakes, but it also makes the simulation faster, both for your users and for your own testing.

List
When I type L, display a list of all the created characters.

Example:

* Politician, Marco Rubio, Republican
* Voter, Juha Mikkola, Socialist
Update
When I type U:

Who would you like to update?
Marco Rubio

# If the name matches a known person
New name?

# If that person is a Politician
New Party?

# If that person is just a Voter
New Politics?
Tip! After most of these actions, you need to return to your main menu. You may use a loop, but if you use classes and methods correctly, you should be able to control the flow by simply calling a main_menu method instead.

Delete
When I type D, I shoud be able to delete a politician or a voter.

Tip! Show a list to the user before deleting.
“`sh
Who would you like to delete?
Marco Rubio

If the name matches a known person
Are you sure?
(Y) es

It should delete that person.

## Getting Started

There are _many_ possible solutions to this problem. We _recommend_ modeling this project using `class`es. If you decide to use OOP techniques, the following are just _suggestions_.

### Characters

There are two _types_ of people in this simulation: politicians and voters. Any time you use the word "type" to describe a feature, that's your coder conscience hinting that you should be modeling each of those types with `class`es. In older versions of Ruby, the now deprecated `type` method was (almost) synonymous with `class`.

So a good start to this program is to define a `Voter` class and a `Politician` class.

There are certain features that `Voter`s and `Politician`s share, like the ability of having a name. Maybe they should be _inherited_?

When deciding whether or not to use inheritance, try to describe the relationship between the two classes. Are you using the phrases "is a" or "is a kind of"? That's your coder conscience hinting that an inheritance relationship is probably appropriate. In fact, Ruby has methods named `is_a?` and `kind_of?` for confirming these types of relationships between classes.

#### Voters

`Voter`s need to remember their:

- `name`
- `politics` (Liberal, Conservative, Tea Party, Socialist, or Neutral)

These _attributes_ should be stored somewhere in the `class`. Are they methods or instance variables?

To help you decide, try to put the feature into words.

Are you using phrases like "has a", "has one", "has many", or "contains"? That's your coder conscience telling you an attribute or instance variable is appropriate.

Are you instead using phrases like "can", "has the ability to", or "is capable of"? That's a hint you should be representing that ability with a method.


#### Politician

`Politician`s need to remember their:

- `name`
- `party` (Democrat or Republican).

### The World

Characters don't exist in a vacuum. They need a place to exist and interact with other characters.

You can't create a chess game without modeling the board. Similarly, you can't run a voting simulation without modeling the world: the country, city, district, etc.

Your world `class` stores all the characters. When the characters interact with each other, they meet each other in this world you've created for them.

The world needs to keep track of:

1. All the `Voter's`
1. All the `Politician's`

The world should be able to contain the characters.

To make testing your simulation easier, try saving the user interaction (`gets`ing input) for the end. Just plug all the data directly into your classes first, then replace all the _hard-coded_ `"strings"` with `gets.chomp`.

Another useful technique for making your code simpler is to hide long `String`s inside a `module`. Instead of

```ruby
puts "Who would you like to update?"
you can use

require './questions.rb'

puts Questions.who_to_update
A more advanced technique is to create a separate class to handle the interaction with the world. This new WorldUI would have to contain:

A @world, which the UI class uses to interact with lists of Voters and Politicians.
All the prompts that request data to send into the @world.
Organization
Organize the files for your project however you’d like. We recommend dedicating a single .rb file to each class. The "world class” should be the only place using require to pull every character class into the world.

