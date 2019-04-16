<h1>JavaScript</h1>

This document aims to highlight the basic of Javascript. <br>
References: [Free Code Camp](https://www.youtube.com/watch?v=PkZNo7MFNFg)

<h2>Data-type and variables</h2>

Seven different data types.
1. undefined
2. null
3. boolean
4. string
5. symbol
6. number
7. object

Three ways to declare variables. **Good Practice: Use only let and const**

<h4> 1) Using var keyword</h4>

* var can be use throughout the program.

```javascript
var myName = "Boo"; //String variable
var myNumber = 100; //number variable
var decimalNum = 6.993 //floating point number
```
<h4> 2) Using let keyword</h4>

* let will only be used within the scope where we declare.

```javascript
let ourName = "bandName";
```

<h4> 3) Using const keyword</h4>

* const is read only cannot be change.

```javascript
const pi = 3.14;
```

<h4>Difference Between var and let Keyword</h4>

* let does not let you declare a variable twice.
* If we change all the var in the following code to let, we will get an error.
* If we declared a variable using var, it is declared globally.

```javascript
var catName = "Beau";
var quote;

var catName = "Quincy";

function catTalk(){
  "use strict"; //enable strict mode, to catch common coding mistake and unsafe action.
  
  catName = "Oliver";
  quote = catName + " says Meow!";
}

catTalk();
```

<h4>Prevent Object Mutation</h4>

* Even though const is read only, the data can be mutated.
* Need to freeze an object to prevent that.
* Object.freeze(obj)

```javascript
function freezeObj() {
  "use strict"
  const MATH_CONSTANTS = {
    PI: 3.14
  };
  
  Object.freeze(MATH_CONSTANTS); //freeze MATH_CONSTANTS to prevent it from changing.
  
  try{
    MATH_CONSTANTS.PI = 999; //will run if MATH_CONSTANTS not frozen.
  } catch (ex) {
    console.log(ex);
  }
  return MATH_CONSTANTS.PI;
}

const PI = freezeObj();
console.log(PI); // will be 999 if MATH_CONSTANTS not frozen.
```



<br>
<br>

<h2>Console log</h2>

Allow you to print onto the console.

```javascript
console.log("Hello World");

var a = 10;
console.log(a);
```

<br>
<br>

<h2>Operations</h2>

Performing operations is the same as in other programming language.

<h4>Basic operations</h4>

```javascript
var a = 5;
var b = 10;

var sum = a + b;
var diff = a - b;
var mul = a * b;
var div = a / b;
var remainder = a % b;
```

<h4>Increment and Decrement</h4>

```javascript
var a = 10;

var increment = a++;
var decrement = a--;
```

<h4>Compound Assignment with Augmented Operations</h4>

```javascript
var a = 10;
var b = 5;
var c = 4;
var d = 15

a += 12; // a = a + 12
b -= 10; // b = b - 10 
c *= 11; // c = c * 11
d /= 3; // d = d / 3
```

<br>

<h2>Strings</h2>

<h4>String Declaration</h4>

* String can be declared using " ".
```javascript
var myString = "This is a String";
```

<h4>Escape Character</h4>

* Everything inside " " is a String, it denotes end and start of a String.
* What if I want to use " " inside a String?
* Solution: Add \ before each " inside " ".
```javascript
var myString = "Adding \"double quote\" inside a String."
```

* Below is a detailed output list using escape char.

|Code |Output         |
|-----|---------------|
|\\'  |Single quote   |
|\\"  |Double quote   |
|\\\  |Backslash      |
|\\n  |New line       |
|\\r  |carriage return|
|\\t  |tab            |
|\\b  |Backspace      |
|\\f  |Form feed      |


<h4>Quoting without " \ " character</h4>

* To use " " in a string without the escape character, we can simply use single quote to start and end the string.
* Double or single quote are both allowed in Javascript.
* To use both single and double quote in a string, we can use \` ` to start and end the string.
```javascript
var myStr = 'This is a "String" with quote.'
var myStr = `'This is a "String" with quote.'`
```

<h4>String Concatenation</h4>

* String can be concatenate using the "+" operator.

```javascript
var ConcatStr = "This comes first. " + "This comes second."
ConcatStr += " Another additional string."
```

<h4>Constructing Strings with Variables</h4>

```javascript
var myStr = "This is a string too."
var Str = "This is a string. " + myStr;
```

<h4>Finding Length of String</h4>

