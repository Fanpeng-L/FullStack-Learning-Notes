> React is a declarative UI library. JS (imperative) is like telling the cook to "Knit the dough, roll the dough, add tomato sauce, add cheese, add ham, add pineapple, bake at 200 degrees Celsius in a stone oven for...”. But React is like to tell the cook: “A Hawaiian pizza please!”

<br>

# 1. Components

Syntax:

```jsx
function Header() {
  return <h1>i am a header component</h1>;
}

export default Header;
```

One component Can only return one Single Top level element.

<br>

# 2. JSX

use `{}` to add JavaScript logic or reference a dynamic property:

```jsx
function Dog(){
  return <p> {3 + 5}</P>
}
```

# 3. Style in React

- `className` to add class
- same stylesheet name as the component.

⭐️ webpack help us bundle the css with the file

# 4. Props

```jsx
<Greet name="John" />
 <Avatar
      person={{ name: 'Lin Lanying', imageId: '1bX5QH6' }}
      size={100}
    />
```

# 5. conditional logic

```jsx
export default function RollDice() {
  const num1 = Math.floor(Math.random() * 3) + 1;
  const num2 = Math.floor(Math.random() * 3) + 1;

  return (
    <div>
      <h2>Roll the dice</h2>
      // only show the h3 when num1 === num2
      {num1 === num2 && <h3>You win!</h3>}
      <p>Num1: {num1}</p>
      <p>Num1: {num2}</p>
    </div>
  );
}
```

<br>

# 6. maping array

```jsx
export default function Colors({ colors }) {
  return (
    <div>
      <p>Color List</p>
      <ul>
        {colors.map((color) => {
          <li>{color}</li>;
        })}
      </ul>
    </div>
  );
}
```

<br>

# 7. Event

```jsx
function handleClick() {
  console.log("Clicked!");
}

export default function Clicker() {
  return (
    <div>
      <p>Click the button</p>
      <button onClick={handleClick}>Click</button>
    </div>
  );
}
```

### 5. State

`useState()` returns an array, so we can access the array values with array destructuring:

```jsx
function HomePage() {
  const [likes, setLikes] = React.useState(0);
}
```

```jsx
function HomePage() {
  // ...
  const [likes, setLikes] = React.useState(0);

  function handleClick() {
    setLikes(likes + 1);
  }

  return (
    <div>
      {/* ... */}
      <button onClick={handleClick}>Likes ({likes})</button>
    </div>
  );
}
```

💡Props is read-only information that's passed to components. State is information that can change over time, usually triggered by user interaction.

### 6.
