---
author: kapnobatai136

levels:

  - basic

  - advanced

  - medium

type: normal

category: must-know


links:

  - '[redux.js.org](https://redux.js.org/basics/usage-with-react){documentation}'

notes: This can be also placed in the react subtopic

aspects:
  - introduction

---

# Use Redux with React (2)

---
## Content

Now, looking in `Counter.js`, we must connect the component to our `store`:

```jsx
// Counter.js
import React from "react";
import { connect } from "react-redux";

class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
  }
  render() {
    // ...
  }
}

function mapStateToProps(state) {
  return {
    count: state.count
  };
}

export default connect(mapStateToProps)(
  Counter
);
```

Let's look at this code step-by-step. We want to connect our `<Counter />` component to our `store`, and to do this we have to make use of the `connect()` method. What this method does is that it takes our component as input, and returns a **new** connected component class that wraps our `<Counter />` component. Notice how you pass the `mapStateToProps` and `Counter` to the `connect` method. This is because `connect()` is a higher order function, which basically means that it returns another function that takes `Counter` as an argument.

The last piece of the puzzle is the `mapStateToProps` function which does exactly what the name suggests. The `<Counter />` component has `count: 0` as a state, and the `mapStateToProps` function will create a new object where the key represents the name of the `prop`, in our case `count`, and the value will be extracted from `state.count`. Now, when you use `connect()` to create a new connected component, the method will pass the entire state of the `<Count />` component to the `mapStateToProps` function which in turn feeds your returned object as `prop`s to the new **connected component**.

Phew, that was a lot of work, but we have finally managed to connect our component to our store, and we are ready to start using `react-redux`.

---
## Practice

Connect the `<Counter />` component to the Redux `store`:

```jsx
export default ??? ??? ???;
```

* `connect`
* `(mapStateToProps)`
* `(Counter)`
* `(mapPropsToState)`
* `(mapProps)`
* `(mapState)`

---
## Revision

Connect the `<Counter />` component to the Redux `store`:

```jsx
export default ??? ??? ???;
```

* `connect`
* `(mapStateToProps)`
* `(Counter)`
* `(mapPropsToState)`
* `(mapProps)`
* `(mapState)`