```javascript
var strLen = 0;
var myStr = "Hello World";

strLen = myStr.length;
```

<h4>Bracket Notation</h4>

* We can find any char in a string using bracket notation.
* Javascript uses 0-based indexing as well.

```javascript
var myStr = "HelloWorld";
var firstChar = myStr[0];

var lastChar = myStr[myStr.length-1];
```

<h4>String Immutability</h4>

* String are immutable, i.e. cannot be alter once created.
* Still, they can be change.

```javascript
var myStr = "Jello World";
myStr[0] = "H"; //This will give an error

myStr = "Hello World" //Must do this
```

<br>

<h2>Arrays</h2>

<H4>Using Array to Store Variables</h4>

* Elements inside an array is separated by a comma. 

```javascript
var arr = ["John", 23]; //first element is a string, 2nd is a number.
var aar2 = ["One", 1, "Two", 2];
```

<h4>Nested Array</h4>

```javascript
var arr = [["Universe", 42], ["Everything", 101010]];
//An array containing 2 arrays
```

<h4>Getting an Element from an array</h4>

```javascript
var dataArray = [50, 60, 70, 80];
var fifty = dataArray[0];
```

<h4>Modifying Array Data with Indexes</h4>

* Unlike string, we can modify data with indexes.

```javascript
var arr = [50, 60, 70, 80];
arr[2] = 75;
```

<h4>Access Multi-Dimensional Arrays with Indexes</h4>

```javascript
var arr = [[1,2,3], [4,5,6], [7,8,9], [[10,11,12], 13, 14]];

var myData = arr[0][0]; //1
var myData2 = arr[3][0][0]; //10
```

<h4>Manipulate Arrays with push()</h4>

* Use to append data to an array.

```javascript
var arr = ["Stimpson", "J", "Dog"];
arr.push(["happy", "joy"]);
//array now equals to ["Stimpson, "J", "Dog", ["happy, "joy"]];
```

<h4>Manipulate Arrays with pop()</h4>

* Use to remove last element from an array.

```javascript
var arr = [1,2,3];
arr.pop();
//arr now equals [1,2]
```

<h4>Manipulate Arrays with shift()</h4>

* Similar to pop(), but...
* Remove 1st element instead of last.

```javascript
var arr = [1,2,3];
arr.shift();
//arr now equals [2,3]
```

<h4>Manipulate Arrays with unshift()</h4>

* Similar to push() but...
* Add element to first element instead of last.

```javascript
var arr = [1,2,3];
arr.unshift(0);
//arr now equals [0,1,2,3]
```

<h4>Mutate an Array Declared With const</h4>

* We cannot reassign an array declared with const, but we can change the element using bracket notation.

```javascript
const arr = [2, 5, 7];

function mutateArr() {
  "use strict";
  
  //arr = [5 , 2, 7]; //This will give an error
  arr[0] = 5;
  arr[1] = 2;
  arr[2] = 7;
}
console.log(arr);
```

<h4>Using Spread Operator to Evaluate Arrays In-Place<h4>

* Just like a rest operator, 3 dots.
* In layman term, to make a copy of an array.
* Previously, assigning an array to another array (arr1 = arr2) does not make a copy, but will make both equal.
* If arr1 = arr2, whatever we change in one array the other will change as well.

```javascript
const arr1 = ['Jan', 'FEB', 'MAR', 'APR', 'MAY'];
let arr2;
(function() {
  //arr2 = arr1; //without spread operator
  arr2 = [...arr1]; //using spread operator
  arr1[0] = 'potato'
})();
console.log(arr2); //first element will be potato before using spread operator
```


<br>
<br>

<h2>Functions</h2>

* Functions can be created just like other language.

```javascript
var a = 5;
var b = 10;
var sum = Addition(a, b);

function Addition(a, b) {
  console.log(a + b);
}
```

<h4>Function Scope</h4>

* Function can be declared without the "var" keyword, this will make the variable global.
* If a variable is declared with a var keyword inside a function, that variable is only available in that function.
* Global variable is created outside of a function.

```javascript
var myGlobal = 10;

function funct1(){
  anotherGlobal = 20; //no var keyword, global
  var funct1Var = 10; //scope on in this function.
}

function  funct2() {
  var output = "";
  if(typeof myGlobal != "undefined"){
    output += "Globa; variable: " + myGlobal;
  }
  if(typeof anotherGlobal != "undefined"){
    output += "anotherGlobal: " + anotherGlobal;
  }
}
```

