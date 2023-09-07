# React
> React is a declarative UI library. JS (imperative) is like telling the cook to "Knit the dough, roll the dough, add tomato sauce, add cheese, add ham, add pineapple, bake at 200 degrees Celsius in a stone oven for...”. But React is like to tell the cook: “A Hawaiian pizza please!” 

## Index
1. Building UI with Components
2. Props

<br>

### 1. Building UI with Components
In React, components are functions that return UI elements. The component should be capitalised. 

```jsx
<script type="text/jsx">
  const app = document.getElementById("app")
  function Header() {
     return (<h1>Develop. Preview. Ship. 🚀</h1>)
   }

   ReactDOM.render(<Header />, app)
</script>
```
<br>

### 2. Props
Like the attributes in HTML, we can pass information as properties to components. Then, these props can pass from parent components to child components.  
Here, we pass `title` as props from `HomePage` to `Header`:

```jsx
function HomePage() {
  return (
    <div>
      <Header title="React 💙" />
    </div>
  );
}
```
if we `console.log` the props, we can see that the props is object with a `title` property:
```jsx
function Header(props) {
    console.log(props) // { title: "React 💙" }
 }

 function HomePage() {
   return (
     <div>
       <Header title="React 💙" />
     </div>
   )
 }
 ReactDOM.render(<HomePage />, app)
```
So object destructuring can be used, also use curly braces {} to write regular JavaScript directly inside JSX markup:

```jsx
function Header({ title }) {
    console.log(title) // "React 💙"
return <h1>{title}</h1>;
```

<br>

### 3. Iterate in an array and arrow function
```jsx
function HomePage() {
  const names = ['Ada Lovelace', 'Grace Hopper', 'Margaret Hamilton'];

  return (
    <div>
      <Header title="Develop. Preview. Ship. 🚀" />
      <ul >
        {names.map((name) => (
          <li key={name}>{name}</li>
        ))}
      </ul>
    </div>
  );
}
```
👆 Here, a key is needed to identify the unique items in an array.

<br>

### 4. Event Handler
- Listen to events: (event names are camelCased)

```jsx
function HomePage() {
  // ...
  return (
    <div>
      {/* ... */}
      <button onClick={}>Like</button>
    </div>
  );
}
```
- handle event:
```jsx
function HomePage() {
  // ...

  function handleClick() {
    console.log("increment like count")
  }

  return (
    <div>
      {/* ... */}
      <button onClick={}>Like</button>
    </div>
     )
   }
```
- call the handle:
```jsx
function HomePage() {
  //    ...
  function handleClick() {
    console.log('increment like count');
  }

  return (
    <div>
      {/* ... */}
      <button onClick={handleClick}>Like</button>
    </div>
  );
}
```

<br>

### 5. State
`useState()` returns an array, so we can access the array values with array destructuring:
```jsx
function HomePage() {
  const [likes, setLikes] = React.useState(0);
}
```
```
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
