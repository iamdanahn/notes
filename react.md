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