<h4>Global vs. Local Scope in Functions</h4>

* It is possible to have a local and global variable with the same name.
* The local variable will take precedence over the global variable.

```javascript
var outerWear = "T-Shirt"; //global variable

function myOutfit() {
  var outerWear = "Sweater"; //local variable
  return outerWear
}

console.log(myOutfit()); //sweater
console.log(outerWear); //T-Shirt
```

<h4>Understanding Undefined Value Returned from a Function</h4>

* Function can return value, but can choose not to as well.

```javascript
var sum = 0;
function add(){
  sum += 3;
}

function addFive(){
  sum += 5;
}

console.log(add()); //undefined since no return value
```

<h4>Using Arrow Functions to Write Concise Anonymous Functions</h4>

* A function with no name is a anonymous function.

```javascript
var magic = function() {
  return new Date();
};

var magic = () => { // same as above, remove function keyword and add an arrow
  return new Date()''
};
```

<h4>Write Arrow Functions with Parameters</h4>

* We can pass parameters to arrow functions.

```javascript
var myConcat = function(arr1, arr2){
  return arr1.concat(arr2);
};
console.log(myConcat([1,2], [3,4,5]));
```

```javascript
const myConcat = (arr1, arr2) => arr1.concat(arr2); // can be shorten since only got 1 return statement, remove return keyword and curly bracket.

console.log(myConcat([1,2], [3,4,5]));
```

<h4>Higher Order Arrow Functions</h4>

* Arrow functions work well with functions taking function as argument.

```javascript
const realNumArr = [4, 5.6, -9.8, 3.14, 42, 6, 8.34, -2];

const squareList = (arr) => {
  const squaredIntegers = arr.filter(num => Number.isInteger(num) && num > 0).map(x => x * x) // result of arr is squared +ve integer;
  return squaredIntegers;
}

const squaredIntegers = squareList(realNumArr);
console.log(squaredIntegers);
```

<h4>Using Rest Operator with Function Parameters</h4>

* A rest operator is 3 dots.
* Use to pass into a function, good when we do not have fixed number of arguments.

```javascript
const sum = (function() {
  return function sum(...args){
    return args.reduce((a,b) => a + b, 0);
  };
})();
console.log(sum(1, 2, 3, 4)); // 4 arguments, can have more or fewer.
```

<h4>Queue</h4>

* Understanding how queue works.
* push() adds an item to the end of the queue.
* shift() remove the first element of the queue.

```javascript
function nextInLine(arr, item) {
  arr.push(item); //add item to the rear of arr
  return arr.shift(); //remove first element of arr
}

var testArr = [1,2,3,4,5];

console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```

<br>
<br>

<h2>Boolean Values</h2>

* True or False only.

<h4>Check equal</h4>

* Want to check if 2 values are the same.
* Like in other programming language, use ==.

```javascript
function equate(val){
  if(val == 12){
    return "Equal";
  }
  return "Not Equal";
}

equate(10);
```

<h4>Strict equality Operator</h4>

* == will convert both comparable to the same type.
* 3 == '3' will equate to true.
* === does not do any conversion.
* 3 === 3 is **true**, 3 === '3' is **false**

<h4>Inequality, Strict Inequality and Logical Comparing Operator</h4>

|Code|Description      |
|----|-----------------|
|!=  |Not equal, convert so both data type are the same.|
|!== |Strict inequality, does not convert both data type|
|\>  |More than         |
|>=  |More than or equal|
|<   |Less than         |
|<=  |Less than or equal|

<br>
<br>

<h2>Switch Statements</h2>

<h4>Typical Swtich Case</h4>

* Check the value of val, if it is 1, return alpha, 2 returns Beta and so on.

```javascript
function caseInSwitch(val){
  var answer = "";
  switch (val) {
    case 1: answer = "alpha"; break;
    case 2: answer = "Beta"; break;
    case 3: answer = "Gamma"; break;
    case 4: answer = "Delta"; break;
    default: answer = "Stuff"; break;
  }
  return answer;
}
console.log(caseInSwitch(1));
```

<h4>Multiple Identical Options in Switch Statement</h4>

* Multiple input give same output.
* If val is 1, 2 or 3, return Low and so on.

```javascript
function sequentialSize(val){
  var answer = "";
  switch(val){
    case 1:
    case 2:
    case 3:
      answer = "low"; break;
    case 4:
    case 5:
    case 6:
      answer = "Mid"; break;
    case 7:
    case 8:
    case 9:
      answer = "High"; break;
  }
}
```

