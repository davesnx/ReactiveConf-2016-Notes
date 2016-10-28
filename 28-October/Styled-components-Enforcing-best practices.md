# Scaling ReactJS Applications
by Max Stoiber

### The Component Age

We are in the era of Components, also CSS are focused on Components.
with posibility of compose them.

--

### Best Practices

1. Focussed components, tiny and small
2. Completely independent, isolated and SRP
3. Split smart and dumb, differentiate between Presentational or Logical (fetching data, formating data, etc...)

--

### What about styling?

The CSS was made for Cascading or Pages not for Components.

1. Single-use classes
2. Components as a styling construc

So we can use JS to put the style on the components.

REF. Michaecl Chan @chantastic

--

### Enforcing best practices?

Manually is not the best option, but basically you can automate it.

--

### styled-components

Remove the mapping between styles and components.
the mapping means: that CSS classes are linked with DOM Elements.

For removing this map using styled-components:

```js
import styled from 'styled-components'

// Create a <Title> react component that renders an <h1> which is
// centered, palevioletred and sized at 1.5em
const Title = styled.h1`
  font-size: 1.5em;
  text-align: center;
  color: palevioletred;
`

// Create a <Wrapper> react component that renders a <section> with
// some padding and a papayawhip background
const Wrapper = styled.section`
  padding: 4em;
  background: papayawhip;
`

ReactDOM.render(
  <Wrapper>
    <Title>Hello World, this is my first styled component!</Title>
  </Wrapper>,
  document.getElementById('root')
)

```

### Features

- Using ES6 strings
- Write actual CSS
- Can pass props into this styles
- Full Support React Native

--

### Theming

theme-provider allows us to wrapp our components and pass the theme,
that is a plain object with some values into all the childs for use this
theme variables inside.

```js
import { ThemeProvider } from 'styled-components'

const theme = {
  main: 'mediumseagreen'
};

// Create a GreenSection component that renders its children wrapped in
// a ThemeProvider with a green theme
const GreenSection = (props) => {
  return (
    <ThemeProvider theme={theme}>
      {props.children}
    </ThemeProvider>
  )
}
```

--

### Problems that can appear:
#### Linting

- Just the standard JS linting (eslint, for instance)
- Have it on Atom and Sublime
