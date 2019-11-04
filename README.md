# **WHAT I LEARNED IN  WEEK 8** 
___

## `extinction-event`

Great practice using addEventListener (in looks also!) and querySelectorAll.


```javascript
const newOl = document.querySelectorAll('.app ol li')

function lineThru(event){
event.target.style.textDecoration = 'line-through'
}
function olEventListenerLoop () {
    for (let i=0;i<newOl.length;i++) {
    newOl[i].addEventListener('click',lineThru);
}
}
olEventListenerLoop()

const newUl = document.querySelectorAll('ul li')

function invisible(event){
event.target.style.opacity = '0'
}
function ulEventListenerLoop () {
    for (let i=0;i<newUl.length;i++) {
    newUl[i].addEventListener('click',invisible);
}
}
ulEventListenerLoop()

const shrink = document.querySelectorAll('#row img')

function shrinking(event){
    event.target.style.width = '0'
    }

function shrinkingEventListenerLoop () {
    for (let i=0;i<shrink.length;i++) {
    shrink[i].addEventListener('click',shrinking);
    }
}
shrinkingEventListenerLoop()

const toggleButton = document.querySelector('#toggle')
toggleButton.addEventListener('click',everyTogether)

function everyTogether () {
    for (let i=0;i<newOl.length;i++) {
        newOl[i].style.textDecoration = 'line-through'
    }
    for (let i=0;i<newUl.length;i++) {
        newUl[i].style.opacity = '0'
    }
    for (let i=0;i<shrink.length;i++) {
        shrink[i].style.width = '0'
        }
}
```

## `midterm`

Midterm went well. I plan to redo the midterm in my own time as there are many things i'd like to improve on. 

```javascript
function isEvenlyDivisible(a,b) {
  return a % b === 0
}

function halfSquare(a) {
  return a**2/2
}

function isLong(str) {
  return str.length>14
}

function exclaim(str) {
  let newStr = ''
  for (let i=str.length-1;i>-1;i--) {
    if (str[i] !== '!') {
      newStr = newStr + str.slice(0,i+1) + '!'
      break;
    }
  }
  return newStr 
}


function countWords(str) {
  let count = 0
  for (let i=0;i<str.length;i++) {
    if (str[i]===' ') {
      count++
    }
  }
  return count + 1
}

function containsDigit(str) {
  for (let i=0;i<str.length;i++) {
    if ('0123456789'.includes[str[i]]) {
      return true
    }
  }
    return false
}

function containsLowerCase(str) {
  for (let i=0;i<str.length;i++) {
    if ('abcdefghijklmnopqrstuvwxyz'.includes[str[i]]) {
      return true
    }
  }
    return false
}

function containsUpperCase(str) {
  for (let i=0;i<str.length;i++) {
    if ('ABCDEFGHIJKLMNOPQRSTUVWXYZ'.includes[str[i]]) {
      return true
    }
  }
    return false
}

function containsNonAlphanumeric(str) {
  for (let i=0;i<str.length;i++) {
    if ('abcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*()'.includes[str[i]]) {
      return true
    }
  }
    return false
}

function containsSpace(str) {
  for (let i=0;i<str.length;i++) {
    if (str[i] === ' ') {
      return true
    }
  }
  return false
}

function digits(str) {
  let newArr = []
  if (str >= 0) {
    let component = str[i]
    for (let i=0;i<component.length;i++) {
    newArr.push(component[i])
    }
  // } else {
  //   newArr.push(Number(`${num}` * -1))
  }
  return newArr
}

function truncate(str) {
  let newStr= ''
  if (str.length>14) {
    newStr = newStr + str.slice(0,8) + '...'
  } else {
    newStr = newStr + str
  }
return newStr 
}
function isValidPassword(str) {
  for (let i=0;i<str.length;i++) {
    let upperCase = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
    let lowerCase = 'abcdefghijklmnopqrstuvwxyz'
    let digits = '0123456789'
    let space = ' '
    if (upperCase.includes(str[i]) && lowerCase.includes(str[i]) && digits.includes(str[i]) &&  space.includes(str[i])) {
      return true 
    }
      if (upperCase.includes(str[i]) || lowerCase.includes(str[i]) || digits.includes(str[i])) {
        return false 
      }
  }
    return true  
  }

function onlyPunchy(arr) {
  let newArr = []
  for (let i=0;i<arr.length;i++) {
    let component = arr[i]
    let newStr = ''
    if (component.length<15 && component.length-1 !== ' ') {
      newArr.push(newStr + arr[i] + '!')
    } else if (component.length<15) {
      newArr.push(newStr + arr[i])
      }
      }
      return newArr
      
    }
```
## `uptown-func`

