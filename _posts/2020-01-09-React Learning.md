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
Started to learning React today. 

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

> const addNumbers = number => number + 5;
> console.log(addNumbers(5));

**Example 2:** 

> const printName = name => {
>  console.log(name);
>}

> printName('Migapipo');

**Example 3:** 

> const printInfo = (name,age) =>{
  console.log(name,age);
}

> printInfo('Miga', 25);

### 3. Exports & Imports

1. person.js
```javascript
const person = {
  name = 'Miga'
}
export default person
```

2. utility.js

```javascript
export const clean = () => {...} 
export const baseData = 10;
```

3. app.js


```javascript
// Default export
import person from './person.js'
import prs from './person.js'
// imports default and ONLY export of the file 


// Named export
import {clean} from './utility.js'
import {baseData} from './utility.js'

```

*name* is defined by export



### 4. Class

#### *Class* 
```javascript
class Person{
  name = 'Migapipo'   //Property: variables
  call = () => {...}  //Method: functions 
}


```

#### *Class Usage* (Constructor Functions)

```javascript
const myPerson = new Person()
myPerson.call()
console.log(myPerson.name)

```

#### *Inheritance*

```javascript
class Person extends Master
```