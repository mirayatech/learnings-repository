# TypeScript Type Declarations

In TypeScript, there are various ways to declare types. Here are some of them:

## Type Annotation 😀

**📝 Explanation:** Type annotation specifies the type of a variable.

```typescript
let username: string = "John";
```

## Type Narrowing 🎯

**📝 Explanation:** Type narrowing is the process of refining a type based on a condition.

```typescript
let value: number | string = "42";

// Narrowing the type of 'value' to 'number' here
if (typeof value === "number") {
  value = value * 2;
}
```

## Function Type 🔧

**📝 Explanation:** Function types describe the shape of functions.

```typescript
type AddFunction = (a: number, b: number) => number;

const add: AddFunction = (a, b) => a + b;
```

## Union Types 🧩

**📝 Explanation:** Union types allow a value to have multiple possible types.

```typescript
let result: number | string = 42;

result = "forty-two";
```

## Intersection Types ♻️

**📝 Explanation:** Intersection types combine multiple types into one.

```typescript
type Person = { name: string };

type Address = { address: string };

type ContactInfo = Person & Address;

const contact: ContactInfo = { name: "John", address: "123 Main St" };
```

## Type Aliases 🏷️

**📝 Explanation:** Type aliases create custom names for types.

```typescript
type Point = [number, number];

const origin: Point = [0, 0];
```

## Index Signatures 🏗️

**📝 Explanation:** Index signatures define types for object properties with dynamic names.

```typescript
type Config = {
  [key: string]: number;
};

const settings: Config = {
  width: 800,
  height: 600,
};
```

## Tuple Types 📦

**📝 Explanation:** Tuple types specify an array with a fixed number of elements.

```typescript
type Pair = [string, number];

const coordinates: Pair = ["x", 42];
```

## Type Assertions 🧙‍♂️

**📝 Explanation:** Type assertions tell TypeScript to treat a value as a specific type.

```typescript
let inputValue: any = "42";

let numericValue: number = inputValue as number;
```

## Literal Types 🚦

**📝 Explanation:** Literal types allow specifying exact values as types.

```typescript
type Direction = "left" | "right" | "up" | "down";

const move: Direction = "left";
```

## Type Inference 🕵️‍♂️

**📝 Explanation:** Type inference automatically determines a variable's type.

```typescript
let x = 42;
```
