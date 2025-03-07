# Introduction to ES6

Welcome to **Introduction to ES6**. After watching this video, you will be able to:
1. Define ECMAScript 6 (ES6).
2. Describe how to use new features that have been added to JavaScript as part of ES6.

---

## What is ECMAScript 6 (ES6)?

**ECMAScript (ES)** is a standard for scripting languages, including JavaScript. The standard is defined by the European Computer Manufacturers Association (ECMA), an organization that creates a wide range of global information and communications technology standards.

### Timeline

- **ES6 (2015)**: Introduced major changes that significantly impacted JavaScript.
- **ES2020**: The most recent version of ECMAScript.
- **ES.Next**: A dynamic name used to refer to the forthcoming version of ECMAScript.

---

## Key Features of ES6

### 1. `let` and `const`

- **`let`**: Allows you to declare variables with block-level scope.
  - **Example**:
    ```javascript
    if (true) {
      let num = 5;
    }
    console.log(num); // Error: num is not defined
    ```

- **`const`**: Allows you to declare constants whose values cannot be changed.
  - **Example**:
    ```javascript
    const num = 5;
    num = 6; // Error: Assignment to constant variable
    ```

### 2. Arrow Functions

Arrow functions provide a shorter and cleaner way to define functions. They can be declared using the `let` and `const` keywords.

- **Syntax**:
  ```javascript
  const sayHello = () => console.log('Hello');
  sayHello(); // Output: Hello
  ```

- **With Parameters**:
  ```javascript
  const add = (a, b) => a + b;
  console.log(add(2, 3)); // Output: 5
  ```

- **With Multiple Lines**:
  ```javascript
  const multiply = (a, b) => {
    const result = a * b;
    return result;
  };
  console.log(multiply(2, 3)); // Output: 6
  ```

### 3. Promises

The promise object represents the eventual completion of an asynchronous operation and its return value.

- **Example**:
  ```javascript
  const myPromise = new Promise((resolve, reject) => {
    const success = true;
    if (success) {
      resolve('Operation was successful');
    } else {
      reject('Operation failed');
    }
  });

  myPromise.then((message) => {
    console.log(message); // Output: Operation was successful
  }).catch((error) => {
    console.log(error);
  });
  ```

### 4. Classes

Object-oriented programming became feasible in JavaScript with the introduction of `class`. Classes are templates for creating objects and are built on prototypes.

- **Syntax**:
  ```javascript
  class Rectangle {
    constructor(height, width) {
      this.height = height;
      this.width = width;
    }

    getArea() {
      return this.height + this.width;
    }
  }

  const myRectangle = new Rectangle(10, 20);
  console.log(myRectangle.getArea()); // Output: 30
  ```

- **Inheritance**:
  ```javascript
  class Square extends Rectangle {
    constructor(side) {
      super(side, side);
    }
  }

  const mySquare = new Square(10);
  console.log(mySquare.getArea()); // Output: 20
  ```

---

## Conclusion

You learned that:
1. ES6 (ECMAScript 6) is a significant update to JavaScript that introduced several new features.
2. Key features of ES6 include `let` and `const` for variable declarations, arrow functions for shorter function syntax, promises for handling asynchronous operations, and classes for object-oriented programming.

These features enhance the capabilities of JavaScript, making it more powerful and easier to work with, especially in complex applications.
