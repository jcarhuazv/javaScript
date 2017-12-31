# javaScript

## Loops

Allows iteration. Repeat an action for a number of times.

### While Loops:

Example:
Count up to a 100 monkeys 🐒
```javascript
var x = 0;
while (x <= 99) {
x = x + 1;
console.log( x + " monkey");
}
```

While the condition is true `(x <= 99)` will add one `x = x + 1;`, from the starting point `var x = 0;` and print `console.log( x + " monkey")` for each adition, until the condition stops being true.

Three main parts for a loop:
* When to start `var x = 0;`
* When to stop `while (x <= 99)`
* How to get to next item `x = x + 1`

"Fizzbuzz" example:
* Loop through the numbers 1 to 100
* If the number is divisible by 3, print "Fizz"
* If the number is divisible by 5, print "Buzz"
* If the number is divisible by both 3 and 5, print "FizzBuzz"
* If the number is not divisible by 3 or 5, print the number

```javascript
var x = 1;
while (x <= 100) {
   if (x % 3 === 0 && x % 5 === 0){
        console.log ("FizzBuzz"); 
    }else if (x % 5 === 0){
        console.log("Buzz");
    }else if (x % 3 === 0){
        console.log("Fizz");
    }else {
        console.log(x);
    }
    x = x + 1; 
}
```

"Nasa" example:

* Orbiter transfers from ground to internal power (50 seconds)
* auto sequence start (31 seconds)
* Activate sound suppression system (16 seconds)
* Activate burnoff system (10 seconds)
* engine start (6 seconds)
* ignition and liftoff! (0 seconds)
* If there's a task being completed, it prints out the task
* If there is no task being completed, it prints out the time as x seconds

```javascript
var x = 60;
while(x >= 0){
    if (x === 50){
        console.log ("Orbiter transfers from ground to internal power"); 
    }else if (x === 31){
        console.log("auto sequence start");
    }else if (x === 16){
        console.log("Activate sound suppression system");
    }else if (x === 10){
        console.log("Activate burnoff system");
    }else if (x === 6){
        console.log("engine start");
    }else if (x === 0){
        console.log(" ignition and liftoff!");
    }else {
        console.log( x + " seconds");
    }
x = x - 1;
}
```

### For Loops

> for ([initialExpression]; [condition]; [incrementExpression])
> statement
>  **MDN Reference**

Example:
Count up to a 100 monkeys 🐒
```javascript
for (var i = 0; i <= 100; i = i + 1 ){ 
console.log( i + " monkey");
}
```
All the neccesary information is declare in the first line.

Three main parts for a loop:
* When to start `var i = 0;`
* When to stop `i <= 100;`
* How to get to next item `i = i + 1 `

### Nested Loops

One or more loops can be nested inside of other loop.

The First/Main loop will triger the loop, then the nested one will loop until the condition is not longer true, stops, to go back to the main loop, that will trigger the nested ones everytime, until its condiction it is no longer true.

example:
```javascript
for (var x = 0; x < 4; x = x + 1) {
  for (var y = 0; y < 3; y = y + 1) {
    console.log(x + "," + y);
  }
}
```
that will print:
> 0, 0 <br>
> 0, 1 <br>
> 0, 2 <br>
> 1, 0 <br>
> 1, 1 <br>
> 1, 2 <br>
> 2, 0 <br>
> 2, 1 <br>
> 2, 2 <br>
> 3, 0 <br>
> 3, 1 <br>
> 3, 2 <br>

#### Increment and decrement 

> x++ or ++x // same as x = x + 1 <br>
> x-- or --x // same as x = x - 1 <br>
> x += 3 // same as x = x + 3 <br>
> x -= 6 // same as x = x - 6 <br>
> x *= 2 // same as x = x * 2 <br>
> x /= 5 // same as x = x / 5 <br>

## Functions

package up code so you can easily use (and reuse) a block of code. 

One parameter, in this case numIngridients:
```javascript
function cookChiken(numIngridients) {
  // code to do something here
}
```

More parameters, in this case action1 & action2:
```javascript
function doubleAction(action1, action2) {
  // code here
}
```

No parameters, empty:
```javascript
function sayHello() {
  var message = "Hello!"
  console.log(message);
}
```

### Print function

using console.log, like the example above, only displays a value.
good to test code, get feedback and debugging purposes.
`console.log` to test your code in the JavaScript console, just that.

