# Component events

## Data/event flow

- parent → child: props
- child → parent: events

## Component events

Props:

A component (e.g. _App_) may pass data (from its state) down to a child component (e.g. _Rating_)

Events:

A sub-component may trigger an event which will cause the state of a parent to update

## Component events

Event handlers are defined as functions and passed down via props.

## Component events

Example:

```jsx
<Rating
  value={prodRating}
  onChange={(newRating) => setProdRating(newRating)}
/>
```

<img src="assets/rating.png" style="width: 16em" />

## Component events

example prop types for a rating component:

```tsx
type RatingProps = {
  value: number;
  onChange?: (value: number) => void;
};
```

## Component events

```tsx
function Rating(props: RatingProps) {
  const starIds = [1, 2, 3, 4, 5];
  return (
    <div>
      {starIds.map((id) => (
        <span
          onClick={() => {
            if (props.onChange) {
              props.onChange(id);
            }
          }}
          key={id}
        >
          {id <= props.value ? '★' : '☆'}
        </span>
      ))}
    </div>
  );
}
```

## Component events

Using the Rating component:

```jsx
const [prodRating, setProdRating] = useState(3);
```

```jsx
<Rating
  value={prodRating}
  onChange={(newRating) => setProdRating(newRating)}
/>
```