<br>
<br>

<h2>Objects</h2>

* Anything before the colon is a property

```javascript
var Dog = {
  "name": "Xiao Qiang",
  "age": 10,
  "favFood": ["Fish", "Chicken", "Beef"]
};
```

<h4>Accessing Object Properties with Dot Notation</h4>

```javascript
var Dog = {
  "name": "Xiao Qiang",
  "age": 10,
  "favFood": ["Fish", "Chicken", "Beef"]
};

var nameVal = Dog.name;
var ageVal = Dog.age;
```

<h4>Accessing Object Properties with Bracket Notation</h4>

* Required when there is a white space in object's properties.

```javascript
var Restaurant = {
  "an entree" : "burger",
  "my side" : "chips",
  "the drink" : "water"
};

var myEntree = Restaurant["an entree"];
var myDrink = Restaurant["the drink"];
```

<h4>Accessing Object Properties with Variables</h4>

```javascript
var testObj = {
  12: "Namath",
  16: "Montana",
  19: "Unitas"
};

var playerNumber = 16;
var player = testObj[playerNumber];
```

<h4>Using Dot Notation to Update Object Properties</h4>

```javascript
var Dog = {
    "name": "Xiao Qiang",
    "age": 10,
    "favFood": ["Fish", "Chicken", "Beef"]
}

Dog.name = "Da Qiang";
```

<h4>Add New Properties to an Object</h4>

* Can do so using dot or bracket notation.

```javascript
var Dog = {
    "name": "Xiao Qiang",
    "age": 10,
    "favFood": ["Fish", "Chicken", "Beef"]
}

Dog.bark = "woof"; //add a new property to dog using dot notation
Dog["Status"] = "Sleep"; //using bracket notation
```

<h4>Deleting Properties of an Object</h4>

* Can do so using the delete keyword.

```javascript
var Dog = {
    "name": "Xiao Qiang",
    "age": 10,
    "favFood": ["Fish", "Chicken", "Beef"]
}

delete Dog.favFood;
```

<h4>Checking if an Object Has A Property</h4>

```javascript
var Dog = {
    "name": "Xiao Qiang",
    "age": 10,
    "favFood": ["Fish", "Chicken", "Beef"]
}

function checkObj(checkProp) {
  if(Dog.hasOwnProperty(checkProp)){
    return Dog[checkProp];
  } else {
    return "Not Found";
  }
};
```

<h4>Manipulating Complex Objects</h4>

* Similar to JSON.
* 2 Objects in music array.

```javascript
var music = [{
    "Artist": "Billy Joel",
    "Title": "Piano Man",
    "Release_year": 1973,
    "Formats": ["CD", "8T", "LP"],
    "Gold": true
  },
  {
    "Artist": "ME",
    "Title": "Briyani",
    "Release_year": 2019,
    "Formats": ["Youtube", "CD", "Blu-ray"],
    "Gold": false
  }];


var heavyMetal = [{
  "Artist": "Metallica",
  "best_Song": "Enter Sandman",
  "Format": ["CD", "Blu-ray", "Youtube"],
  "Gold": true
},
{
  "Artist": "GnR",
  "best_Song": "SweetChild",
  "Format": ["CD", "Blu-ray", "Youtube"],
  "Gold": true
}];
```

<h4>Accessing Nested Objects</h4>

* We can use multiple dots or brackets notation to access nested objects
* A car has interior (inside), inside there is a glove box which contains a map.
* Recall {} denotes an object.

```javascript
var storage = {
  "car": {
    "inside":{
      "glove box": "maps",
      "passenger seats": "crumbs"
    },
    "outside": {
      "trunk": "tools"
    }
  }
};

var gloveBoxContent = storage.car.inside["glove box"];
console.log(gloveBoxContent); //should print out maps
```

<h4>Accessing Nested Arrays</h4>

```javascript
var plants = [{
  "type": "flowers",
  "list": ["rose", "turnips", "dandelion"]
},
{
  "type": "trees",
  "list": ["fir", "maple", "birch"]
}];

var myRose = plants[0].list[0];
console.log(myRose);

var myMaple = plants[1].list[1];
console.log(myMaple);
```

<h4>Update a List Exercise</h4>

* Each record has a label.
* Write a function to update the property and value.

