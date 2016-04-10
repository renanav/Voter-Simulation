#Voter Simulation Project:  a REPL-driven voting simulation program

This is a program that allows a user to create a directory of politicians and voters. Users will be able to Create, List, Update and Delete both voters and politicians from the directory.

This is a common set of behaviour, and collectively are refered to as CRUD actions.

Voters and Politicians are both People with names. Voters however, have a *political affliliation* of either Liberal, Conservative, Tea Party, Socialist, or Neutral, while politicians have a *party affiliation* either Democrat or Republican.

Once the program starts, you will be greeted with a “main menu” that allows you to perform all the CRUD actions on either voter or politicians: (C )reate, (L)ist, (U)pdate, (D)elete.
The game will go back to the beggining when an action is completed.
When asking a user for input, I used abbreviated shortcuts when possible and if they make sense. Here, for example, I suggest allowing users to enter `c` or `C` instead of typing out `Create`. Not only does it reduce the likelihood of mistakes, but it also makes the simulation faster, both for the users and for my own testing.



##Outline
The game begins with a welcome message followed by a series of questions:

* The user's name (with audio)
* What would you like to do?
(C)reate, (L)ist, (U)pdate,  (D)elete, or (E)xit
 * When type `C`:

		A user can create a (P)olitician or a (V)oter.
		
		When choosing to create a politician: 	
		* He is givan a name
		* He is given a party
		* Politician is created
		
		When choosing to create a voter:
		* He is given a name
		* He is given a party affiliation: (L)iberal, (C)onservative, (T)ea Party, (S)ocialist, or (N)eutral
		* Voter is created

 
	* When type `L`
		* A list of all the created characters is displayed

			Example:
			
			* Politician, Marco Rubio, Republican
			* Voter, Martin Van Buren, Non-affiliated

	*	When type `U`:

		* A name to update is being requested

### If the name matches a known person
*	New name?

### If that person is a Politician
* New Party?

### If that person is just a Voter
* New affiliation?


*	When type `d`
	*	The user is able to delete a politician or a voter.


### The World

Characters don't exist in a vacuum. They need a place to exist and interact with other characters.

You can't create a chess game without modeling the board. Similarly, you can't run a voting simulation without modeling the world: the country, city, district, etc.

Your world `class` stores all the characters. When the characters interact with each other, they meet each other in this world you've created for them.

The world keeps track of:

1. All the `Voter's`
1. All the `Politician's`

The world is able to contain the characters.

