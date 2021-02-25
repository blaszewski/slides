<!-- closely realated content in presentations typescript and react-->

# TypeScript basics for React

## TypeScript

_TypeScript_: superset of JavaScript that supports static typing

## Static typing

data types may be specified in order to support the development environment:

- auto completion
- errors when types mismatch

## Static typing

during build: TypeScript is translated to JavaScript, all type information is discarded

## Variable types

Variable types are usually detected automatically

_explicitly_ declaring variable types:

```ts
const age: number = 32;
const name: string = 'Samuel';
const loggedIn: boolean = true;
```

## Function types

```ts
function shorten(text: string, maxLen: number): string {
  // ...
}
```

```ts
const shorten = (text: string, maxLen: number): string => {
  // ...
};
```

## Function types

Functions without a return value: `void`

```ts
const logMessage = (message: string): void => {
  console.log(message);
};
```

## Array types

```js
let names: Array<string> = [];
names.push('Alice');
```

alternative syntax:

```ts
let names: string[] = [];
names.push('Alice');
```

## Generics

_Generics_: type declarations that can receive more specific type information when applied (via `<...>`)

## Generics

example: `Array` is a generic

```ts
const names: Array<string> = ['Alice', 'Bob', 'Charlie'];
```

example: React's `Component` is a generic

```ts
class MyComp extends Component<MyProps, MyState> {
  // ...
}
```

## Type assertions

Type assertions enable treating an existing object as a specific type

fails:

```ts
// type: HTMLElement or null
const nameInput = document.getElementById('name-input');
console.log(nameInput.value);
```

works:

```ts
const nameInput = document.getElementById(
  'name-input'
) as HTMLInputElement;
console.log(myInput.value);
```

## Any

Any: variable can be of any type - arbitrary properties may be accessed

```ts
const nameInput = document.getElementById(
  'name-input'
) as any;
console.log(nameInput.value);
```

## Type and interface declarations

**Interfaces** describe the structure of an object / of a class in detail (e.g.: `Todo`, `Person`)

**Types**: similar to interfaces, but are also applicable to strings, arrays, ...

## Types and interfaces

Essentialy types offer more functionality than interfaces

https://stackoverflow.com/a/52682220/

## Types

```ts
type Todo = {
  id: number;
  title: string;
  completed: boolean;
};

type TodoCollection = Array<Todo>;
```

## Types and objects

```ts
type Todo = {
  id: number;
  title: string;
  completed: boolean;
  // optional
  description?: string;
  // method
  toggle: (id: number) => void;
};
```

## Type declarations for libraries

Some JavaScript libraries come with type declarations for TypeScript included - e.g. _redux_.

For other libraries there are usually external declaration packages that are prefixed with _@types/_; e.g. for _react_ there's the package _@types/react_.