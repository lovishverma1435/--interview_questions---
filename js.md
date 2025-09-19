1. Difference between var, let, and const?

Answer:
✔ var: function-scoped hota hai, hoisting ke wajah se code ke top par chala jata hai.
✔ let: block-scoped hota hai, reassign ho sakta hai, lekin redeclare nahi.
✔ const: block-scoped hota hai, value ko reassign nahi kar sakte, lekin object ke properties change ho sakti hain.

2. What is hoisting in JavaScript?

Answer:
✔ JavaScript execution se pehle variable aur function declarations ko memory mein move kar deta hai
✔ var aur function declarations hoisting mein define hote hain
✔ let aur const temporal dead zone mein hote hain jab tak initialize na ho

3. Explain scope chain and closure.

Answer:
✔ Scope chain: current function ke variables ke baad parent functions ke variables accessible hote hain
✔ Closure: function apne outer function ke variables ko yaad rakhta hai chahe outer function execute ho chuka ho

Example:

function outer() {
  let count = 0;
  return function inner() {
    count++;
    return count;
  }
}
const counter = outer();
console.log(counter()); // 1
console.log(counter()); // 2

➤ Functions & Objects
4. What are arrow functions and how are they different from normal functions?

Answer:
✔ Arrow functions shorter syntax deti hain
✔ this value lexical hoti hai, matlab parent context se leti hain
✔ Constructor ke roop mein use nahi kar sakte

5. What is the difference between call, apply, and bind?

Answer:
✔ call: function ko turant execute karta hai aur arguments comma se pass karta hai
✔ apply: arguments array ke roop mein pass karta hai
✔ bind: naye function ko return karta hai jisme this permanently set hota hai

Example:

function greet(age) {
  console.log(this.name + ' is ' + age);
}
const user = { name: 'Ashish' };
greet.call(user, 25);
greet.apply(user, [25]);
const bound = greet.bind(user);
bound(25);

6. What is object destructuring?

Answer:
✔ Object ke andar se properties ko alag-alag variable mein extract karne ka tareeka
Example:

const user = { name: 'Ashish', age: 25 };
const { name, age } = user;
console.log(name, age); // Ashish 25

7. What is the difference between shallow copy and deep copy?

Answer:
✔ Shallow copy sirf top level properties copy karta hai
✔ Deep copy nested objects tak copy karta hai
✔ Object.assign() shallow copy karta hai, structuredClone() deep copy ke liye use kar sakte hain

➤ Async JavaScript – Callbacks, Promises, Async/Await
8. Explain how promises work in JavaScript.

Answer:
✔ Promise ek object hai jo future mein result ya error dega
✔ then() success ke liye, catch() error handle karne ke liye use karte hain
Example:

const promise = new Promise((resolve, reject) => {
  setTimeout(() => resolve('Success'), 1000);
});
promise.then(msg => console.log(msg)).catch(err => console.log(err));

9. What is async/await?

Answer:
✔ Async functions promise return karti hain
✔ Await promise ke result ko synchronous tareeke se handle karta hai
Example:

async function fetchData() {
  const result = await fetch('https://jsonplaceholder.typicode.com/todos/1');
  const data = await result.json();
  console.log(data);
}
fetchData();

10. Difference between synchronous and asynchronous code?

Answer:
✔ Synchronous code line by line execute hota hai, har line poora hone ke baad agla chalega
✔ Asynchronous code parallel tasks execute karta hai, callbacks, promises ya async/await ke through handle hota hai

11. What is event loop in JavaScript?

Answer:
✔ JavaScript single-threaded hai lekin event loop background mein asynchronous tasks handle karta hai
✔ Microtasks (Promises) aur macrotasks (setTimeout) ke through event queue process karta hai

➤ DOM Manipulation & Events
12. How do you attach events in JavaScript?

Answer:
✔ addEventListener() use karte hain
Example:

document.querySelector('button').addEventListener('click', () => {
  console.log('Button clicked');
});

13. What is event delegation?

