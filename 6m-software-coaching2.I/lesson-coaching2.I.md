# 2.1 Introduction to ReactJS

## NPM

Node Package Manager
creates a package.json file and allows us to install dependencies from the npm respository (https://www.npmjs.com/)

Read more: https://www.w3schools.com/whatis/whatis_npm.asp

Note that it's usually important to use the same NodeJS version for the app you're working on.

A useful tool for you to explore - Node Version Manager (NVM).

Allows you to select the Node version environment.

Setup NVM Guide: https://www.freecodecamp.org/news/node-version-manager-nvm-install-guide/

## Virtual DOM

DOM - Document Object Model - how the browser represents the page

VDOM - React uses to represent the DOM - diffing

ReactJS Virtual DOM: https://blog.greenroots.info/reactjs-virtual-dom-and-reconciliation-explain-like-im-five

## Create React App

There are a few ways of creating a React app. create-react-app (CRA) is the easiest way for new learners because all the dependencies and settings are all created for you.

```sh
npx create-react-app my-app
```

This creates the boiler plate code for a basic React app.

To start the app

```sh
npm start
```

## Components and JSX

JSX - Javascript XML

```js
	function MyComponent() { // props = { firstName: "Not Provided"}
		// JS code here
		console.log("hello"); ✅

		// JSX is used in the return statement
		return (
			<div>
				console.log("hello"); ❌
				<h1>My App</h1>
				<p>{firstName}</p>
			<div/>
		)
	}
```

```js
App.js;

function App() {
  return (
    <div>
      <MyComponent firstName="John" />
    </div>
  );
}
```

In the return section, components defined by you has to be capitalized e.g. <MyComponent>

React recognizes capitalized tags as defined by you, and lower case ones as HTML e.g.

```js
	<Header>My Header Component</Header>

	<header><h1>HTML header tag</h1></header>
```

### React Fragments

React only allows 1 root element per return statement.

```js
	return (
		<div>Hello World</div>
		<div>Hello again</div> ❌
	)
```

If there is more than 1, use fragments to enclose them.

```js
return (
  <>
    <div>Hello World</div>
    <div>Hello again</div>
  </>
);
```

note this also applies when returning JSX in a map method

```js
{
  cars.map((car) => (
    <>
      <p>{car.brand}</p>
      <p>{car.color}</p>
      <p>{car.price}</p>
    </>
  ));
}
```

## Styling React

Inline styles (highest specificity)

```js
	<div style={{ padding: 50 }}>
```

CSS stylesheets

```js
	import "./styles.css" // usual css import

	<div className="card">
```

CSS Modules

```js
	import styles from "./MyComponent.module.css"; // CSS Modules - generates unique class names - no collision

	<div className={styles.card} >
```

Other Styling options:

- Tailwind, Bootstrap

## Images

There are 2 main ways of using images in React

Imports https://create-react-app.dev/docs/adding-images-fonts-and-files/ <- use this
Public Folder https://create-react-app.dev/docs/using-the-public-folder/

# 2.2 Functional Components and Props

## Functional Components

as opposed to Class Components - which we don't use anymore because it is deprecated but still supported.

different ways of defining a function - both are okay! Mostly just a matter of preference.

```js
// function declaration
function MyComponent() {}
// arrow function
const MyComponent = () => {};
```

If unsure, you can use function declarations because they are hoisted.

What is hoisting: https://www.w3schools.com/js/js_hoisting.asp

## Import and Export (JavaScript Module System)

Not a React concept but for all JS applications - so that we can keep our code modular instead of 1 long chunk of code.

### Default Exports

```js
export default MyComponent;

import MyComponent from "./MyComponent";
```

### Named Exports

```js
export const MyComponent = () => {};

import { MyComponent } from "./MyComponent";
```

Named exports vs default exports: https://medium.com/@etherealm/named-export-vs-default-export-in-es6-affb483a0910

## Props

Props is a reserved keyword in React.

```js
function MyComponent(props) {
  return <p>{props.firstName}</p>;
}
```

## Destructuring Props

```js
// with default parameters
function MyComponent({ firstName = "Not entered" }) {
  return <p>{firstName}</p>;
}

function MyComponent(props) {
  const { firstName = "John" } = props;
  return <p>{firstName}</p>;
}
```

# Additional Practice

Replicate this page using React.
https://unique-brioche-fcbba6.netlify.app/
