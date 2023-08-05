## Values & Types

- JavaScript has **typed values**, not typed variables.
- Following built-in types are available:
  - string
  - number
  - boolean
  - null
  - undefined
  - object
  - symbol
  - bigint
- It provides a **typeof** operator that can examine a value and tell you what type it is. The return value from the typeof operator is always one of the above string values. e.g. "string", "number" etc.
- typeof null would result "object". This is a bug present in JS from long ago.

### Object

- The object type refers to a compound value where you can set properties(named locations) that each hold their own values of any type.
- Properties can either be accessed with dot notation (i.e., obj.a) or bracket notation (i.e. obj["a"]).

### Array

- An array is an object that holds values (of any type) not particularly in named properties/keys, but rather in numerically indexed positions.
- typeof an array will result "object".
- Because arrays are special objects (as typeof implies), they can also have properties, including the automatically updated length property.

### Function

- Function is another subtype of object.
- typeof a function returns "function" main type.
- But you can use object properties in limited cases.
  e.g.

  ```javascript
  function foo() {
    return 10;
  }

  foo.bar = "hello world!";

  typeof foo; // function
  typeof foo(); // number
  typeof foo.bar; // string
  ```

---

---

## Comparision

- There are two main types of comparision in JavaScript, _equality_ & _inequality_.
- The result of any comparision is a strictly boolean value(true or false), regardless of what types are compared.

### Coercion

- Coercion means _type conversion_.
- Coercion comes in two types,
  - _explicit_ : The automatic conversion which happens in code from one type to other.
    ```javascript
    var a = "42";
    var b = Number(a);
    a; // "42"
    b; // 42--the number!
    ```
  - _implicit_ : Type conversion happens as a non obvisous side effect of some other operation.
    ```javascript
    var a = "42";
    var b = a * 1; // "42" implicitly coerced to 42 here
    a; // "42"
    b; // 42--the number!
    ```

### Truthy & falsy

- List of **falsy** values in JS are,
  - "" (empty string)
  - 0, -0, NaN (invalid number)
  - false
  - null, undefined
- Any value apart from _falsy_ values above, is **truthy**.
  e.g. - [], {}, " ", true
- It's important that, a non-boolean value only follows this "truthy/falsy" coercion if it's actually coerced to boolean.

### Equality

- There are four equality operators: **==, ===, !== and !===**.
- The ! forms are symmetric "not equal" version of their counter parts. _non-equality_ should not be confused with _inequality_.
- == checks for value equality with coercion allowed and === checks for value equality without allowing coercion. === is often called **strictly equality** for this reason.
- Some simple rules to decide whether to use == or === are:
  - If either value (aka side) in a comparison could be the true or false value, avoid == and use ===.
  - If either value in a comparison could be of these specific values (0, "", or []—empty array), avoid == and use ===.
  - In all other cases, you’re safe to use ==. Not only is it safe, but in many cases it simplifies your code in a way that improves readability.