### Return function

Return statement:
```javascript
function sayHello() {
  var message = "Hello!"
  return message; // returns value instead of printing it
}
```
Stops the execution of the function.

#### Some Practise:
Build a triangle:
```javascript
function makeLine(length) {
    var line = "";
    for (var j = 1; j <= length; j++) {
        line += "* ";
    }
    return line + "\n";
}

function buildTriangle(length) {
    var Line = "";
    for (var i = 1; i <= length; i++) {
       Line += makeLine(i);
    }
    return Line;
}

console.log(buildTriangle(10));
```
prints: <br>
![image](https://user-images.githubusercontent.com/30567608/34456985-85ec9bb2-eda4-11e7-83e5-a11aa28311ff.png)


```javascript
function laugh(num){
    var laughter = "";
    for (var x = 0; x < num; ++x ){ 
        laughter += "ha";
    }
return laughter + "!";
}
console.log(laugh(3));
```
prints:
hahaha!

### Run a function

Up to here we only have declare the functions.
For the function to do something, we have to invoke or call the function using the function name, 
followed by parentheses with any arguments that are passed into it, if it has any.
`cookChiken(6); or doubleAction(look, jump); or sayHello()`

### Parameters vs. Arguments

**Parameters** are always variables name and appears in the function declaration, that are used to store the data that's passed into a function for the function to use. <br>
**Arguments** are always going to be a value, the actual data (i.e. any of the JavaScript data types - a number, a string, a boolean, etc.) and will always appear in the code when the function is called or invoked.

### Scope

Global Scope: defined at the top level, not inside of any functions. Available everywhere.

Function Scope: variable defined inside a function. Available inside of the function it was declared in (even in functions declared inside the function).

Block Scope: //needs clarification***************************************

JavaScript Engine´ll start looking inside the current function when trying to access an identifier. 
If it does not get any results it'll continue to the next outer function to see if it can find any there. 
It will keep doing this until it reaches the global scope.

Minimize the use of global variables. Can lead to bad variable names, conflicting variable names, and messy code.

#### Shadowing or Scope overriding

This first case will shadow, since "x" it is re-asign inside of the function:

```javascript
var x = 1;

function addTwo() {
  x = x + 2;
}

addTwo();
x = x + 1;
console.log(x);
```

The way to avoid it´s by declering "x" in a new variable inside of the function.
From altering a global scope variable becomes a function scope variable.

```javascript
var x = 1;

function addTwo() {
  var x = x + 2;
}

addTwo();
x = x + 1;
console.log(x);
```

### Hoisting
//needs clarification*****************************************
To avoid bug due to this: 
always declare functions at the top of the sripts and variables at the top of the functions.
This way syntax and behavior are consistent.

### Function Expressions

A function stored inside a variable it's called a function expression.
Example:
```javascript
var catSays = function(max) {
  var catMessage = "";
  for (var i = 0; i < max; i++) {
    catMessage += "meow ";
  }
  return catMessage;
};
```
Function has no name, it is anonymous.

#### Functions as parameters

callback: A function that is passed into another function.

#### Inline function expressions
//needs clarification*****************************************
Example:
```javascript
function movies(messageFunction, name) {
  messageFunction(name);
}

movies(function displayFavorite(movieName) {
  console.log("My favorite movie is " + movieName);
}, "Vikings");
```
Returns: My favorite movie is Vikings

Example:
```javascript
function emotions(myString, myFunc) {
    console.log("I am " + myString + ", " + myFunc(2));
}
emotions("happy", function laugh(num) {
    var risa = "";
    for (var i = 0; i < num; i++){
        risa += "ha";
    }
    return risa + "!";
});
```
Returns: I am happy, haha!


Example:
```javascript
var cry = function sad() {
    return "boohoo!";
}

console.log(cry());
```
Returns: boohoo!

anonymous inline function expressions: for functions that are not going to be reused.

Example:
```javascript
var laugh = function(num) {
    var L = "";
    for (i = 0; i < num; i++){
        L += "ha";
    }
    return L + "!";
}

console.log(laugh(3));
```
Returns: hahaha!


## Arrays

Stores information.
Stores multiple values into a single, organized data structure. 
Start an array by listing values separated with commas between square brackets [].
`var donuts = ["glazed", "powdered", "jelly"];` <br>
You can store strings, like the example above or numbers, booleans or any type of data. But usually arrays are made out of same data values. <br>
We can even put an array inside an array to create a nested array.

**Arrays Elements** : Are the individual pieces of data in the array.

**Index**: the position/location of the element inside of the Array (starts counting from 0).

**Accessing Array elements**:

First put the name of the array followed by square brackets [] containing the index of the value you want to access.

Example:
```javascript
var donuts = ["glazed", "powdered", "sprinkled"];
console.log(donuts[0]);
```
Prints: "glazed"

In case we need to change the value of an element in array:
```
donuts[1] = "glazed cruller"; 
console.log(donuts[1]);
```
Prints: "glazed cruller"

### Array Properties and Methods 

[MDN documentation about Arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

JavaScript provides a large number of built-in methods for modifying arrays and accessing values in an array.
<!-- Type [] in the console to see full list -->
List:
concat()
Array()
copyWithin()
entries()
every()
fill()
filter()
find()
findIndex()
flatMap()
flatten()
forEach()
includes()
indexOf()
join()
keys()
lastIndexOf()
map()
pop()
push()
reduce()
reduceRight()
reverse()
shift()
slice()
some()
sort()
splice()
toLocaleString()
toString()
unshift()
values()

Array.lenght = find the lenght of an array.
example:
```
var donuts = ["glazed", "powdered", "sprinkled"];
console.log(donuts.length);
```
Prints: 3

Array.push & Array.pop: 
modifying arrays.

push() = 
add elements to the end of an array.
example:
```
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled"];
donuts.push("powdered");
```
Returns: 7
donuts array: ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled", "powdered"]

pop() = 
remove elements from the end of an array.
example:
```
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled", "powdered"];

donuts.pop(); 
donuts.pop();
donuts.pop();
```
Returns: "cinnamon sugar"
donuts array: ["glazed", "chocolate frosted", "Boston creme", "glazed cruller"]

splice() =
powerful method.
changes the contents of an array by removing existing elements and/or adding new elements.
allows you to specify the index location to add new elements, as well as the number of elements you'd like to delete (if any).
sintax:
`array.splice(start[, deleteCount[, item1[, item2[, ...]]]])`

Examples:
Remove 0 elements from index 2, and insert "drum":
```
var myFish = ['angel', 'clown', 'mandarin', 'sturgeon'];
var removed = myFish.splice(2, 0, 'drum');
```
result:
myFish is ["angel", "clown", "drum", "mandarin", "sturgeon"] 
removed is [], no elements removed

Remove 1 element from index 3:
```
var myFish = ['angel', 'clown', 'drum', 'mandarin', 'sturgeon'];
var removed = myFish.splice(3, 1);
```
result:
removed is ["mandarin"]
myFish is ["angel", "clown", "drum", "sturgeon"]

More examples [MDN Splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)

### Array Loops

Example:
```javascript
var donuts = ["jelly donut", "chocolate donut", "glazed donut"];

for (var i = 0; i < donuts.length; i++) {
    donuts[i] += " hole";
    donuts[i] = donuts[i].toUpperCase();
}
```
Prints: 
donuts array: ["JELLY DONUT HOLE", "CHOCOLATE DONUT HOLE", "GLAZED DONUT HOLE"]

**The forEach() loop**
 alternative way to iterate over an array
 Parameters: can take up to 3.

Example:
```javascript
var donuts = ["jelly donut", "chocolate donut", "glazed donut"];

donuts.forEach(function(donut) {
  donut += " hole";
  donut = donut.toUpperCase();
  console.log(donut);
});
```
Prints: 
JELLY DONUT HOLE
CHOCOLATE DONUT HOLE
GLAZED DONUT HOLE

forEach() method calls the function once for each element in the array.
Example:
```javascript
words = ["cat", "in", "hat"];
words.forEach(function(word, num, all) {
  console.log("Word " + num + " in " + all.toString() + " is " + word);
});
```
Prints:
Word 0 in cat,in,hat is cat
Word 1 in cat,in,hat is in
Word 2 in cat,in,hat is hat

Example:
```javascript
var test = [12, 929, 11, 3, 199, 1000, 7, 1, 24, 37, 4,
    19, 300, 3775, 299, 36, 209, 148, 169, 299,
    6, 109, 20, 58, 139, 59, 3, 1, 139
];

test.forEach(function(value,index) {
    if(value % 3 === 0){
      test[index] += 100;
    }
});

console.log(test);
```
Prints:
[ 112,
  929,
  11,
  103,
  199,
  1000,
  7,
  1,
  124,
  37,
  4,
  19,
  400,
  3775,
  299,
  136,
  209,
  148,
  169,
  299,
  106,
  109,
  20,
  58,
  139,
  59,
  103,
  1,
  139 ]

**Map**
Returns a new array from an existing array.
Accepts only 1 argument.

Example:
```javascript
var donuts = ["jelly donut", "chocolate donut", "glazed donut"];

var improvedDonuts = donuts.map(function(donut) {
  donut += " hole";
  donut = donut.toUpperCase();
  return donut;
});
```
Prints:
donuts array: ["jelly donut", "chocolate donut", "glazed donut"]
improvedDonuts array: ["JELLY DONUT HOLE", "CHOCOLATE DONUT HOLE", "GLAZED DONUT HOLE"]

Example:
```javascript
var bills = [50.23, 19.12, 34.01,
    100.11, 12.15, 9.90, 29.11, 12.99,
    10.00, 99.22, 102.20, 100.10, 6.77, 2.22
];

var totals = bills.map(function(amount){
    amount += Number (0.15*amount)
    return Number(amount.toFixed(2));
})

console.log(totals);
```
Prints:
[ 57.76,
  21.99,
  39.11,
  115.13,
  13.97,
  11.38,
  33.48,
  14.94,
  11.5,
  114.1,
  117.53,
  115.11,
  7.79,
  2.55 ]

### Arrays in Arrays


Example:
```javascript
var donutBox = [
  ["glazed", "chocolate glazed", "cinnamon"],
  ["powdered", "sprinkled", "glazed cruller"],
  ["chocolate cruller", "Boston creme", "creme de leche"]
];

for (var row = 0; row < donutBox.length; row++) {
  for (var column = 0; column < donutBox[row].length; column++) {
    console.log(donutBox[row][column]);
  }
}
```
Prints:
"glazed"
"chocolate glazed"
"cinnamon"
"powdered"
"sprinkled"
"glazed cruller"
"chocolate cruller"
"Boston creme"
"creme de leche"
![image](https://user-images.githubusercontent.com/30567608/34461587-2d284776-ee2e-11e7-8b45-d7c69f7ecccc.png)

Example:
```javascript
var numbers = [
    [243, 12, 23, 12, 45, 45, 78, 66, 223, 3],
    [34, 2, 1, 553, 23, 4, 66, 23, 4, 55],
    [67, 56, 45, 553, 44, 55, 5, 428, 452, 3],
    [12, 31, 55, 445, 79, 44, 674, 224, 4, 21],
    [4, 2, 3, 52, 13, 51, 44, 1, 67, 5],
    [5, 65, 4, 5, 5, 6, 5, 43, 23, 4424],
    [74, 532, 6, 7, 35, 17, 89, 43, 43, 66],
    [53, 6, 89, 10, 23, 52, 111, 44, 109, 80],
    [67, 6, 53, 537, 2, 168, 16, 2, 1, 8],
    [76, 7, 9, 6, 3, 73, 77, 100, 56, 100]
];

for (var row = 0; row < numbers.length; row++) {
  for (var column = 0; column < numbers[row].length; column++) {
    if(numbers[row][column] % 2 === 0){
        numbers[row][column] = "even";
    }else{
       numbers[row][column] = "odd"; 
    }
  }
}
console.log(numbers);
```
Prints:
[ [ 'odd','even','odd','even','odd','odd','even','even','odd','odd' ],
  [ 'even','even','odd','odd','odd','even','even','odd','even','odd' ],
  [ 'odd','even','odd','odd','even','odd','odd','even','even','odd' ],
  [ 'even','odd','odd','odd','odd','even','even','even','even','odd' ],
  [ 'even','even','odd','even','odd','odd','even','odd','odd','odd' ],
  [ 'odd','odd','even','odd','odd','even','odd','odd','odd','even' ],
  [ 'even','even','even','odd','odd','odd','odd','odd','odd','even' ],
  [ 'odd','even','odd','even','odd','even','odd','even','odd','even' ],
  [ 'odd','even','odd','odd','even','even','even','even','odd','even' ],
  [ 'even','odd','odd','even','odd','odd','odd','even','even','even' ] ]



## Source of the materials:
* MDN
* Udacity Google Challenge Scholarship: Front-End Web Dev 2017-2018