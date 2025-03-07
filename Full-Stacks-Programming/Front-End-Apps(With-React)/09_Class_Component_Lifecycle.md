# Class Component Lifecycle in React

Welcome to the **Class Component Lifecycle** video. After watching this video, you will be able to:
1. Explain a component's lifecycle.
2. Describe each phase.
3. List methods used in each phase.

React class components have lifecycles, meaning they go through three main phases over their lifetime: **mounting**, **updating**, and **unmounting**. During each phase, React provides specific lifecycle methods that you can access to manage the component's behavior.

---

## Phases of a Component's Lifecycle

### 1. Mounting

The mounting phase is when the component is first created and added to the DOM. During this phase, the following methods are called in order:

1. **constructor**: Constructs the object and may call the super constructor with the `props` object if any specific props are being set.
2. **getDerivedStateFromProps**: Used when the state depends on changes to props.
3. **render**: This mandatory method returns the JSX that makes the component appear and can return only one root element.
4. **componentDidMount**: Invoked immediately after the component is mounted or inserted into the DOM tree.

### Example

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

**Order of Console Logs**:
1. Constructor
2. Render
3. Component Did Mount

### 2. Updating

The updating phase occurs when the component's state or props change, leading to a re-render. The following methods are called in order:

1. **getDerivedStateFromProps**: Used when the state depends on changes to props.
2. **shouldComponentUpdate**: By default, returns true. This method is called to determine whether the component should update. It can return false to prevent re-rendering.
3. **render**: Updates the component in the UI.
4. **getSnapshotBeforeUpdate**: Invoked just before the changes are rendered. It provides access to the component's previous props and state before updating.
5. **componentDidUpdate**: Invoked immediately after updating occurs. This method allows you to create side effects such as sending network requests or calling `this.setState`.

### Example

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
    console.log('Render');
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

**Order of Console Logs**:
1. Render (initial render)
2. Component Did Update (after state change)

### 3. Unmounting

The unmounting phase occurs when the component is removed from the DOM tree. This phase has only one lifecycle method:

1. **componentWillUnmount**: Called just before the component is removed from the page, marking the end of its lifecycle. This method is used to perform necessary cleanup such as canceling network requests or removing listeners.

### Example

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

**Order of Console Logs**:
1. Component Will Unmount (after 5 seconds)

---

## Summary of Lifecycle Methods

### Mounting Phase
- **constructor**
- **getDerivedStateFromProps**
- **render**
- **componentDidMount**

### Updating Phase
- **getDerivedStateFromProps**
- **shouldComponentUpdate**
- **render**
- **getSnapshotBeforeUpdate**
- **componentDidUpdate**

### Unmounting Phase
- **componentWillUnmount**

### Common Method
- **render** (used in both mounting and updating phases)

---

In this video, you learned that the lifecycle of a React component refers to its relationship with the DOM. The three phases include:
1. **Mounting**: Methods include `constructor`, `getDerivedStateFromProps`, `render`, and `componentDidMount`.
2. **Updating**: Methods include `getDerivedStateFromProps`, `shouldComponentUpdate`, `render`, `getSnapshotBeforeUpdate`, and `componentDidUpdate`.
3. **Unmounting**: Method includes `componentWillUnmount`.

Understanding these lifecycle methods is crucial for managing component behavior and optimizing performance in React applications.