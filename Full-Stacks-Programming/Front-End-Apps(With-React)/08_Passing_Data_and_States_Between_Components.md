# Passing Data and States Between Components

Welcome to **Passing Data and States Between Components**. After watching this video, you will be able to:
1. Describe the lifecycle of React components.
2. Explain how to pass data and states to components.

---

## Lifecycle of React Components

Each React component has three phases in its lifecycle:

### 1. Mounting

This phase is when the component is first created and inserted into the DOM. Four methods are called in this order during mounting:

1. **constructor**: Constructs the object. This may call the superconstructor with the `props` object if any specific props are being set.
2. **getDerivedStateFromProps**: Used when the state depends on changes to props.
3. **render**: Mandatory method in a React component. Returns the JSX that makes the component appear. Must return a DOM element and can only return one root element which may contain nested child elements.
4. **componentDidMount**: Invoked immediately after the component is mounted or inserted into the DOM tree.

### 2. Updating

This phase occurs when the component's state or props change, causing a re-render. Five methods are called in this order during updating:

1. **getDerivedStateFromProps**: Used when the state depends on changes to props.
2. **shouldComponentUpdate**: By default, returns true. Called to determine whether the component should update. This method can return false to prevent re-rendering.
3. **render**: Updates the component.
4. **getSnapshotBeforeUpdate**: Invoked just before the changes are rendered. Keeps track of what has changed.
5. **componentDidUpdate**: Invoked immediately after updating occurs. 

### 3. Unmounting

This phase occurs when the component is removed from the DOM tree. One method is called during unmounting:

1. **componentWillUnmount**: Called when the component is about to be removed from the DOM.

---

## Example: Component Lifecycle Methods

### Mounting Phase Example

```jsx
class App extends React.Component {
  constructor(props) {
    super(props);
    console.log('Constructor');
  }

  componentDidMount() {
    console.log('Component Did Mount');
  }

  render() {
    console.log('Render');
    return <h1>Hello, world!</h1>;
  }
}

export default App;
```

### Updating Phase Example

```jsx
class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  shouldComponentUpdate(nextProps, nextState) {
    return true;
  }

  componentDidUpdate(prevProps, prevState) {
    console.log('Component Did Update');
  }

  incrementCounter = () => {
    this.setState({ count: this.state.count + 1 });
  };

  render() {
    return (
      <div>
        <button onClick={this.incrementCounter}>Increment</button>
        <p>Count: {this.state.count}</p>
      </div>
    );
  }
}

export default App;
```

### Unmounting Phase Example

```jsx
class AppInner extends React.Component {
  componentWillUnmount() {
    console.log('Component Will Unmount');
  }

  render() {
    return <h1>Inner Component</h1>;
  }
}

class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = { showInner: true };
  }

  componentDidMount() {
    setTimeout(() => {
      this.setState({ showInner: false });
    }, 5000);
  }

  render() {
    return (
      <div>
        {this.state.showInner ? <AppInner /> : <div>Inner Component Unmounted</div>}
      </div>
    );
  }
}

export default App;
```

---

## Passing Data Between Components

### 1. Parent to Child (Using Props)

Props are used to pass data from a parent component to a child component. Props are read-only.

#### Example: Parent to Child

**Parent Component (App.jsx)**

```jsx
import React from 'react';
import EmployeeDetails from './EmployeeDetails';

class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: 'John',
      color: 'green'
    };
  }

  handleInputChange = (event) => {
    const { name, value } = event.target;
    this.setState({ [name]: value });
  };

  render() {
    return (
      <div>
        <input
          type="text"
          name="name"
          value={this.state.name}
          onChange={this.handleInputChange}
        />
        <input
          type="text"
          name="color"
          value={this.state.color}
          onChange={this.handleInputChange}
        />
        <EmployeeDetails name={this.state.name} color={this.state.color} />
      </div>
    );
  }
}

export default App;
```

**Child Component (EmployeeDetails.jsx)**

```jsx
import React from 'react';

class EmployeeDetails extends React.Component {
  render() {
    return (
      <div>
        <p>Name: {this.props.name}</p>
        <p>Color: {this.props.color}</p>
      </div>
    );
  }
}

export default EmployeeDetails;
```

### 2. Child to Parent (Using Callbacks)

A callback function can be passed as a prop from the parent to the child component. The child component can then call this function to pass data back to the parent.

#### Example: Child to Parent

**Parent Component (App.jsx)**

```jsx
import React from 'react';
import AppInner from './AppInner';

class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = { currentTime: '' };
  }

  handleTimeUpdate = (time) => {
    this.setState({ currentTime: time });
  };

  render() {
    return (
      <div>
        <p>Current Time: {this.state.currentTime}</p>
        <AppInner parentCallback={this.handleTimeUpdate} />
      </div>
    );
  }
}

export default App;
```

**Child Component (AppInner.jsx)**

```jsx
import React from 'react';

class AppInner extends React.Component {
  componentDidMount() {
    this.intervalId = setInterval(() => {
      const currentTime = new Date().toLocaleTimeString();
      this.props.parentCallback(currentTime);
    }, 1000);
  }

  componentWillUnmount() {
    clearInterval(this.intervalId);
  }

  render() {
    return <h1>Inner Component</h1>;
  }
}

export default AppInner;
```

---

## Conclusion

In this video, you learned that:

1. Each React component has three phases in its lifecycle: mounting, updating, and unmounting. Methods are called in a specific order during these phases.
2. Data can be passed between React components from parent to child using props and from child to parent using callbacks.

Understanding the lifecycle of components and how to pass data between them is essential for creating dynamic and interactive React applications.