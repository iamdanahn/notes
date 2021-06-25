# Functional vs Class
https://www.twilio.com/blog/react-choose-functional-components

# React Context
https://www.freecodecamp.org/news/react-context-in-5-minutes/
https://scrimba.com/scrim/czkvE4sw
Context is similar to Redux where data can be sent to different components

# PropTypes (type checking)
https://www.youtube.com/embed/SKqFMYOSy4g
https://reactjs.org/docs/typechecking-with-proptypes.html#gatsby-focus-wrapper
NOTE: 
 - Flow or TypeScript are very similar
 - PropTypes must be imported
 - Only checks types for props passed down

It is possible to check for types (string, number) using a built in React 
PropTypes feature.
To run typechecking on the props for a component, you can assign the special propTypes property:
This will help catch any bugs as content is filled out.

```js
import PropTypes from 'prop-types';

class Greeting extends React.Component {
  render() {
    return (
      <h1>Hello, {this.props.name}</h1>
    );
  }
}

Greeting.propTypes = {
  name: PropTypes.string
};
```

# Hooks
Basics: useState, useEffect, useContext
- Can only be called at top level of the function.

### useState - creates internal state
Re-renders UI when data changes
```js
const [count, setCount] = useState(0);
// const [stateName, setState] = useState(default value)

```

### useEffect - lifecycle hooks
covers:
- componentDidMount
- componentDidUpdate
- componentWillUnmount
```js
useEffect(() => {
  // runs w.e is inside the block
})

useEffect(() => {

}, [])
// if 2nd arg is supplied, runs whenever any state inside updates
// if 2nd arg is empty, only runs at cdM

useEffect(() => {
  return () => {
    // anything inside the return of useEffect runs when the component is 
    // destroyed. Acts as cwUM
  }
})
```

### useContext - shares data without passing props
```js
// this moods can be shared in disconnected componenets by using createContext
const moods = {
  happy: ":)",
  sad: ":("
}

// moods is now "stashed" in the Context
const MoodContext = createContext(moods)

// to use it in a separate component, create a Provider and any children
// can inherit the value without passing down props
function App(props) {
  return (
    <MoodContext.Provider value={moods.happy}>
      <MoodEmoji />
    </MoodContext.Provider>
  )
}

function MoodEmoji() {
  // access the MoodContext by using `useContext`
  // consumes value form nearest parent provider
  const mood = useContext(MoodContext);

  // mood updates based on value in parent provider
  return (
    <p>{ mood }</p>
  )
}
```