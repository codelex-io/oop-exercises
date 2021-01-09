# Defining Classes

## Exercise #1

```js
class Person {
  constructor(name, email, phone) {
    this.name = name;
    this.email = email;
    this.phone = phone;
  }

  greet(otherPerson) {
    console.log("Hello " + otherPerson.name + ", I am " + this.name + "!");
  }
}
```

Write code to

1. Instantiate an instance object of `Person` with name of 'Sonny', email of 'sonny@hotmail.com', and phone of '483-485-4948', store it in the variable `sonny`
1. Instantiate another person with the name of 'Jordan', email of 'jordan@aol.com', and phone of '495-586-3456', store it in the variable `jordan`
1. Add a method `printContactInformation()` which prints person contact information
1. Have `sonny` greet `jordan` using the `greet` method and print contact information afterwards
1. Have `jordan` greet `sonny` using the `greet` method and print contact information afterwards

## Exercise #2

Create a class `Product` that represents a product sold in a shop.

A product has a `price`, `amount` and `name`.

The class should have:

- A constructor public Product(name, priceAtStart, amountAtStart)
- A method `printProduct()` that prints a product in the following form:

```
Banana, price 1.1, amount 13
```

Test your code by running your code and adding three products:

- "Logitech mouse", 70.00 EUR, 14 units
- "iPhone 5s", 999.99 EUR, 3 units
- "Epson EB-U05", 440.46 EUR, 1 units

Print out information about them.

Add new behaviour to the `Product` class:

- possibility to change quantity
- possibility to change price

Reflect your changes in a working application.

## Exercise #3

Create a class called `DateTime`, class constructors accepts UNIX timestamp in seconds.

Class must have:

- `getYear`, `getMonth`, `getDate`, `getHours`, `getMinutes`, `getSeconds` methods
- `prettyPrint` method which prints time in format of `2020-01-30 11:59:59`

## Exercise #4

Create an object that represents a cat. It should have properties for `tiredness`, `hunger`, `lonliness` and `happiness`

Next, write methods that increase and decrease those properties. Call them something that actually represents what would increase or decrease these things, like "feed", "sleep", or "pet".

Last, write a method that prints out the cat's status in each area. (Be creative e.g. Paws is really hungry, Paws is VERY happy.)

Bonus: Make the functions take arguments that increase or decrease arbitrary amounts

Bonus: Make the functions as arbitrary as cats are - sometimes make it so the cat doesn't _want_ to be petted.

## Exercise #5

The class `Movie` is stated below. An instance of class `Movie` represents a film.
This class has the following three class variables:

- `title`, which is a string representing the title of the movie
- `studio`, which is a string representing the studio that made the movie
- `rating`, which is a string representing the rating of the movie (i.e. PG­13, R, etc)

1.  Write a constructor for the class `Movie`, which takes the title of the movie, studio, and rating as its arguments, and sets the respective class variables to these values.
1.  Write a method `getPG()`, which takes an array of base type Movie as its argument, and returns a new array of only those movies in the input array with a rating of "PG". You may assume the input array is full of Movie instances. The returned array may be empty.
1.  Write a piece of code that creates an instance of the class `Movie`:
    - with the title “Casino Royale”, the studio “Eon Productions” and the rating “PG­13”;
    - with the title “Glass”, the studio “Buena Vista International” and the rating “PG­13”;
    - with the title “Spider-Man: Into the Spider-Verse”, the studio “Columbia Pictures” and the rating “PG”.
