---
layout: post
title: React Learning Notes


categories:
  - Technology
tags:
  - study

---

# React Learning Process Track
## Section 1: Intro 

### What is React? -  "A JavaScript Library for building User Interface" 

Components for building User Interface (Header, Sidebar, Headline, Article Content). 

You can think components like Building Blocks. (Maybe you can see it as a Lego block, and you are building a car using several small lego blocks.) 

### Pros: 
- Maintainable Teamwork
- Manageable Code
- Reusable Code
- Custom HTML elements

Code writing Tool: CodePen

HTML, CSS, Javascript are the fundamental knowledge you need to know when you learn React. 


## Section 2: Refreshing Next Generation of JS


### 1. let & const
var -> let & const

let -> variable values
const -> constant values

### 2. Arrow Function

No more issue with the *this* keyword.

**Example 1:** 

```javascript
  const addNumbers = number => number + 5;
  console.log(addNumbers(5));
```

**Example 2:** 
```javascript
  const printName = name => {
  console.log(name);
}

printName('Migapipo');
```

**Example 3:** 
```javascript
  const printInfo = (name,age) =>{
  console.log(name,age);
}

printInfo('Miga', 25);
```

### 3. Exports & Imports

#### Example 1. person.js

```javascript
const person = {
  name = 'Miga'
}
export default person
```

#### Example 2. utility.js

```javascript
export const clean = () => {...} 
export const baseData = 10;
```

#### Example 3. app.js

```javascript
// Default export
import person from './person.js'
import prs from './person.js'
// imports default and ONLY export of the file 


// Named export
import {clean} from './utility.js'
import {baseData} from './utility.js'
```
**name** is defined by export



### 4. Understanding Classes

#### 4.1 Class
```javascript
class Person{
  name = 'Migapipo'   //Property: variables
  call = () => {...}  //Method: functions 
}
```

#### 4.2 Class Usage (Constructor Functions)

```javascript
const myPerson = new Person()
myPerson.call()
console.log(myPerson.name)
```

#### 4.3 Inheritance

```javascript
class Person extends Master
```


Classes are blueprints for js objects.


```javascript
class Human{
  constructor(){
    this.gender = 'female';
  }
  printGender(){
    console.log(this.gender);
  }
  
}
class Person extends Human{
  constructor(){
    super();
    this.name = 'Miga';
    this.gender ='male';
  }
  
  printMyname(){
    console.log(this.name);
  }
}

const person = new Person();
person.printMyname();
person.printGender();
```


### 5. Classes, Properties & Methods

- **Properties : Variables**

**ES6**
```javascript
constructor(){
  this.myProperty ='value'
  }
```

**ES7**
```javascript
myProperty ='value' 
```
---

- **Methods : Functions**

**ES6**
```javascript
myMethod(){...} 
```

**ES7**

**Arrow Function**
```javascript
myMethod = () => {...} 
```

Let's go back to the example we made in the last part of the course. They look like this right now: 
```javascript
class Human{
  gender = 'female';   // easier to cliam a variable
  
  printGender =() => {
    console.log(this.gender); // still need to keep "this" keyword referring to the variable
  }
  
}
class Person extends Human{
    name = 'Miga';
    gender ='male';
  }
  
  printMyname =() => {
    console.log(this.name);
  }
}


const person = new Person();
person.printMyname();
person.printGender();
```


### 6. Spread & Reset Operators

### Three Dots ... 
#### 1. Spread
Used to split up array elements OR object properties
```
const newArray = [...oldArray, 1, 2]
const newObject = (...oldObject, newProp:5)
```

#### Example-1: 
```javascript
const numbers = [1, 2, 3];
const newNumbers = [...numbers, 4];

console.log(newNumbers);
```
#### Example-1 Output:
```
[1, 2, 3, 4]
```

#### Example-2: 
```javascript
const person = {
  name = 'Miga'
};

const newPerson ={
  ...person,
  age: 25

}

console.log(newPerson);
```
#### Example-2 Output:
```
[object Object] {
  age: 25,
  name: "Miga"
}
```

:question: Question Time: Why the name has appended at the end? 

I tried more Examples to figure this out. 

#### Example-3: 
```javascript
const person = {
  name : 'Miga'
};

const newPerson ={
  person,
  age: 25
}

console.log(newPerson);
```
#### Example-3 Output:
```
[object Object] {
  age: 25,
  person: [object Object] {
    name: "Miga"
  }
}
```



#### Example-4: 
```javascript
const person = {
  name : 'Miga'
};

const newPerson ={
  ...person,
  age: 25,
  height:160
}

console.log(newPerson);
```
#### Example-4 Output:
```
[object Object] {
  age: 25,
  height: 160,
  name: "Miga"
}
```


#### 2. Rest
Used to merge a list of function arguments into an array 

```
function soryArgs(...args){
  return args.sort()
}
```

#### Example: 
 ```javascript
const filter = (...args) => {
  return args.filter(el => el === 1);
}

console.log(filter(1, 2, 3));
```

#### Example Output: 
```
[1]
```

#### Three Equals === 
Check for type and value equality

```
el === 1
```