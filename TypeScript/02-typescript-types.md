# TypeScript Types 📝

Welcome to the TypeScript Types section in my learning repository!

## Assertions in TypeScript ✅

TypeScript allows you to assert types in many ways to provide more specific type information. Here are some common type assertions:

- **`as const`**: This assertion tells TypeScript that a variable should be treated as a readonly value. It's often used with literals to create exact types.

  ```typescript
  const colors = ["red", "green", "blue"] as const;
  // `colors` is now of type ["red", "green", "blue"]
  ```

- **`as [type]` as `any`**: This assertion allows you to temporarily treat a value as `any`, bypassing type checks. Be cautious when using it, as it weakens TypeScript's type safety.

  ```typescript
  const value: number = "Hello" as any;
  // No type error, but it can lead to runtime issues
  ```

- **Non-Null Assertion**: When you're certain that a value won't be `null` or `undefined`, you can use the non-null assertion operator (`!`) to tell TypeScript that a variable is defined.

  ```typescript
  const element = document.getElementById("myElement")!;
  // `element` is guaranteed to be non-null
  ```

## TypeScript Primitive Types 🧱

TypeScript supports several primitive data types:

- **boolean**: Represents `true` or `false` values.

  ```typescript
  let isActive: boolean = true;
  ```

- **number**: Represents numeric values, including integers and floating-point numbers.

  ```typescript
  let count: number = 42;
  ```

- **string**: Represents textual data.

  ```typescript
  let message: string = "Hello, Miraya!";
  ```

- **void**: Indicates that a function doesn't return a value.

  ```typescript
  function log(message: string): void {
    console.log(message);
  }
  ```

- **undefined** and **null**: Represent missing or uninitialized values.

  ```typescript
  let data: string | null = null;
  ```

## Object Types in TypeScript 🧰

TypeScript provides several ways to define object types:

- **Interfaces**: These define the structure of an object, specifying property names, types, and optional properties.

  ```typescript
  interface Person {
    name: string;
    age: number;
  }
  ```

- **Classes**: You can use classes to create object blueprints with both properties and methods.

  ```typescript
  class Rectangle {
    constructor(public width: number, public height: number) {}
  }
  ```

- **Enums**: Enums allow you to define a set of named constants, often used to represent a finite set of values.

  ```typescript
  enum Direction {
    Up,
    Down,
    Left,
    Right,
  }
  ```

- **Arrays and Tuples**: TypeScript supports arrays for lists of values and tuples for fixed-length arrays with specific types at each index.

  ```typescript
  let fruits: string[] = ["apple", "banana", "cherry"];
  let coordinates: [number, number] = [10, 20];
  ```

## Other TypeScript Types 🌌

- **any**: The `any` type allows you to work with values of any type, effectively opting out of TypeScript's type checking.

  ```typescript
  let value: any = 42;
  ```

- **object**: This type represents non-primitive values, i.e., anything that's not a `number`, `string`, `boolean`, `symbol`, `null`, or `undefined`.

  ```typescript
  let obj: object = { key: "value" };
  ```

- **unknown**: `unknown` is a type-safe counterpart of `any`. You must narrow it down to a specific type before using it.

  ```typescript
  let userInput: unknown = "Hello, TypeScript!";
  if (typeof userInput === "string") {
    let message: string = userInput;
  }
  ```

- **never**: The `never` type represents values that never occur. It's often used for functions that never return (throwing errors or entering infinite loops).

  ```typescript
  function throwError(message: string): never {
    throw new Error(message);
  }
  ```