```javascript
var record = {
  "1111": {
    "Artist": "Metallica",
    "Year": 1990
    "Tracks": ["Enter Sandman", "Master of Puppet", "Nothing Else Matter"]
  },
  "1112": {
    "Artist": "GnR",
    "Year": 1987,
    "Tracks": ["Welcome to the Jungle", "Sweet Child", "November Rain"]
  },
  "1113": {
    "Artist": "Robert Palmer",
    "Tracks": []
  },
  "1114": {
    "Tracks": ["Does your mother know", "Mama Mia"]
  }
}

var CollectionCopy = JSON.parse(JSON.stringify(record)); //Before update
updateRecords("1111", "Tracks", "Seek and Destroy");
CollectionCopy = JSON.parse(JSON.stringify(record)); //After Update

function updateRecords(id, prop, value){
  
  if (value ===""){ //empty value, delete that property
    delete record[id][prop];
  } else if (prop === "Tracks"){
    record[id][prop] = record[id][prop] || [];
    record[id][prop] = push[value];
  } else {
    record[id][prop] = value;
  }
  return record;
}
```

<h4>Destructuring Assignment to Assign Variables from Objects</h4>

* The following code shows the traditional way to assign objects parameter to its own variable.

```javascript
var voxel = {x: 3.6, y: 7.4, z: 6.54};

var x = voxel.x;
var y = voxel.y;
var z = voxel.z;
```

* Using destructuring

```javascript
var voxel = {x: 3.6, y: 7.4, z: 6.54};

const {x:a, y:b, z:c} = voxel; //destructuring syntax
```

* Example

```javascript
const AVG_TEMPERATURES = {
  today: 77.5;
  tomorrow: 79;
};

function getTempofTmr(AvgTemperatures){
  "use strict"
  
  const {tomorrow:tempOfTomorrow} = avgTemperatures; //get "tomorrow" from AVG_TEMPERATURES obj (avgTemperatures) and assign it to "tempOfTomorrow"
  return tempOfTomorrow;
}

console.log(getTempofTmr(AVG_TEMPERATURES));
```
<br>
<br>

<h2>Loops</h2>

* Similar to other programming language.

<h4>While Loops</h4>

```javascript
var i = 0;
var arr = [];
while (i < 5){
  arr.push(i);
  i++;
} 
console.log(arr);
```

<h4>For Loop</h4>

```javascript
var arr = [];
for (var i = 0; i < 10; i++){
  arr.push(i);
}
console.log(arr);
```

<br>
<br>

<h2>Random</h2>

<h4>Generating Random Fractions</h4>
* We can use Math.random() function to generate random fraction.

```javascript
function randomFunction() {
  
  return Math.random();
  
}
```

<h4>Generating Random Whole Numbers<h4>

* Can use Math.floor() to achieve.
* Math.floor() round down to the nearest whole number.

```javascript
var randWholeNumberBetween0and9 = Math.floor(Math.random() * 20); //get a whole number between 0 and 20 exclusively

function generateRandWholeBetween(val){
  return Math.floor(Math.random() * val);
}

console.log(generateRandWholeBetween(10));
```

<h4>Generating Random Number Within a Range</h4>

```javascript
function randomRange(min, max) {
  return Math.floor(Math.random() * (max-min+1)) + min;
  
}
```

<br>
<br>

<h2>Parsing</h2>

<h4>Using the parseInt Function</h4>

* Takes a string and returns an int.
* If a string cannot be coverted, will return NAN (Not a Number).

```javascript
function convertToInteger(str) {
  return parseInt(str);
}
convertToInteger("56");
```


<h4>Use the parseInt Function with a Radix</h4>

* Specify base of number in a string, i.e. base 2 is binary, base 10 is decimal

```javascript
function convertToInt(str) {
  return parseInt(str, 2); //binary
}
convertToInt("10011");
```

<br>
<br>

<h2>Advance Conditional Statement</h2>

<h4>Using the Conditional (Ternary) Operator</h4>

* Aka one line if-else statement.
* condition ? statement-if-true : statement-if-false

```javascript
function checkEqual(a, b) {
  return a === b ? true : false;
}
```

<h4>Use Multiple Conditional (Ternary) Operators</h4>

* Conditional operators can be nested.
* The following is a function to check sign.
* Returns positive if number is positive, negative if number is negative
* statement-if-false can be replaced with a condition, in case statement-if-true is not true.

```javascript
function checkSign(num) {
  return num > 0 ? "positive" : num < 0 ? "negative" : "zero";
}
```