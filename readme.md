1. What are the basic data types in TypeScript?
TypeScript builds on JavaScript's basic types and introduces static typing. Here are the basic data types:

number: Represents all numbers (integer or floating-point).
let age: number = 25;

string: Represents text.
let name: string = "John";

boolean: Represents true or false values.
let isActive: boolean = true;

any: Can hold any type (opt-out of type checking).
let value: any = "Could be anything";

unknown: Similar to any but type-safe (requires type checking before use).
let data: unknown = "Maybe anything";

void: Represents the absence of any value (used for functions that don't return anything).
function logMessage(): void {
  console.log("This function returns nothing");
}

null and undefined: Represent absence or uninitialized values.
let empty: null = null;
let uninitialized: undefined = undefined;

array: Represents a collection of values.
let numbers: number[] = [1, 2, 3];

tuple: Represents a fixed-size array with known types.
let person: [string, number] = ["Alice", 30];

enum: Used to define a set of named constants.
enum Colors {
    Red,
    Green,
    Blue,
}
let color: Colors = Colors.Green;

object: Represents non-primitive types.
let obj: object = { key: "value" };




2. What is Generic Data Type?
Generics allow you to define reusable components that work with various data types while maintaining type safety. Instead of specifying a specific type, you use a placeholder.
function identity<T>(value: T): T {
    return value;
}
let numberValue = identity<number>(42); // Type: number
let stringValue = identity<string>("Hello"); // Type: string
Here, T is a type variable that gets replaced with a specific type during usage.

3. What is Type Inferring in TypeScript?
Type inference means that TypeScript automatically determines the type of a variable based on its value, without explicitly specifying it.
let age = 25; // TypeScript infers `age` to be of type `number`

4. What are the possible ways to define typing for functions?
TypeScript allows typing in multiple ways for functions:

Function Parameter and Return Type:
function add(a: number, b: number): number {
    return a + b;
}

Anonymous Function Typing:
const multiply = function(a: number, b: number): number {
    return a * b;
};

Arrow Function Typing:
const divide = (a: number, b: number): number => a / b;


Program -
Define the types in typescript for the given following JavaScript code.
Todo:
- Define type/interface for a single Todo object.
- Define type for each function.
- Do not use any (TS Data Type) type of typescript.
Code: 
var todos = [];
function add(name, description) {
 return todos.push({
 name: name,
 description: description,
 done: false
 });
}
function remove(index) {
 return todos.splice(index, 1);
}
function list() {
 todos.forEach(function(todo, index) {
 console.log(index + " - " + todo.name);
 });
}
function update(index, name, description) {
 todos[index].name = name;
 todos[index].description = description;
 return todos[index];
}


Ans

// Define the Todo interface
interface Todo {
  name: string;
  description: string;
  done: boolean;
}

// Define the todos array type
let todos: Todo[] = [];

// Function to add a new todo
function add(name: string, description: string): number {
  return todos.push({
    name: name,
    description: description,
    done: false,
  });
}

// Function to remove a todo by index
function remove(index: number): Todo[] {
  return todos.splice(index, 1);
}

// Function to list all todos
function list(): void {
  todos.forEach(function (todo: Todo, index: number) {
    console.log(`${index} - ${todo.name}`);
  });
}

// Function to update a todo by index
function update(index: number, name: string, description: string): Todo {
  todos[index].name = name;
  todos[index].description = description;
  return todos[index];
}
