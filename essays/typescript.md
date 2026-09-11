---
layout: essay
type: essay
title: "TypeScript? You mean JavaScript DLC?"
# All dates must be YYYY-MM-DD format!
date: 2026-09-10
published: true
labels:
  - TypeScript
  - Javascript
  - Software developement
---

<img width="200px" class="rounded float-start pe-4" src="../img/typescript/typescript.png">

## What is TypeScript?

TypeScript, as the name implies, is a stongly typed programming language, which means that the coder has the ability to catogorize the data into different types - such as integers, strings or booleans. This might sound like your sterotypicaly programming language, but typescript is a superset of Javascript, a dynamically typed that has the ability to assign and reassign a varibles into different types. This sounds awesome, right? Since I can assign reassign varibles without casting it unlike other typed programming languages. 

Well, potential issues might arise in JavaScript in this particular example:

```js
function calculateTotal(price, taxRate) {
    return price + (price * taxRate);
}

// You accidentally pass a string from an HTML input field instead of a number
const total = calculateTotal("100", 0.05);

// JavaScript coerces the types. Instead of 105, it returns a string nightmare:
console.log(total); // Outputs: "1005"
```
In this case, JavaScript will still compile this code successfully, but the output of the function will be unexpected. Although this might seem like an easy fix/catch, what if you have a giant Javascript file where the result of the function is not explicitly outputted, and instead is passed through another function and causes more unexpected outputs. Now you have to spend time to debug and pin point the exact line of code that is causing the issue.

Now if you put TypeScript in the same scenerio, where you have the ability to declare a type of the variable before assigning it, it will imediatlly flag it at compile-time, saving you much time.

```ts
function calculateTotal(price: number, taxRate: number): number {
    return price + (price * taxRate);
}

// TypeScript knows price must be a number
// This causes a TypeScript error because "100" is a string
const total = calculateTotal("100", 0.05);

console.log(total);
```

TypeScript flags the incorrect argument:

```text
Argument of type 'string' is not assignable to parameter of type 'number'.
```




## My First Impression
As someone who is actively using JavaScript for work, I think it's a great language for software developement. It's lightweight, fast, and a popular language used across websites. When I first heard aboput TypeScript, it was explained to me like a extension of JavaScript, where types are now declearable for all variables, I wasn't super hyped about it. Since JavaScript works just fine for me, and cases like the one I mentioned in the previous section rarely happens and are easily fixable. Then I started scripting in TypeScript for a software engineering I have to take, and I see the benefit of using TypeScript. 

As mentioned before, TypeScript catches errors during compile-time, as I am typing the code. This means I get to correct my mistake before I spend my time running the script only to find out I have made a mistake somewhere when it returns an error. How great is that?

Now that is about the only thing I found useful in TypeScript really, I do feel lazy sometime and like the way that I don't have to declear a type or parsing a variable when reassigning in JavaScript.

One thing TypeScript did remind me of however, is the Typed programming language I used like Java, C++ and Python to some extend. Since these are the language that I coded the most on before JavaScript, picking up TypeScript is relatively easy, just forget the fact that you must declare your type after the name of your variable.

```ts
let age: number = 20;
let name: string = "Jordan";
const isStudent: boolean = true;
```

Where as in language like Java, you must declare the type before the name:

```java
int age = 20;
String name = "Jordan";
boolean isStudent = true;
```
This feels like I have to relearn how to speak again, as in my mind, where I am used to languages like Java, I say "There's a variable, called age, with the value of 20". Where as now, I have to remember it the TypeScript way and say "Let there be a variable called age, which is number with the vaule of 20". Sounds a lot fancier, doesn't it?


## Athletic Software Enigneering with TypeScript
After a few classes of TypeScript, I feel like it's still hard for me to grasp the unsual syntax of it. During Workout of the Day (WOD) where we have 30 minutes to solve script a solution from a prompt, I spent about a quarter of my time fixing syntaxs, as it mixed and matches with both JavaScript and Java/C++/C in my mind. But with enough practice, I believe TypeScript syntax will burn into my brain like every other languages I've learned.
