# Composition

## Exercise #1

- Create a class `BookList`
- Create another class called `Book`

- `BookList` should have the following properties:
  - Number of books marked as read
  - Number of books marked not read yet
  - A reference to the next book to read (book object)
  - A reference to the current book being read (book object)
  - A reference to the last book read (book object)
  - An array of all the Books
- Each `Book` should have several properties:
  - Title
  - Genre
  - Author
  - Read (true or false)
  - Read date, can be blank, otherwise needs to be a [JS Date() object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)
- Every `Booklist` should have a few methods:

  - .add(book)
    - should add a `book` to the books list.
  - .finishCurrentBook()
    - should mark the `book` that is currently being read as "read"
    - Give it a read date of new Date(Date.now())
    - Change the last `book` read to be the book that just got finished
    - Change the current `book` to be the next book to be read
    - Change the next `book` to be read property to be the first unread book you find in the list of books

- `Booklist` and `Books` might need more methods than that. Try to think of more that might be useful.

## Exercise #2

Create a class `Card`. A `card` object will have 2 properties:

- `point` - the point value of the card: a number between 1 and 13.
- `suit` - the suit of the card: one of diamonds, clubs, hearts and spades.

A card will be created thus:

```js
const myCard = new Card(5, "diamonds");
```

And you can access the individual properties like:

```js
myCard.point; // 5
myCard.suit; // 'diamonds'
```

Add a `getImageUrl()` method to card objects by adding it as a member method to your Card class. The method should return the URL path to the png image file for the card.

```js
myCard.getImageUrl(); // 'images/5_of_diamonds.png'
```

A `hand` is simply represented as a collection of cards, but it would also be convenient for a hand to be able to return it's point value. We would like to be able to do this with a Hand constructor:

```js
const myHand = new Hand();
myHand.addCard(new Card(5, "diamonds"));
myHand.addCard(new Card(13, "spades"));
myHand.getPoints(); // 15
```

Implement a Hand class that will allow the code above to work.

A `deck` is also represented as a collection of cards, but it would also be convenient for it to be able to shuffle itself, and be asked to draw a card. We would like to be able to do this with a `Deck` constructor:

```js
const myDeck = new Deck();
myDeck.draw(); // Card {point: 6, suit: "clubs"}
myDeck.draw(); // Card {point: 1, suit: "spades"}
myDeck.shuffle();
myDeck.numCardsLeft(); // 50
```

Implement a Deck class that will allow for the above code to work.

## Exercise #3

In this exercise, we make organisms and groups of organisms which move around each other. The position of the organisms is reported by using a bidimensional coordinate system. Each position is defined by two numbers, the x and y coordinates. The x coordinate tells us how far from the "point zero" the position is horizontally, whereas the y coordinate tells u how far the position is vertically. If you have got doubts of what a coordinate system is, you can read more information in Wikipedia, for instance.

Together with the exercise, you find the interface `Movable`, which represents things that can be moved from one place to another. The interface contains the method `move(dx, dy)`. The parameter `dx` tells us how much the object moves on the x axis and `dy` tells us about the movement on the y axis.

Implement the classes `Organism` and `Group`, which are both movable.

### Implementing Organism

Create the class `Organism`; let `Organism` implement the interface `Movable`. Organisms have to know their own position (x and y coordinates). The API of Organism has to be the following:

- `constructor(x, y)`, it receives the x and y initial coordinates of the object
- `toString()` it creates and returns a string which represents the object. The form should be the following "x: 3; y: 6". Note that the coordinates are separated by a semicolon (;)
- `move(dx, dy)`; it moves the object as much as it is specified by the arguments. The variable dx contains the x coordinate of the movement, whereas dy contains the y coordinate of the movement. For instance, if the value of the variable dx is 5, the object variable x has to be increased by five

Try our the functionality of `Organism` using the following code.

```ts
const organism = new Organism(20, 30);
console.log(organism);
organism.move(-10, 5);
console.log(organism);
organism.move(50, 20);
console.log(organism);
```

```
x: 20; y: 30
x: 10; y: 35
x: 60; y: 55
```

### Implementing Group

Create the class `Group`; `Group` implements the interface `Movable`. The `Group` is made of various different objects which implement the interface `Movable`, and they have to be stored into a list construction, for instance.

The class `Group` should have the following API.

- `toString()`; it returns a string which describes the position of the group organisms, each organism is printed in its own line.
- `addOrganism(movable)`; it adds a new objects which implements the interface `Movable` to the group.
- `move(dx, dy)`; it moves a group as much as it is defined by the arguments. Note that you will have to move each group organism.

Try out your program functionality with the following code.

```ts
const group = new Group();
group.addOrganism(new Organism(73, 56));
group.addOrganism(new Organism(57, 66));
group.addOrganism(new Organism(46, 52));
group.addOrganism(new Organism(19, 107));
console.log(group);
```

```
x: 73; y: 56
x: 57; y: 66
x: 46; y: 52
x: 19; y: 107
```
