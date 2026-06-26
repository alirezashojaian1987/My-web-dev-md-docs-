React is like a pile of legos. The components act as legos. In other words, components are building block of the project.
One of the good things about components is reusability.
It has some html tags. also js as well.

Components are like functions that return HTML elements. They serve the same purpose as JavaScript functions, but work in isolation and return HTML.
##### Create your first component
When creating a React component, the component's name **Must** start with an uppercase letter.
```jsx
function Car() {
  return (
    <h2>Hi, I am a Car!</h2>
  );
}
```
##### Rendering a component
Now your React application has a component called `Car`, which returns an `<h2>` element.
To use this component in your application, refer to it like this:`<Car />
*Example:*
```jsx
createRoot(document.getElementById('root')).render(
  <Car />
)
```
##### Props
Arguments can be passed into a component as `props`
You send the arguments into the component as HTML attributes.
```jsx
function Car(props) {
  return (
    <h2>I am a {props.color} Car!</h2>
  );
}

createRoot(document.getElementById('root')).render(
  <Car color="red"/>
);
```

##### Rendering a component twice
```jsx
function Car(props) {
  return (
    <h2>I am a {props.brand}!</h2>
  );
}

function Garage() {
  return (
    <>
      <h1>Who lives in my Garage?</h1>
      <Car brand="Ford"/>
      <Car brand="BMW"/>
    </>
  );
}

createRoot(document.getElementById('root')).render(
  <Garage />
);
```
##### Components in files
React is all about re-using code, and it can be a good idea to split your components into separate files.
To do that, create a new file in the `src` folder with a `.jsx` file extension and put the code inside it:
*!Note:* Note that the filename must start with an uppercase character.
Vehicle.jsx
```jsx
function Car() {
  return (
    <h2>Hi, I am a Car!</h2>
  );
}

export default Car;
```
Main.jsx
```jsx
import { createRoot } from 'react-dom/client'
import Car from './Vehicle.jsx';

createRoot(document.getElementById('root')).render(
  <Car />
);
```