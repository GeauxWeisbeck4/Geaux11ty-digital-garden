- # Data Types
    - ### Backslashes (\)
        - We use the backslash escape character when we want to put quotes within strings
        - ```javascript
var sayHello = 'Hello world! \'I am a JavaScript programmer.\' ';
document.write(sayHello);```
        - Other special characters:
        - ![](local-asset://Geaux-Notes/bfWIlOTaFV.png)
        - 
- ## Arithmetic Operators
    - ![](local-asset://Geaux-Notes/gc8n2o2SzL.png)
    - 
- Increment ++ and Decrement --
    - ![](local-asset://Geaux-Notes/Nf9mzv6QGU.png)
- ## Assignment Operators
    - ![](local-asset://Geaux-Notes/DdUh1xI7jY.png)
- ## Comparison Operators
    - ![](local-asset://Geaux-Notes/384r7JkVT5.png)
    - Show that time < or equal to 12, print "am". If it is greater than 12, print "pm"
    - ```javascript
function main() {
    var hour = parseInt(readLine(), 10);
    // Your code goes here
    time = hour >= 0 && hour <= 12 ? "am" : "pm";
    console.log(time)
}```
- ## Logical Operators
    - ![](local-asset://Geaux-Notes/LZdMyfAV8o.png)
    - Write function for am = 0 ->12 hours anything after that is pm
        - ```javascript
function main() {
    var hour = parseInt(readLine(), 10);
    // Your code goes here
    time = hour >= 0 && hour <= 12 ? "am" : "pm";
    console.log(time)
}```
- # The If Statement
    - ```javascript
var month = readLine()
//your code goes here
if (month == 'august') {
    console.log("vacation")
}```
    - ## The Else Statement
    - ```javascript
var height = parseFloat(readLine(), 10)
//your goes code here
if (height > 2.45) {
    console.log("new record")
} else {
    console.log("not this time")
}```
- ## The else-if statement
    - ```javascript
var score = parseInt(readLine(), 10)
/*
88 and above => excellent
40-87   => good
0-39 => fail
*/
// your code goes here
if (score >= 88) {
    console.log("excellent")
} else if (score >=40 && score < 88) {
    console.log("good")
} else {
    console.log("fail")
}```
- ## The Switch Statement
    - ```javascript
function main() {
    var themeNumber = parseInt(readLine(), 10)
    /*
    1 - Light
    2 - Dark
    3 - Nocturne
    4 - Terminal
    5 - Indigo
    */
    // Your code here
    switch ( themeNumber ){
        case 1:
        console.log("Light")
        break
        case 2:
        console.log("Dark")
        break
        case 3:
        console.log("Nocturne")
        break
        case 4:
        console.log("Terminal")
        break
        case 5:
        console.log("Indigo")
        break
    }
}```
- ## The For Loop
    - ```javascript
var expression = readLine();

//your code goes here
for (var i = 0; i < 3; i++) {
    console.log(expression)
}```
    - ![](local-asset://Geaux-Notes/amTyQejvtV.png)
- ## The While Loop
    - ```javascript
function main() {
    var seconds = parseInt(readLine(), 10)
    // Your code here
    while(seconds >= 0){
        console.log(seconds)
        seconds--
    }
}```
    - ![](local-asset://Geaux-Notes/GGC1gU1wyL.png)
- ## The Do While Loop
- Example:
    - ```javascript
var countOfRooms = 15;
// Your code here
for (i=1; i <= 16; i++){
    if (i == 13)
    continue;
    console.log(i)
}```
- ## Break and Continue
- ## The snail in the well
    - The snail climbs up 7 feet each day and slips back 2 feet each night.
    - How many days will it take the snail to get out of a well with the given depth?
    - **Sample Input:**
    - 31
    - **Sample Output:**
    - 6
    - **Explanation**: Let's break down the distance the snail covers each day:
    - Day 1: 7-2=5
    - Day 2: 5+7-2=10
    - Day 3: 10+7-2=15
    - Day 4: 15+7-2=20
    - Day 5: 20+7-2=25
    - Day 6: 25+7=32
    - So, on Day 6 the snail will reach 32 feet and get out of the well at day, without slipping back that night.
    - ```javascript
function main() {
    var depth = parseInt(readLine(), 10);
    //your code goes here
    var day = 0;
  for(let climb = 0; climb <= depth;) {
      day +=1;
      climb += 7;
      if(climb >= depth) {
          break;
      }
      climb -= 2;
  }
  console.log(day);
}
```
- ## Function Parameters
    - ```javascript
function main() {
    var eventExample = readLine();
    // function call
    setReminder(eventExample)
}
//complete the function
function setReminder(event) {
    console.log("You set a reminder about " +event)
};```
- ```javascript
function main() {
    var goalsTeam1 = parseInt(readLine(), 10);
    var goalsTeam2 = parseInt(readLine(), 10);
    // function call
    finalResult(goalsTeam1, goalsTeam2)
    
}
//complete the function
function finalResult(goalsTeam1, goalsTeam2) {
    if (goalsTeam1 > goalsTeam2){
        console.log("Team 1 won")
    } else if (goalsTeam2 > goalsTeam1) {
        console.log("Team 2 won")
    } else {
        console.log("Draw")
    }
};```
    - ```javascript
function main() {
    var num1 = parseInt(readLine(),10);
    var num2 = parseInt(readLine(),10);
    var num3 = parseInt(readLine(),10);
    
    var average = avg(num1, num2, num3);
    
    
    //assign the average value to the variable average 
    
    
    
    console.log(average)
    
}

//complete the function
function avg(num1, num2, num3){
    return ((num1 + num2 + num3) / 3)
}```
    - ```javascript
function main() {
    var amount = parseFloat(readLine(), 10);
    var rate = parseFloat(readLine(), 10);
    
    console.log(convert(amount, rate));
}

function convert(amount, rate) {
    return amount * rate
}

convert();```
- ## Creating your own objects
    - ```javascript
function main() {
    //take flight number and its status
    var flightNumber = readLine();
    var flightStatus = readLine();
    
    var flight1;
    //assign a flight object to flight1 variable
    var flight1 = new Flight(flightNumber, flightStatus)
    //output
    console.log('The flight ' + flight1.number + ' is ' + flight1.status)
    
}

function Flight(flightNumber, status) {
    //fix the constructor
    this.number = flightNumber;
    this.status = status;
};```
- # Adding Methods
    - A store manager needs a program to set discounts for products.
    - The program should take the product ID, price and discount as input and output the discounted price. However, the??**changePrice??**method, which should calculate the discount, is incomplete. Fix it!
    - ```javascript
// **Sample Input**
// LD1493
// 1700
// 15
// **Sample Output**
// LD1493 price: 1700
// LD1493 new price: 1445


function main() {
    var prodID = readLine();
    var price = parseInt(readLine(),10);
    var discount = parseInt(readLine(),10);
    
    var prod1= new Product(prodID, price);
    console.log(prod1.prodID + " price: " + prod1.price);
    
    prod1.changePrice(discount);
    console.log(prod1.prodID + " new price: " + prod1.price);
}

function Product(prodID, price) {
    this.prodID = prodID;
    this.price = price;

    this.changePrice = function(discount) {
        //your code goes here
    this.price = price - ((discount/100) * price);
    }
}```
        - # Methods
            - Functions stored as object properties
            - ```javascript
// Create an object method:

methodName = function() { code }

// Access and Object Method

objectName.methodName()```
            - You can define the function outside of the constructor function
            - ```javascript
function person(name, age) {
  this.name= name;  
  this.age = age;
  this.yearOfBirth = bornYear;
}
function bornYear() {
  return 2016 - this.age;
}```
                - As you can see, we have assigned the object's??**yearOfBirth??**property to the??**bornYear??**function.
                - The??**this??**keyword is used to access the??__age??__property of the object, which is going to call the method.
- 
- 
- 
