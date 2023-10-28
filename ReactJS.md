#programming #library
Official website : [reactJS](https://reactjs.org/)

React is a library for building user interface. It is not a framework - it's not even exclusive to the web. It's used with other libraries to render to certain environments.
For instance, React Native can be used to build mobile applications.

Primary goal is to minimize the bugs that occur when developers are building UIs. It does this through the use of components. It abstracts away much of the rendering work, leaving you to concentrate on the UI design.

React use [[JSX]] syntax, which enable to write HTML like code inside Javascript.

To create a new HTML element with React in Javascript, we can write
```jsx
const header = (
	<header>
		<h1>Hello World</h1>
	</header>
)
```

The above code is in JSX syntax. [Babel](https://babeljs.io) will convert JSX syntax to the javascript code, and React will handle create new HTML element.
```javascript
const header = React.createElement('header', null, 
		React.createElement('h1', null, 'Hello World')
		);
```

React will create a HTML element of 
```html
<header>
	<h1> Hello World </h1>
</header>
```

If JSX syntax were not introduced, we will be having to write React native syntax, which will get messy as the project grows.
