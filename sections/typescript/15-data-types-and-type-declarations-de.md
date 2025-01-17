# Datentypen und Typendeklarationen

## Datentypen

- boolean
- number
- string
- array
- object
- any

## Variablentypen

Variablentypen können beim Deklarieren von Variablen angegeben werden:

```ts
let age: number = 32;
```

```ts
let age: number;
age = 32;
age++;
```

## Type Inference

in vielen Fällen kennt TypeScript den Typ automatisch (keine Annotation notwendig):

```ts
let age = 32;
```

## Primitive Typen

```ts
const age: number = 32;
const name: string = 'Alice';
const loggedIn: boolean = true;
```

## Array-Typen

```js
let names: Array<string> = [];
names.push('Alice');
```

alternative Schreibweise:

```ts
let names: string[] = [];
names.push('Alice');
```

## Objekttypen

Typendeklaration:

```ts
let todo: {
  id: number;
  title: string;
  completed: boolean;
};
```

Zuweisung:

```ts
todo = { id: 1, title: 'foo', completed: false };
```

## Objekttypen

optionale Einträge werden mit `?` gekennzeichnet

```ts
let todo: {
  id: number;
  title: string;
  completed: boolean;
  date?: string;
};
```

## Any

Manchmals möchten wir die Typenüberprüfung aufheben:

```ts
const nameInput: any = document.getElementById(
  'name-input'
);
console.log(nameInput.value);
```

Deklarieren wir eine Variable asl `any`, können wir auf beliebige Properties zugreifen
