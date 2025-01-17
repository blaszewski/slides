# Examples: querying APIs from React

## Examples: querying APIs from React

loading todos in a React component:

```js
const [todos, setTodos] = useState([]);
async function loadTodos() {
  const todos = await fetchTodos();
  setTodos(todos);
}
```

```jsx
<button onClick={() => loadTodos()}>
  load todos from API
</button>
```

## Examples: querying APIs from React

code for adding a loading indicator:

```js
const [todos, setTodos] = useState([]);
const [loadingStatus, setLoadingStatus] = useState('idle');

async function loadTodos() {
  setLoadingStatus('loading');
  try {
    const todos = await fetchTodos();
  } catch (e) {
    setLoadingStatus('error');
  }
  setTodos(todos);
  setLoadingStatus('success');
}
```

## Examples: querying APIs from React

loading exchange rate data:

```ts
const [usdRates, setUsdRates] = useState<
  Record<string, number>
>({});
async function loadRate(currency) {
  const rate = await fetchExchangeRate('usd', currency);
  setUsdRates({ ...usdRates, [currency]: rate });
}
```

```jsx
<button onClick={() => loadRate('eur')}>
  load EUR rate
</button>
<button onClick={() => loadRate("jpy")}>
  load JPY rate
</button>
```