In this exercise we called functions within other functions. 

```javascript
function call(func) {
  func();
}

function callTwice(func) {
  func();
  func();
}

function callXTimes(func,n) {
  for (let i=0;i<n;i++) {
    func()
  }
}

function returnFromFunc(func) {
  return func()
}

function modifyString(str,func) {
  return func(str)
}

function modifyNumber(num,func) {
  return func(num)
}

function modifyAnything(something,func) {
  return func(something)

}

function twoFuncs(func1,func2) {
  return func2(func1())
}

function twoValues(val1,val2,func) {
  return func(val1,val2)
}

function twoValuesRTL(val1,val2,func) {
  return func(val2,val1)
}

```
## `Domosaur`

This activity helped us get our head around adding event listeners and some more practice with query selectors.

```javascript
document.querySelector('.mess-with-me').style.fontSize = '3em'
document.querySelector('.mess-with-me').style.backgroundColor = 'lightgreen'
document.querySelector('img').style.width = '324px'
document.querySelector('#hide-me-area').style.display = 'none'
function redBorder(event){
   event.target.style.border = '5px solid red'
}
document.querySelector('img').addEventListener('click', redBorder)
function halfOpacity(event){
    event.target.style.opacity = '0.5'
}
document.querySelector('#feathers').addEventListener('click', halfOpacity)
function padRight(event){
    event.target.style.paddingRight = '100px';
}
document.querySelector('#rattle').addEventListener('click', padRight)
function something(){
    document.querySelector('#row').style.backgroundColor = 'orange'
}
function something2 () {
    document.querySelector('#row').style.backgroundColor = 'white'
}
function clicky(){
    if (document.querySelector('#row').style.backgroundColor !== 'white'){
    something2()
    } else {
    something()
    }
}
document.querySelector('#toggle').addEventListener('click', clicky)

function makesBig (event) {
    event.target.style.width = '200px'

}

function returnsToNormal (event) {
    event.target.style.width = '162px'
}

document.querySelector('#biggify').addEventListener('mouseover', makesBig)
document.querySelector('#biggify').addEventListener('mouseout', returnsToNormal)

```
## `Funculate`

The aim of this activity was to get the perform calculation function to take previous functions.

```javascript
function calculate(operation, firstNum, secondNum) {
  const num1 = Number(firstNum);
  const num2 = Number(secondNum);
  
  const isAddition = operation === '+'
    || operation === 'plus';
  
  const isSubtraction = operation === '-'
    || operation === 'minus';
    
  const isMultiplication = operation === '*'
    || operation.toLowerCase() === 'x'
    || operation === 'times';
    
  const isDivision = operation === '/';
    
  const isModulus = operation === '%'
    || operation === 'mod'
    || operation === 'modulus';
  
  if (isAddition) {
    return performCalculation(add,num1,num2);
  } else if (isSubtraction) {
    return performCalculation(subtract,num1,num2);
  } else if (isMultiplication) {
    return performCalculation(multiply,num1,num2);
  } else if (isDivision) {
    return performCalculation(divide,num1,num2);
  } else if (isModulus) {
    return performCalculation(modulus,num1,num2);
  } else {
    return `Sorry, that's not a mathematical operation!`
  }
}

function add(num1,num2) {
  return num1 + num2
}

