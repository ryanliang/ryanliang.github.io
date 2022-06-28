---
title: "Javascripts Notes1"
date: 2019-06-27T22:39:58-04:00
draft: false
---

# var, let and const

## var
- Scope: Global or function.
- Variables declared by `var` can be redifined or updated.
```js
var bar = "foo1";
var bar = "foo2";
bar = "foo3";
```
- Problems: As in the above example, you don't know if `bar` has been declared somewhere else and it can be a total surprise!
- Hoisting: top of the code and initialized to `undefined`

## let
- Scope: block
- Variables declared by `let` can be updated but not re-declared within its scoped.
```js
let bar = "foo";
bar = "new foo";
```
This won't work
```js
let bar = "foo";
let bar = "new foo"; // error: Identifier 'bar' has already been declared
```
Re-declaration outside of scope will be allowed (WTF?!):
```js
let bar = "foo";
if (someCondition) {
    let bar = "some foo";
}
console.log(bar); // "some foo"
```
- Hoisting: does not initialize variables to `undefined`.  

## Const
- Scope: block
- Can't be re-declared or updated.
- Must be initialized at the time of declaration.
- Objects property can be updated, although the object itself cannot.
```js
const contact1 = {
    emailAddress: "dummy@example.com",
    firstName: "Dummy"
}
contact1.firstName = "John"; // This is ok.
```
- Hoisting: same as `let`.  Hoisted to the top but does not initialize declarations.