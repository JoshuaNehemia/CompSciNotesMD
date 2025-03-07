# Introduction to States and Props in React

## Overview

After reviewing this information, you will be able to:
1. Explain the use of states in class components.
2. Explain the use of props in class components.
3. Compare and contrast states and props.

---

## States in Class Components

### Definition and Purpose

States allow you to change data in an application. In class components, the **state object** includes key-value pairs that specify different types of data you want to track in the application. React class components have a built-in state object, which stores property values belonging to the component. Any change in the state object re-renders the component.

### Types of States

- **Local State**: Lives in a single component and cannot be accessed by other components. Used for showing or hiding information within the component.
- **Shared State**: Can be accessed and changed by more than one component. Used for data that needs to be shared, like a list of orders in an ordering application.

### Characteristics

- **Plain JavaScript Object**: Represents information about the component's current situation.
- **Instance of Component Class**: Contains observable properties that control the component's behavior.
- **Dynamic and Interactive**: States determine how a component renders and behaves. They allow tracking changes, updating forms, buttons, timers, etc.

### Example

Consider a simple application with a button and a counter. When the user presses the button, the counter variable increases by one. The value is held in the state.

```jsx
class TestComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = { id: 1, name: "John", age: 25 };
  }

  render() {
    return (
      <div>
        <p>Name: {this.state.name}</p>
        <p>Age: {this.state.age}</p>
      </div>
    );
  }
}
```

---

## Props in Class Components

### Definition and Purpose

**Props** is short for properties. You use props to pass data between components in React. Data between components flows from parent to child only. Props are read-only components and are immutable.

### Characteristics

- **Data Flow**: Unidirectional from parent to child.
- **Read-Only**: Props cannot be modified from inside the component. 
- **Function Arguments**: Behave like arguments to functions that can be passed from one component to another.

### Example

```jsx
class TestComponent extends React.Component {
  render() {
    return (
      <div>
        <p>Name: {this.props.name}</p>
      </div>
    );
  }
}

// Usage
<TestComponent name="John" />
<TestComponent name="Jill" />
```

---

## Comparing States and Props

| Feature          | States                                                   | Props                                              |
|------------------|----------------------------------------------------------|----------------------------------------------------|
| **Mutability**   | Mutable within the component using `setState`            | Immutable; cannot be modified by the receiving component |
| **Usage**        | Manage and preserve component-specific data              | Pass data from parent to child                     |
| **Modification** | Data can be modified within the component                | Read-only; cannot be modified within the child component |
| **Scope**        | Limited to the component that defines it                 | Can be passed to any component from its parent     |

### Key Points

- **State**: Creates interactive components by managing internal data and re-rendering the component on data change.
- **Props**: Enable data flow between components, making components reusable by passing data from parent to child.

---

## Conclusion

In this lesson, you learned:
1. A **state** is a JavaScript object representing information about the component's current situation, allowing you to create interactive components.
2. **Props** pass data between components in a unidirectional flow from parent to child, ensuring components can access the necessary data without direct modification.
3. States are mutable within their own component, while props are immutable and only passed from parent to child.

These concepts are foundational for building dynamic and reusable React applications, enabling efficient data management and component communication.