function subtract(num1,num2) {
  return num1 - num2
}

function multiply(num1,num2) {
  return num1*num2
}

function divide(num1,num2) {
  return num1/num2
}

function modulus(num1,num2) {
  return num1 % num2 
}

function performCalculation(func,value1,value2) {
  return func(value1,value2)
  }
```

## `Promtulate`

Practice setting up a prompt window that takes in user input and puts it in a function.

```javascript
const result = window.prompt('Please, type in some numbers!')
const arrNum = result.split(' ')
operation = result[0]  
num1 = Number(arrNum[1])
num2 = Number(arrNum[2])
// Array Deconstruction
// const [operation, num1, num2] = result
const resolution = calculate(operation, num1, num2);
 
console.log(resolution)
const printAnswer = document.querySelector('#result');
printAnswer.innerText = resolution

//document.querySelector('#result').innerText = calculate(operation, num1, num2)
```

## `Iffy-2`

This task followed from our previous work on building an app and led nicely from Promtulate. We worked towards making a prompt window for our app.

```javascript
// if (userInput2 === 'kg') {
//     toPounds(userInput1);
// } else if (userInput2==='lbs') {
//     toKg(userInput1);
// }
// } else {
//     console.log('check your units please');
// }


function weightConverter(weight, unit) {
    if (unit==='kg' || unit==='kgs' || unit==='kilograms') {
      return weight * 2.20462 + 'lbs'
    } else if (unit==='lbs' || unit==='pounds'){
      return weight * 0.453592 + 'kgs'
    } else {
      return "check your units please"
    }
  }

//   advice(100) -> 'You\'re doing great!'

// '100 kg' -> 'You weigh 180 pounds. You\'re doing great!'
// '180 pounds' -> 'You weigh 100 kgs. You\'re doing great!'

function advice(weight, unit) {

    // Check kg before or after conversion.
    if ((weight>=100 && (unit === 'kg' || unit === 'kgs' || unit === 'kilograms')) || (weight>=220 && (unit === 'lbs' || unit === 'pounds'))) {
        return "Cut down calories and get yourself to the gym son"
    } else if ((weight>=90 && (unit === 'kg' || unit === 'kgs' || unit === 'kilograms')) || (weight>=198 && (unit === 'lbs' || unit === 'pounds'))) {
        return "Eat the right foods and work out a little every week"
    } else if ((weight>=80 && (unit === 'kg' || unit === 'kgs' || unit === 'kilograms')) || (weight>=176 && (unit === 'lbs' || unit === 'pounds'))) {
        return "You're doing alright don't worry about it. You could potentially up your activity level"
    } else if ((weight>=70 && (unit === 'kg' || unit === 'kgs' || unit === 'kilograms')) || (weight>=154 && (unit === 'lbs' || unit === 'pounds'))) {
        return "You're perfect"
    } else if ((weight>=60 && (unit === 'kg' || unit === 'kgs' || unit === 'kilograms')) || (weight>=132 && (unit === 'lbs' || unit === 'pounds'))) {
        return "Eat a little more"
    } else {
        return "Up the calories and maintain a healthy diet"
    }
}

// advice(userInput1);

// console.log(advice(userInput1));

let weightInputs = window.prompt('Please, type in your weight and units')
// const arrNum = result.split(' ')
// operation = result[0]  
// num1 = Number(arrNum[1])
// num2 = Number(arrNum[2])
// // Array Deconstruction
// // const [operation, num1, num2] = result
// const resolution = calculate(operation, num1, num2);

// console.log(resolution)
let arrNum = weightInputs.split(' ')
const weight = arrNum[0]
const unit = arrNum[1]
// const space = arrNum[1]
// const [num1,num2] = result
const result = weightConverter(weight, unit) + '.' + ' ' + advice(weight, unit) + '!'

const printAnswer = document.querySelector('#result');
printAnswer.innerText = result

//document.querySelector('#result').innerText = calculate(operation, num1, num2)
```