Answer:
✔ Parent element par event listener lagakar uske children ke events handle karna
✔ Performance improve hoti hai jab bahut saare child elements ho

14. Explain bubbling and capturing phases.

Answer:
✔ Bubbling mein event child se parent tak bubble karta hai
✔ Capturing mein parent se child tak event pass hota hai
✔ addEventListener() mein third parameter true hone par capturing phase active hoti hai

15. How to prevent default behavior in events?

Answer:
✔ event.preventDefault() ka use karte hain
Example:

document.querySelector('a').addEventListener('click', (e) => {
  e.preventDefault();
  console.log('Link click blocked');
});

➤ ES6 Features
16. What are template literals?

Answer:
✔ Backticks (`) ka use karke variables aur expressions easily embed kar sakte hain
Example:

const name = 'Ashish';
console.log(`Hello, ${name}!`);

17. Explain rest and spread operators.

Answer:
✔ Rest operator (...args) function mein unlimited arguments accept karta hai
✔ Spread operator (...array) array ya object ko expand karta hai
Example:

function sum(...nums) {
  return nums.reduce((a, b) => a + b, 0);
}
const arr = [1, 2, 3];
console.log(sum(...arr)); // 6

18. What are modules in JavaScript?

Answer:
✔ Code ko alag files mein organize karne ka tareeka
✔ export aur import se reuse kar sakte hain
Example:

// math.js  
export function add(a, b) { return a + b; }

// app.js  
import { add } from './math.js';
console.log(add(2, 3));

➤ Error Handling
19. How do you handle errors in JavaScript?

Answer:
✔ try...catch block ka use karte hain
Example:

try {
  JSON.parse('invalid');
} catch (error) {
  console.log('Error occurred:', error.message);
}

20. What is the difference between throw and return?

Answer:
✔ throw exception ko generate karta hai aur code execution stop karta hai
✔ return function ko result deta hai aur execution wapas lauta deta hai

21. Explain execution context aur call stack kaise kaam karta hai?

Answer:
✔ Jab bhi function call hota hai, uske liye ek execution context banta hai
✔ Global execution context sabse pehle banta hai
✔ Call stack mein function push aur pop hota hai jab tak wo complete nahi ho jata
✔ Scope aur variable lookup isi context mein hota hai

22. Closure kaise kaam karta hai aur iska use case kya hai?

Answer:
✔ Closure tab banta hai jab inner function outer function ke variables ko yaad rakhta hai, chahe outer function finish ho gaya ho
✔ Use case: private variables, callbacks, event handlers, memoization

Example:

function makeCounter() {
  let count = 0;
  return function() {
    count++;
    return count;
  }
}
const counter = makeCounter();
console.log(counter()); // 1
console.log(counter()); // 2

23. Explain how “this” keyword ka behavior change karta hai?

Answer:
✔ Normal function mein this global ya undefined hota hai strict mode mein
✔ Object method mein this object ko point karta hai
✔ Arrow function mein this lexical hota hai – parent context se leta hai

➤ Objects, Prototypes, Inheritance
24. Explain prototype chain and inheritance in JavaScript.

Answer:
✔ Har object ka ek hidden property __proto__ hota hai jo parent object ko reference karta hai
✔ Agar property object mein nahi milti to prototype chain follow karke dhoondhta hai
✔ Inheritance mein child object parent ke methods aur properties inherit karta hai

25. What is the difference between Object.create() and class-based inheritance?

Answer:
✔ Object.create() se seedha prototype assign karke inheritance create kar sakte hain
✔ Class syntax ES6 mein abstraction deta hai lekin andar se wahi prototype chain use hoti hai

26. Explain shallow vs deep cloning of objects with examples.

Answer:
✔ Shallow clone sirf top level copy karta hai, nested objects reference copy hote hain
✔ Deep clone pura structure copy karta hai, nested objects bhi alag hote hain
Example:

let obj = { a: 1, b: { c: 2 } };
let shallow = Object.assign({}, obj);
let deep = JSON.parse(JSON.stringify(obj));

➤ Asynchronous Programming
27. Explain event loop, call stack, task queue aur microtask queue ka difference.

Answer:
✔ Call stack mein functions execute hote hain
✔ Task queue mein setTimeout ya setInterval wale tasks wait karte hain
✔ Microtask queue mein promises ke callbacks high priority mein execute hote hain
✔ Event loop in queues ko check karta hai aur stack empty hote hi process karta hai

28. Why setTimeout(fn, 0) still delays execution?

Answer:
✔ Even 0ms delay tasks next event loop cycle mein queue hote hain
✔ Call stack clear hone ke baad hi setTimeout execute hota hai

29. What is promise chaining and how error handling works in it?

Answer:
✔ Multiple then() ko chain karke sequential operations kar sakte hain
✔ Agar chain mein koi error aaye to last catch() usko handle karega

Example:

Promise.resolve(5)
  .then(x => x * 2)
  .then(x => { throw new Error("Oops"); })
  .catch(err => console.log(err.message)); // Oops

30. Explain async/await error handling.

Answer:
✔ Async functions ke andar errors ko try...catch block mein handle karte hain
✔ Await kisi rejected promise ko bhi throw karta hai

Example:

async function fetchData() {
  try {
    const res = await fetch('invalid-url');
  } catch (err) {
    console.log('Error:', err.message);
  }
}
fetchData();

➤ Memory Management
31. What causes memory leaks in JavaScript?

Answer:
✔ Unused references, closures holding memory, circular references, event listeners jo remove nahi kiye
✔ Global objects mein data store karke garbage collection se bach sakta hai

32. How can you prevent memory leaks?

Answer:
✔ Variables ko null ya undefined kar do jab use na ho
✔ Event listeners remove karo
✔ Closures ka careful use karo
✔ Large data structures ko clean karo

➤ ES6+ Features
33. Explain destructuring with default values.

Answer:
✔ Agar object mein property nahi milti to default value assign karte hain
Example:

const { name = 'Guest', age = 30 } = {};
console.log(name, age); // Guest 30

34. What is the difference between == and ===?

Answer:
✔ == loosely compare karta hai aur type conversion karta hai
✔ === strictly compare karta hai bina type conversion ke

35. Explain optional chaining and how it prevents errors.

Answer:
✔ Agar kisi nested property ka value undefined hai to error nahi aayega
✔ Syntax: obj?.prop?.subprop

Example:

const user = null;
console.log(user?.name); // undefined

➤ Performance & Debugging
36. How to debug JavaScript code efficiently?

Answer:
✔ Browser dev tools ka use karo
✔ Breakpoints set karo
✔ Console logs use karo
✔ Performance tab se analyze karo
✔ Memory snapshot leke leaks detect karo

37. What is throttling and debouncing in JavaScript?

Answer:
✔ Throttling event ko fixed time interval mein limit karta hai
✔ Debouncing event ko tab tak delay karta hai jab tak user ruk na jaye

Example:
✔ Scroll ya resize event mein performance improve karne ke liye use hota hai

➤ Best Practices
38. Why should you avoid polluting the global scope?

Answer:
✔ Variable collisions aur bugs ka risk badhta hai
✔ Modular aur maintainable code likhna mushkil hota hai
✔ Namespace pattern ya modules use karne se problem solve hoti hai

39. Explain immutability and why it's important?

Answer:
✔ Data ko directly modify na karke naye object return karo
✔ Predictable aur bug-free code likhne mein help karta hai
✔ Redux jaise state management mein kaafi useful

40. How do you ensure clean code in JavaScript projects?

Answer:
✔ Functions ko small aur reusable rakho
✔ Comments aur documentation likho
✔ Consistent naming aur formatting follow karo
✔ Errors ko proper handle karo
✔ Test cases likho

41. What is the module pattern and why is it useful?

Answer:
✔ Code ko encapsulate karne aur private state maintain karne ka tareeka
✔ Global scope ko pollute hone se bachata hai
✔ Example:

const Counter = (function() {
  let count = 0;
  return {
    increment() { count++; },
    getCount() { return count; }
  };
})();
Counter.increment();
console.log(Counter.getCount()); // 1

42. Explain IIFE (Immediately Invoked Function Expression).

Answer:
✔ Function ko declare karte hi execute kar diya jata hai
✔ Private variables aur initialization ke liye use hota hai
Example:

(function() {
  console.log('This runs immediately!');
})();

43. What is currying in JavaScript?

Answer:
✔ Ek function ko multiple arguments ke bajay ek-ek argument le kar chhote functions mein todna
✔ Functional programming mein kaafi use hota hai
Example:

function multiply(a) {
  return function(b) {
    return a * b;
  }
}
const double = multiply(2);
console.log(double(5)); // 10

44. What is function composition?

Answer:
✔ Do ya usse zyada functions ko chain karke ek naya function banana
✔ Output of one function next ka input hota hai
Example:

const add = x => x + 2;
const multiply = x => x * 3;
const composed = x => multiply(add(x));
console.log(composed(2)); // 12

➤ Error Handling & Debugging
45. What are common types of errors in JavaScript?

Answer:
✔ Syntax Error – galat likhne par hota hai
✔ Reference Error – undefined variable use karne par hota hai
✔ Type Error – wrong type ke operation par hota hai
✔ Range Error – invalid range jaise recursion limit cross karne par hota hai

46. How do you create custom errors in JavaScript?

Answer:
✔ Error class inherit karke apna error define kar sakte hain
Example:

class ValidationError extends Error {
  constructor(message) {
    super(message);
    this.name = 'ValidationError';
  }
}
throw new ValidationError('Invalid data!');

47. Explain how stack trace helps in debugging.

Answer:
✔ Error hone par browser call stack dikhata hai
✔ Function ke execution path ko trace karne mein madad karta hai
✔ Source code mein exact line dhoondhne mein help karta hai

➤ Browser APIs & Events
48. What is event bubbling and how can you stop it?

Answer:
✔ Event parent elements tak propagate hota hai
✔ event.stopPropagation() se bubbling ko rok sakte hain
Example:

document.querySelector('div').addEventListener('click', e => {
  e.stopPropagation();
  console.log('Div clicked but not bubbled!');
});

49. How does the Intersection Observer API work?

Answer:
✔ Element ka viewport mein dikhna detect karta hai
✔ Scroll-based animations ya lazy loading ke liye use hota hai
Example:

const observer = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if(entry.isIntersecting) {
      console.log('Element visible!');
    }
  });
});
observer.observe(document.querySelector('#myElement'));

50. What is the difference between localStorage, sessionStorage, and cookies?

Answer:
✔ localStorage: data browser mein permanent store hota hai
✔ sessionStorage: tab close hone tak store hota hai
✔ cookies: small data store hota hai, server ko bhi bheja jata hai aur expiration set hota hai

➤ Performance Optimization
51. What is debouncing and how is it implemented?

Answer:
✔ Frequent events ko limit karne ke liye use hota hai
✔ User rukne ke baad hi function execute hota hai
Example:

function debounce(fn, delay) {
  let timeout;
  return function(...args) {
    clearTimeout(timeout);
    timeout = setTimeout(() => fn.apply(this, args), delay);
  };
}

52. What is throttling and where is it useful?

Answer:
✔ Frequent events ko fixed time mein limit karta hai
✔ Scroll ya resize events mein performance improve karta hai
Example:

function throttle(fn, limit) {
  let inThrottle;
  return function(...args) {
    if (!inThrottle) {
      fn.apply(this, args);
      inThrottle = true;
      setTimeout(() => inThrottle = false, limit);
    }
  };
}

53. How to optimize DOM manipulation?

Answer:
✔ Document fragments ka use karo
✔ Batch updates karo
✔ Layout thrashing avoid karo
✔ Minimal reflows karne ki koshish karo

➤ Memory Leaks & Debugging
54. What is garbage collection in JavaScript?

Answer:
✔ Memory cleanup process hai jo unused variables aur objects ko remove karta hai
✔ Circular references aur closures ke wajah se leaks ho sakte hain

55. How can you detect memory leaks?

Answer:
✔ Chrome DevTools mein memory snapshot lekar objects ko track karo
✔ Event listeners remove karo
✔ Global objects mein data store avoid karo

➤ Security
56. What is Cross-Site Scripting (XSS) and how to prevent it?

Answer:
✔ Malicious scripts inject karne ka attack hai
✔ Input sanitize karo, trusted data hi render karo, content security policy lagao

17. How does CSP (Content Security Policy) help secure JavaScript?

Answer:
✔ Browser ko batata hai kaunsa script allowed hai
✔ Inline scripts ko block karta hai
✔ External domains par restriction lagata hai

➤ Design Patterns
58. Explain observer pattern in JavaScript.

Answer:
✔ Ek object dusre object ko notify karta hai jab state change hoti hai
✔ Event-driven programming mein kaafi use hota hai

59. What is factory function and how is it different from class?

Answer:
✔ Factory function plain function hoti hai jo object return karti hai
✔ Class structured hoti hai aur new keyword se use hoti hai
✔ Dono reusable objects create karne ke liye use hote hain

60. What is singleton pattern and when should you use it?

Answer:
✔ Ek hi instance create karne ka pattern hai
✔ Configuration ya state sharing ke liye useful hai
Example:

const Singleton = (function() {
  let instance;
  function create() {
    return { name: 'singleton' };
  }
  return {
    getInstance() {
      if (!instance) instance = create();
      return instance;
    }
  };
})();

61. Explain how microtasks and macrotasks differ and their priority.

Answer:
✔ Microtasks (Promises, queueMicrotask) event loop mein macrotasks se pehle process hote hain
✔ SetTimeout, setInterval jaise macrotasks baad mein run hote hain
✔ Isse ensure hota hai ki promises turant execute honge jab call stack empty ho

62. What are service workers and how do they relate to JavaScript?

Answer:
✔ Background script hai jo browser mein run hoti hai
✔ Offline caching, push notifications aur background sync handle karti hai
✔ Network requests intercept karne aur control karne mein help karti hai

63. What is the difference between structured clone and JSON methods for copying objects?

Answer:
✔ structuredClone() deeply clone karta hai aur functions, Dates, Maps, Sets jaise objects ko bhi copy karta hai
✔ JSON.parse(JSON.stringify(obj)) sirf plain objects aur arrays ke liye kaam karta hai aur unsupported types ko ignore karta hai

64. Explain how async iterators work.

Answer:
✔ Data stream handle karne ke liye use hote hain
✔ for await...of loop se asynchronous data consume kar sakte hain
Example:

async function* generator() {
  yield "First";
  yield "Second";
}
(async () => {
  for await (const val of generator()) {
    console.log(val);
  }
})();

65. What is requestAnimationFrame and how is it different from setTimeout?

Answer:
✔ requestAnimationFrame browser ke paint cycle ke saath sync hota hai
✔ Smooth animations deta hai, CPU aur battery dono save karta hai
✔ setTimeout mein fixed delay hota hai jo frame drop kar sakta hai

➤ Memory, Debugging & Optimization
66. Explain weak references and WeakMap/WeakSet.

Answer:
✔ WeakMap aur WeakSet mein keys weakly referenced hoti hain
✔ Garbage collector unko memory free karne mein consider karta hai
✔ Memory leaks avoid karne mein help karta hai

67. How do you prevent layout thrashing?

Answer:
✔ DOM reads aur writes ko batch karo
✔ Multiple reads ke beech mein writes avoid karo
✔ CSS animations ya transforms ka use karo jo reflow nahi karte

68. What are memory leaks caused by event listeners?

Answer:
✔ Event listeners jo remove nahi kiye gaye aur objects ko reference mein rakhte hain
✔ Garbage collection fail ho jata hai aur memory consume hoti rehti hai

➤ Functional Programming in JavaScript
69. What is immutability and how can you implement it in JavaScript?

Answer:
✔ Objects ko directly change nahi karte, naye object return karte hain
✔ Spread operator, Object.assign ya libraries jaise Immer use karte hain
Example:

const user = { name: "Ashish", age: 25 };
const updated = { ...user, age: 26 };

70. Explain higher-order functions with examples.

Answer:
✔ Aise functions jo doosre functions ko accept ya return karte hain
✔ Reusability aur composition mein help karta hai
Example:

function withLogging(fn) {
  return function(...args) {
    console.log('Calling function with', args);
    return fn(...args);
  };
}
const add = (a, b) => a + b;
const loggedAdd = withLogging(add);
loggedAdd(2, 3);

71. What is a pure function?

Answer:
✔ Input ke alawa kuch use nahi karta
✔ Same input pe same output deta hai
✔ Side effects nahi hota
Example:

function add(a, b) {
  return a + b;
}

➤ Security
72. How can you prevent XSS attacks in JavaScript applications?

Answer:
✔ User input sanitize karo
✔ InnerHTML avoid karo, instead textContent use karo
✔ Trusted templates ya libraries use karo
✔ CSP headers implement karo

73. What is CORS and why is it needed?

Answer:
✔ Cross-Origin Resource Sharing ek mechanism hai jo batata hai ki kis domain se request allowed hai
✔ APIs ko secure banata hai aur browser mein restrictions enforce karta hai

➤ State Management & Architecture
74. How do you manage state in a complex JavaScript app?

Answer:
✔ Local state – component level
✔ Global state – context API ya Redux
✔ Server state – React Query, SWR
✔ State ko immutability aur pure functions ke saath maintain karo

75. What is observable pattern and how can it be implemented?

Answer:
✔ State change par subscribers ko notify karta hai
✔ Data streams handle karne mein helpful
Example:

class Observable {
  constructor() {
    this.subscribers = [];
  }
  subscribe(fn) {
    this.subscribers.push(fn);
  }
  notify(data) {
    this.subscribers.forEach(fn => fn(data));
  }
}
const obs = new Observable();
obs.subscribe(data => console.log('Got', data));
obs.notify('Hello');

➤ Debugging & Testing
76. How do you debug async issues in JavaScript?

Answer:
✔ Async/await use karke readability badhao
✔ Promises ko catch karo aur error handle karo
✔ Browser DevTools mein breakpoints lagao
✔ Network requests ko monitor karo

77. Explain how jest, mocha, or other testing frameworks help in JavaScript development?

Answer:
✔ Automated tests likhne mein madad karte hain
✔ Edge cases aur bugs ko catch karte hain
✔ Code reliability aur refactoring mein confidence dete hain

➤ Patterns & Best Practices
78. What is the observer vs pub-sub pattern difference?

Answer:
✔ Observer mein direct relationship hota hai subject aur observer ke beech
✔ Pub-sub mein loosely coupled events hote hain, message broker ke through communicate karte hain

79. What is the difference between synchronous and asynchronous iterables?

Answer:
✔ Synchronous iterable ek baar mein sab data deta hai
✔ Asynchronous iterable promises ke through data stream handle karta hai

80. How do you structure a scalable JavaScript application?

Answer:
✔ Modular components
✔ Separation of concerns
✔ Clean folder structure
✔ State management best practices
✔ Linter aur formatter use karo
✔ Testing aur CI/CD pipelines integrate karo

➤ Advanced Functions & Closures
81. What is memoization in JavaScript?

Answer:
✔ Function ka result cache karke future calls fast bana dena
✔ Especially recursive functions ke liye useful
Example:

function memoize(fn) {
  const cache = {};
  return function(...args) {
    const key = args.toString();
    if (cache[key]) return cache[key];
    const result = fn(...args);
    cache[key] = result;
    return result;
  }
}
const factorial = memoize(n => (n <= 1 ? 1 : n * factorial(n - 1)));
console.log(factorial(5)); // 120

82. What are pure functions and why are they important?

Answer:
✔ Same input, same output
✔ No side effects
✔ Testing aur predictability easy hoti hai
Example:

function add(a, b) { return a + b; }

83. Explain function currying and partial application.

Answer:
✔ Currying: Function ko ek argument pe ek argument receive karne wale chhote functions me convert karna
✔ Partial: Function ke kuch arguments fix kar dena
Example:

const multiply = a => b => a * b;
const double = multiply(2);
console.log(double(5)); // 10

84. What is IIFE and why use it?

Answer:
✔ Immediately invoked function expression
✔ Private scope create karta hai
✔ Initialization ke liye use hota hai
Example:

(function() { console.log('IIFE executed'); })();

85. Difference between call, apply, bind?

Answer:
✔ call – immediately execute, comma separated arguments
✔ apply – immediately execute, array of arguments
✔ bind – function copy return karta hai with this bound
Example:

function greet(age) { console.log(this.name + ' is ' + age); }
const user = { name: 'Ashish' };
greet.call(user, 25);
greet.apply(user, [25]);
const bound = greet.bind(user);
bound(25);

➤ Prototypes & Classes
86. Explain prototype chain in JavaScript.

Answer:
✔ Objects ka parent-child chain hota hai
✔ Property na mile to prototype chain follow hoti hai
✔ Inheritance achieve hota hai
Example:

const parent = { greet() { console.log('Hello'); } };
const child = Object.create(parent);
child.greet(); // Hello

87. Difference between class and constructor function?

Answer:
✔ Class – ES6 syntax, syntactic sugar over prototypes
✔ Constructor function – ES5, manually prototype set karna padta hai
✔ Behavior almost same hai

88. Shallow copy vs deep copy

Answer:
✔ Shallow – top level properties copy hoti hain, nested reference copy hoti hai
✔ Deep – pura object copy hota hai, nested object alag hota hai
Example:

let obj = { a: 1, b: { c: 2 } };
let shallow = Object.assign({}, obj);
let deep = structuredClone(obj);

➤ Async JavaScript
89. What is event loop?

Answer:
✔ JS single-threaded hota hai
✔ Event loop call stack aur task queues ko manage karta hai
✔ Microtasks (Promises) pehle run hote hain, macrotasks (setTimeout) baad mein

90. Promise chaining & error handling

Answer:
✔ Multiple then chain kar sakte ho
✔ Catch at last handle karta hai errors

Promise.resolve(5)
  .then(x => x * 2)
  .then(x => { throw new Error('Oops'); })
  .catch(err => console.log(err.message)); // Oops

91. Async/await error handling

Answer:
✔ try/catch block ke andar use karte hain

async function fetchData() {
  try { await fetch('invalid-url'); }
  catch(err) { console.log(err.message); }
}
fetchData();

92. setTimeout(fn, 0) ka use aur delay kyun hota hai?

Answer:
✔ 0ms bhi next event loop cycle ke liye queue hota hai
✔ Call stack empty hone ke baad hi execute hota hai

➤ Memory & Performance
93. Memory leaks kaise detect karein?

Answer:
✔ Chrome DevTools Memory tab se snapshot
✔ Event listeners remove karo
✔ Closures aur global references clean karo

94. Throttling vs Debouncing

Answer:
✔ Throttling – fixed interval pe function run kare
✔ Debouncing – last action ke baad function run kare
Example: Scroll/resize event optimization

95. Garbage collection

Answer:
✔ JS automatically unused memory free karta hai
✔ Circular references aur closures memory leak cause kar sakte hain

➤ Browser & APIs
96. localStorage vs sessionStorage vs cookies

Answer:
✔ localStorage – permanent storage
✔ sessionStorage – tab close hone tak
✔ cookies – small, server ko bhi bheja jata hai, expiration set hota hai

97. Intersection Observer API

Answer:
✔ Element ka viewport mein visible hona detect karta hai
✔ Lazy loading, infinite scrolling aur animation ke liye use hota hai

98. requestAnimationFrame vs setTimeout

Answer:
✔ requestAnimationFrame browser ke paint cycle ke saath sync
✔ Smooth animation aur CPU efficiency
✔ setTimeout fixed interval pe run karta hai

➤ Functional Programming
