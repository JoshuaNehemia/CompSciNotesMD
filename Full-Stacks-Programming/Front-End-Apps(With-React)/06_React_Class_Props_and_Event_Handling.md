# Working with React Class Components, Props, and Event Handling

Welcome to a video on working with **React class components, props, and event handling**. After watching this video, you will be able to:
1. Define a class component.
2. Describe how a class component works.
3. Describe how to manage the state in a React class component.
4. Describe how to use props in a class component in React.
5. Describe how to handle events in class components.

---

## Defining a Class Component

A **class component** in React is a JavaScript class that extends `React.Component` from the React library. Class components were the primary way of defining components in React before the introduction of hooks. They encapsulate UI components and their behavior into reusable building blocks.

### Basic Example of a Class Component

```jsx
import React, { Component } from 'react';

class MyComponent extends Component {
  render() {
    return (
      <div>
        <h1>Hello, world!</h1>
      </div>
    );
  }
}

export default MyComponent;
```

- **Import Statements**: `import React, { Component } from 'react';` - Imports React and the component class.
- **Class Declaration**: `class MyComponent extends Component {}` - Declares a class extending `React.Component`.
- **Render Method**: `render() {}` - Required method that returns JSX representing the UI.
- **Export Statement**: `export default MyComponent;` - Exports the class component for use in other files.

---

## State Management in Class Components

State management is crucial in React class components. The state represents the data the component needs to render and respond to user interactions. You initialize the state in the constructor using `this.state` and update it using `this.setState`.

### Example: Managing State

```jsx
import React, { Component } from 'react';

class EmployeeDetails extends Component {
  constructor(props) {
    super(props);
    this.state = {
      emp_id: '',
      emp_email: ''
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
          name="emp_id"
          value={this.state.emp_id}
          onChange={this.handleInputChange}
        />
        <input
          type="text"
          name="emp_email"
          value={this.state.emp_email}
          onChange={this.handleInputChange}
        />
        <button onClick={() => alert(`ID: ${this.state.emp_id}, Email: ${this.state.emp_email}`)}>
          Show Details
        </button>
      </div>
    );
  }
}

export default EmployeeDetails;
```

- **Constructor**: Initializes the state with `emp_id` and `emp_email`.
- **handleInputChange Method**: Updates state properties based on user input.
- **Render Method**: Binds input values to state properties and handles events.

---

## Using Props in Class Components

Props, or properties, send data from parent to child components. The child component receives the data from the parent and can use it, but cannot modify it (read-only).

### Example: Using Props

#### Parent Component (OrganizationDetails.jsx)

```jsx
import React from 'react';
import EmployeeDetails from './EmployeeDetails';

class OrganizationDetails extends React.Component {
  render() {
    return (
      <EmployeeDetails employee_designation="Project Manager" />
    );
  }
}

export default OrganizationDetails;
```

#### Child Component (EmployeeDetails.jsx)

```jsx
import React, { Component } from 'react';

class EmployeeDetails extends Component {
  render() {
    const { employee_designation } = this.props;
    return (
      <div>
        <p>Designation: {employee_designation}</p>
      </div>
    );
  }
}

export default EmployeeDetails;
```

- **Parent Component**: Passes `employee_designation` prop to the child component.
- **Child Component**: Accesses and displays the `employee_designation` prop.

---

## Event Handling in Class Components

Event handling in React is the process of responding to user interactions such as clicks, mouseovers, and form submissions.

### Example: Handling Events

```jsx
import React, { Component } from 'react';

class EmployeeDetails extends Component {
  constructor(props) {
    super(props);
    this.state = {
      emp_id: '',
      emp_email: '',
      employee_designation: 'Project Manager'
    };
  }

  handleInputChange = (event) => {
    const { name, value } = event.target;
    this.setState({ [name]: value });
  };

  handleShowDetails = () => {
    const { emp_id, emp_email, employee_designation } = this.state;
    alert(`ID: ${emp_id}, Email: ${emp_email}, Designation: ${employee_designation}`);
  };

  render() {
    return (
      <div>
        <input
          type="text"
          name="emp_id"
          value={this.state.emp_id}
          onChange={this.handleInputChange}
        />
        <input
          type="text"
          name="emp_email"
          value={this.state.emp_email}
          onChange={this.handleInputChange}
        />
        <button onClick={this.handleShowDetails}>
          Show Details
        </button>
      </div>
    );
  }
}

export default EmployeeDetails;
```

- **onClick Event**: Calls `handleShowDetails` method to display an alert with state values.

---

## Conclusion

In this video, you learned that:

1. A **class component** in React is a JavaScript class extending `React.Component`.
2. Class components **manage state**, handle lifecycle events, and define component methods.
3. **Props** send data from parent to child components, and are read-only in the child component.
4. **Event handling** responds to user interactions within a React application.

These concepts are fundamental for working with React class components, enabling you to build dynamic and interactive user interfaces.