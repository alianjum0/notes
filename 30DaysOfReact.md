# 30 Days of React
## Day 1
* Internal: Written inside the html file
* External:  Linked from another file

* It is preferred to put JavaScript in the body.
* let and const are block scope, var is functions scope. Avoid using var in ES6
## Data Types
1. Primitive/Immutable: Numbers, Strings,  Booleans, Null, Undefined
2. Non-Premitive/Mutable: Objects, Functions, Arrays

* Primitive data types can be compared by value whereas non-primitive data
  types can not be compared with values.

## Template Literals
* ${expression}
```
let a = 2
let b = 3
console.log('the sum of ${a} + ${b} is ${a + b}`)  
```
ES6 string interpolation 

## String functions
```
let first_name = 'Damn'
let last_name = 'it'
let fn = first_name + last_name
```
1. fn.length - size of string
2. fn[0] - character at index
3. fn.toUpperCase()
4. fn.toLowerCase()
5. fn.substr(5,2) - it, 2nd parameter is number of characters
6. fn.substring(5,7) - it, 2nd parameter is index
7. fn.split(' ') - ['Damn', 'it']
8. fn.trim() - remove trailing spaces from beginning and end
9. fn.includes('it) - true
10. fn.replace('Damn', 'Dang') - 'Dang it'
11. fn.charAt(0) - D
12. fn.charCodeAt(0) - ASCII number of D
13. ...
19. matchWith()
```
let txt = 'In 2019, I ran 30 Days of Python. Now, in 2020 I am super exited to start this challenge'
let regEx = /\d+/
console.log(txt.match(regEx))  // ["2", "0", "1", "9", "3", "0", "2", "0", "2", "0"]
console.log(txt.match(/\d+/g)) // ["2019", "30", "2020"]
```
* String to Int: 
parseInt(), Number(), Plus sign e.g +Num

## Arrays
```
 let array = []
```
* Arrays can have items of different data types.
* Initialize array with 0
```
 let arr = Array(8).fill(0)
```
* concat two arrays
```
 const fruitsVegitables = fruits.concat(vegetables)
```


* If we are interested in the index of the array forEach is preferable to for of loop. 
1. for of
```
 for (const number of numbers){} 
```
2. forEach
```
 numbers.forEach((number,i)){}
```
3. for in - useful for objects literals to get keys of the object.
```
 for (const key in user){}
```

* The scope let and const is the same. The difference is only reassigning. We can not change or reassign the value of const variable. 
* let and const scope is block (function, loop, if), whereas var scope is
  functional.

## Objects
* object is a key value pair.
* Can be accessed by . or square bracket and a quote.
* copy an object
```
 const copyObj = Object.assign({},obj)
```

## Functions
### Unlimited number of parameters in regular function

* A function declaration provides a function scoped arguments array like object. Any thing we passed as argument in the function can be accessed from arguments object inside the functions. Let us see an example
```
  function sumAllNums() {
   console.log(arguments)
  }
```
* In arrow function
```
 const sumAllNums = (...args) => {}
```
* **Note** Arrow functions automatically performs context binding, so explicit bind is not required. 
* Otherwise this has windows scope in non-strict mode and undefined in strict
  mode.

* Anonymous function or without a name
```
 anonymousFunc = function() {}
```
* Expression functions are anonymous functions. After we create a function
  without a name and we assign it to a variable. 
```
 const square = function(n) {}
```
* self invoking functions, which don't need to be called to return a value.

###  Arrow function
* Arrow function is an alternative to writing a function with some minor
  differences.
```
 const square = (n) => {}
```
* If function only have return statement, we can write it as
```
 const printFullName = (First, Last) => '${First} ${Last}'
```

* Function with default parameter
```
 function name (param = value) {}
```
### Higher order functions
* functions which take other function as a parameter or return a function as
  a value.
* Callback is a function, which can be passed as parameter to other function.
* Returning function: return function as a value
```
 let sum = 0
 const callback = function(element){ sum += element }
 arr.forEach(callback)
```
### Destructuring and Spreading
* It is a way to unpack array and objects and assign to a distinct variable.
```
 const [num1, n2, n3] = [1,2,3]
const countries = [
  ['Finland', 'Helsinki'],
  ['Sweden', 'Stockholm'],
  ['Norway', 'Oslo'],
]

for (const [country, city] of countries) {
  console.log(country, city)
}
```
* Object destructuring
```
const rectangle = {
  width: 20,
  height: 10,
}

let { width, height, perimeter = 200 } = rectangle
```
### Functional Programming
1. forEach
```
 const callback = (item, i, arr) => {}
 array.forEach(callback)
```
2. map: one on one mapping
* We use map method with array and return an array
```
const countries = ['Finland', 'Estonia', 'Sweden', 'Norway']
const newCountries = countries.map((country) => country.toUpperCase())
```
3. filter: returned array is equal or less
```
 const numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
 const evens = numbers.filter((n) => n % 2 === 0)
```
4. reduce: returns a single value
```
 const value = numbers.reduce((acc, cur) => acc * cur)
```
5. find: find first occurrence of an item or element
```
 const firstEvenNum = numbers.find((n) => n % 2 === 0)
```
6. findIndex
```
 const firstEvenIndex = numbers.findIndex((n) => n % 2 === 0)
```
7. some: if one or some of the items satisfy the criteria, it returns true
   otherwise false.
```
 const someAreEvens = numbers.some((n) => n % 2 === 0)
```
8. every: every item satisfy the criteria.
```
 const allAreEvens = numbers.every((n) => n % 2 === 0)
```

## Class
* **Static Method** These are called by the class and doesn't require to create
  and instance.
* getter and setters: There is no difference between normal method and getter
  and setters in functionality. These are for understanding and readability.
```
 get getScore() {}
 set setScore() {}
```

### Inheritance
* Using inheritance we can access all the properties and methods of parent
  class.
```
 class Student extends Person {}
```
### Overriding methods
* add additional properties and functionality
```
class Student extends Person {
  constructor(firstName, lastName, age, country, city, gender) {
    super(firstName, lastName, age, country, city)
    this.gender = gender
  }
}
```

# Day 2
[Dummy Data Generator](https://www.30daysofreact.com/dummy-data)

# Day 3
```
// math.js
export const addTwo = (a, b) => a + b
export const multiply = (a, b) => a * b
export const subtract = (a, b) => a - b

export default (function doSomeMath() {
  return {
    addTwo,
    multiply,
    subtract,
  }
})()
```
Import
```
// index.js
// to import the doSomeMath from the math.js with or without extension
import doSomeMath from './math.js'

// to import the other modules
// since these modules were not exported as default we have to desctructure
import { addTwo, multiply, subtract } from './math.js'

import * as everything from './math.js' // to import everything remaining
console.log(addTwo(5, 5))
console.log(doSomeMath.addTwo(5, 5))
console.log(everything)
```

* **Package** is a module of collection of modules e.g React, ReactDOM

* creating a new application
```
 npx create-react-app
```
* start the application
```
 npm start
```

## Component
* components name starts with PascalCase. Words start with capital letter.
* JSX element
```
const header = (<header><h1>Welcome</h1></header>)
```
* React component
```
const Header = () => { return header }
const Header = () => { return (<header><h1>Welcome</h1></header>)}
or
const Header = () => ( <header><h1>Welcome</h1></header>)
```

* Calling JSX element we use curly brackets
```
 {header}
```
* Calling component and passing attribute as follows
```
 <ComponentName propsName={'data-type'}/>
```
* CSS properties uses camelCase. Number without unit is considered as px in
  CSS.
## Props
* Array props mapping
```
 const skillList = props.skills.map((skill) => <li>{skill}</li>)
```
* Boolean props
```
 let status = props.status ? 'Old enough to drive' : 'Too young for driving'
```
* Function inside curly brackets
```
 <Button text='Say Hi' onClick={() => alert('Hi')} />
```
* In React, handlers are in camelCase. For instance onClick, onMouseOver, onKeyPress etc.
### Destructuring Props
1. Step by step destructuring
```
  const data = props.data
  const { welcome, title, subtitle, author, date } = data
  const { firstName, lastName } = author
```
2. Destructuring in one line
```
  const data = props.data
  const {
    welcome,
    title,
    subtitle,
    author: { firstName, lastName },
    date,
  } = data
````
3. Destructuring the props inside the parenthesis
```
const Header = ({
  data: {
    welcome,
    title,
    subtitle,
    author: { firstName, lastName },
    date,
  },
}) => {}
```
* **propTypes** package helps us to assign the data types of the props passed
  to a component.
* **defaultProps** can be used when we want to have some default props types
  for a component.

# Day 7
## Mapping Arrays
### Mapping Array of numbers
```
 const list = numbers.map((number) => <li>{number}</li>)
```
### Mapping Array of arrays
```
 const Skill = ({ skill: [tech, level] }) => (
   <li>
     {tech} {level}
   </li>
 )
```
### Mapping array of objects
```
 const countryList = countries.map((country) => <Country country={country} />)

 const Country = ({ country: { name, city } }) => {
   return (
     <div>
       <h1>{name}</h1>
       <small>{city}</small>
     </div>
   )
 }
```
### Keys in Mapping
* Key is a unique identifier given to an element inside an array.
```
 const list = numbers.map((num) => <li key={num}>{num}</li>)
```
# Day 7
## Class Components
* Only class base functions use to have state and life cycle methods.
* After react version 16.8.0 functional components can have state and life
  cycle using React Hooks.
* Class component is extended from React.Component and have a render function.
* It can also have constructor function.
```
class Header extends React.Component {
  constructor(props) {
    super(props)
    // the code inside the constructor run before any other code
  }
  render() {
    return (
      <header>
      </header>
  )}
}
```
* Most of the time container or parent component can be written as class
  component and others as functional or presentational component.
* Data usually flows parent to child component and it is unidirectional.
# Day 8 - States
* State is an object in react which let the component re-render when state
  changes.
* updating a state
```
 this.setState({ count: this.state.count + 1 })
```

# Day 9 - Conditional Rendering
* Conditional rendering can be done using if-else, ternary operator &&.
* Using if-else
```state = {
    loggedIn: false,
  }
  handleLogin = () => {
    this.setState({
      loggedIn: !this.state.loggedIn,
    })
  }
  let status
  let text

  if (this.state.loggedIn) {
    status = <h1>Welcome to 30 Days Of React</h1>
    text = 'Logout'
  } else {
    status = <h3>Please Login</h3>
    text = 'Login'
  }
```
* Using ternary operator
```
    let status = this.state.loggedIn ? (
      <h1>Welcome to 30 Days Of React</h1>
    ) : (
      <h3>Please Login</h3>
    )
```
* Conditionally rendering a component.
```
 const status = this.state.loggedIn ? <Welcome /> : <Login />
```
```
{!loggedIn && (
   <p>
   Please login to access more information about 30 Days Of React
   challenge
   </p>
)}
```
* Change background on interval
```
constructor() {
    super()
    this.state = {
      loggedIn: false,
      techs: ['HTML', 'CSS', 'JS'],
      message: 'Click show time or Greet people to change me',
      style: {
        backgroundColor: ''
      },
    }
    this.colors = [
      "#f27feb", "#38dbbe", "#6e1fe0", "#df2037"
    ]
    this.num = 0
  }
  componentDidMount(){
    let intervalId = setInterval(this.changeBackground, 1000)
    this.setState({ intervalId: intervalId })
  }

  componentWillUnmount(){
    clearInterval(this.state.intervalId)
  }
  changeBackground = () => {
    this.num +=1
    this.setState({ style:{backgroundColor:this.colors[this.num%4]}})
  }
}
return (
    <div className='app' style={this.state.style}>
)
```
# Day 10 -  React Project Folder Structure
* There are various folder structures to follow, but stick to the one that make
  sense to you.
* FileNaming: use PascalCase file name for all components
* Folder: 
1. assets => images, icons, fonts
2. styles => CSS
3. components
* importing/exporting a component
```
// src/App.js
import React from 'react

// named export in arrow function
export const App = () => <h1>Welcome to 30 Days Of React</h1>
```
or
```
// src/App.js
import React from 'react
// named export in regular function, function declaration
export function App () {
return <h1>Welcome to 30 Days Of React</h1>
}
```
```
// index.js
import React from 'react'
import ReactDOM from 'react-dom'
import { App } from './App'

const rootElement = document.getElementById('root')
ReactDOM.render(<App />, rootElement)
```
* Exporting as default
```
export default function App () {
  return <h1>Welcome to 30 Days Of React</h1>
}
```
const App = () => <h1>Welcome to 30 Days Of React</h1>
export default App
```
```
import App from './App'
```
* Components structure
```
src
  App.js
  index.js
  components
   -auth
    -Signup.js
    -Signin.js
    -Forgotpassword.js
    -Resetpassord.js
  header
   -Header.js
  footer
   -Footer.js
  assets
   -images
   -icnons
   - fonts
  styles
   -button.js
   -button.scss
 utils
  -random-id.js
  -display-time.js
  -generate-color.js
 shared
  -Button.js
  -InputField.js
  -TextAreaField.js
```
## Fragments
* Fragments are a way to avoid unnecessary parent element in JSX.
```
import React, { Fragment } from 'react'
const Skills = () => {
  return (
    <Fragment>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </Fragment>
  )
}
```
or
```
import React from 'react'
const Skills = () => {
  return (
    <React.Fragment>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </React.Fragment>
  )
}
```
```
import React from 'react'

// Recommended
const Skills = () => {
  return (
    <>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </>
  )
}
```
# Day 11 - Events
* An event is an action recognized by a software.
* React events are named using camelCase
* with JSX you pass a function as the event handler, rather than a string.
```
import React from 'react'
// if it is functional components
const App = () => {
  const greetPeople = () => {
    alert('Welcome to 30 Days Of React Challenge')
  }
  return <button onClick={greetPeople}> </button>
}
``` 
``` 
import React, { Component } from 'react'
// if it is functional components
class App extends Component {
  greetPeople = () => {
    alert('Welcome to 30 Days Of React Challenge')
  }
  render() {
    return <button onClick={this.greetPeople}> </button>
  }
}
``` 
* In react you must call preventDefault expilitly.
* These events can be used: onMouseMove, onMouseEnter, onMouseLeave, onMouseOut, onClick, onKeyDown, onKeyPress, onKeyUp, onCopy, onCut, onDrag, onChange,onBlur,onInput, onSubmit
```
// triggered whenever the mouse moves
  handleMouseMove = (e) => {
    this.setState({ message: 'mouse is moving' })
  }

  <button onMouseMove={this.handleMouseMove}>Move mouse on me</button>
```
# Day 12 - Forms
[Reference](https://github.com/alianjum0/30-Days-Of-React/blob/master/12_Day_Forms/12_forms.md)
* Form is used to collect data from a user. Available fields in HTML5.
```
<input type="text" />
<input type="number" />
<input type="range" />

<input type="email" />
<input type="password" />
<input type="tel" />

<input type="checkbox" />
<input type="radio" />

<input type="color" />

<input type="url" />
<input type="image" />
<input type="file" />

<input type="hidden" />

<input type="date" />
<input type="datetime-local" />
<input type="month" />
<input type="week" />
<input type="time" />

<input type="reset" />
<input type="search" />
<input type="submit" />
<input type="button" />

<textarea>Please write your comment ...</textarea>

<select name="country">
  <option value="">Select your country</option>
  <option value="finland">Finland</option>
  <option value="sweden">Sweden</option>
  <option value="denmark">Denmark</option>
  <option value="norway">Norway</option>
  <option value="iceland">Iceland</option>
</select>
```
* To get data from input field onChange event and state is used on a controlled
  input.
* Input element has many attributes: value, name, id, placeholder, type and event handler.
* We can link a label and an input field using an id of input field and htmlFor of the label.If label and input are linked it will focus the input when we click on label.
```
import React, { Component } from 'react'
import ReactDOM from 'react-dom'

class App extends Component {
  // declaring state
  // initial state
  state = {
    firstName: '',
  }
  handleChange = (e) => {
    const value = e.target.value
    this.setState({ firstName: value })
  }

  render() {
    /*
     accessing the state value and 
     this value will injected to the input in the value attribute
     */

    const firstName = this.state.firstName
    return (
      <div className='App'>
        <label htmlFor='firstName'>First Name: </label>
        <input
          type='text'
          id='firstName'
          name='firstName'
          placeholder='First Name'
          value={firstName}
          onChange={this.handleChange}
        />
        <h1>{this.state.firstName}</h1>
      </div>
    )
  }
}

const rootElement = document.getElementById('root')
ReactDOM.render(<App />, rootElement)
```
## Getting multiple input data from form
```
class App extends Component {
  state = {
      firstName: '',
  }
  
  handleChange = (e) => {
      const { name, value } = e.target
      this.setState({ [name]: value })
    }
  handleSubmit = (e) => {
      e.preventDefault()
  
      console.log(this.state)
    }
  
  render() {
    // accessing the state value by destrutcturing the state
    const { firstName} = this.state
    return (
      <div className='App'>
        <h3>Add Student</h3>
        <form onSubmit={this.handleSubmit}>
          <div>
            <input
              type='text'
              name='firstName'
              placeholder='First Name'
              value={firstName}
              onChange={this.handleChange}
            />
          </div>
         <button class='btn btn-success'>Submit</button>
        </form>
      </div>
    )
  }
}
```
## Validation
[Source](https://github.com/alianjum0/30-Days-Of-React/blob/master/12_Day_Forms/12_forms.md)

# Day 13 - Uncontrolled Components
* Controlled inputs are recommended by React.
* But it is also possible to get uncontrolled inputs using **ref**.
```
handleSubmit = (e) => {
    e.preventDefault()
    console.log(this.firstName.current.value)
  }

render() {
    return (
      <div className='App'>
        <form onSubmit={this.handleSubmit}>
          <label htmlFor='firstName'>First Name: </label>
          <input
            type='text'
            id='firstName'
            name='firstName'
            placeholder='First Name'
            ref={this.firstName}
          />
          <button type='submit'>Submit</button>
        </form>
      </div>
    )
  }
```
# Day 14 - Components Life Cycle
[Source](https://github.com/alianjum0/30-Days-Of-React/blob/master/14_Day_Component_Life_Cycles/14_component_life_cycles.md)
* Component has three main phases
1. Mounting: constructor(), static getDerivedSateFromProps(), render(),
   componentDidMount()
* Now a days we can class based component without a constructor and can write
  the state outside the constructor, previously the state is used always inside
the constructor.
* The constructor get parapemeters using props and super method has to be
  called.
* getDerivedSateFromProps method is called right before rendering the
  component. This is the right place to set state object based on initial
props.
* render method is called whenever there is a change in the state.
* ComponentDidMount is called after component is render. This is the right
  place to set time intervals and calling API.
* API call and setTimeout example. 
* Sometimes it's better to have seperate method to render the data.
2. Updating: static getDerivedSateFromProps, shouldComponentUpdate, render,
   getSnapshotBeforeUpdate, componentDidUpdate
* An update of component can called when props or state is changed.
* shouldComponentUpdate returns a boolean, if false the application will not
  update.
* componentDidUpdate is called when component is updated.
3. Unmounting: componentWillUnmount
* componentWillUnmount is called when componet is unmounted.

# Day 15 - Third Party Packages
[Source](https://github.com/alianjum0/30-Days-Of-React/blob/master/15_Third_Party_Packages/15_third_party_packages.md)
* Either npm or yarn can be used to install packages.
* recommend not to use both in one application.
## node-sass
* CSS preprocess which allows to write CSS function, nesting and many more.
```
/* ./styles/header.scss */
header {
  background-color: #61dbfb;
  padding: 25;
  padding: 10px;
  margin: 0;
}

// Header.js
import React from 'react'
import './styles/header.scss
const Header = () = (
   <header>
          <div className='header-wrapper'>
            <h1>30 Days Of React</h1>
            <h2>Getting Started React</h2>
            <h3>JavaScript Library</h3>
            <p>Instructor: Asabeneh Yetayeh</p>
            <small>Oct 15, 2020</small>
          </div>
        </header>
)

export default Header
```
* CSS modules can be used in React. naming convension test.module.css or
  test.module.scss
## axios 
* JavaScript library to make HTTP requests to fetch data.
* GET, POST, PUT, PATCH, DELETE
* we can use axios with await and async functions. Then we have to handle error
  using try and catch.
## react-icons
* to get different SVG icons
## moment
* Gives different time format.
## styled-components
* It uses tagged template literals to style a component.
* This means when you are defining your styles, you are actually creating
  a normal React component.
## reactstrap
* allows to use a component with bootstrap
## lodash
* A modern JavaScript utility library deliverign modularity, performance
  & extra.

# Day 16 - Higher Order Components
* Takes a component and returns another component same as higher order
  functions in JavaScript.
```
// One way of writing a Higher Order Component(HOC)
import React from 'react'
const higherOrderComponent = (Component) => {
  return (props) => {
    return <Component {...props} />
  }
}
```
* Most of the time third party use higher order function e.g redux,
  react-router-dom and material-ui

# Day 17 - React Router
* React router is a component which allows to navigate between React
  components.
* React Router 5 is the latest version.
* this code is of versio  4.
* components in react-router-dom: BrowserRouter, Route, NavLink, Switch,
  Redirect, Prompt, withRouter
## BrowserRouter
* It is a parent component which allows to wrap the application.
* browser history can be accessed using this.
* sometimes it can renames as router.
* after wrapping application with BrowseRouter, it works smoothly as it used to
  be.
```
 import { BrowserRouter as Router } from 'react-router-dom'
```
## Route
* It allows to navigate between component. It requires two props: path and
  component to render.
```
import { BrowserRouter as Router, Route } from 'react-router-dom'

class App extends Component {
  render() {
    return (
      <Router>
        <div className='App'>
          <Route path='/' component={Home} />
        </div>
      </Router>
    )
  }
}
```
* Because / will always take to home. To make /about go to about
  page use exact. or we can rearrange to put home at the end.
```
 <Route exact path='/about' component={About} />
```
* If we don't want slash at the end /about/. We can use strick attribute in
  addition to exact.
```
 <Route exact strict path='/about' component={About} />
```
## Switch
* It allows only on component to render.
* with switch if it finds first matching route, it will stop looking and
  render. Otherwise it will render all matching components.
## NavLink
* It allows to navigate without refreshing.
```
 <NavLink to='/'>Home</NavLink>
```
* routes and navigation works perfectly if it founds the route otherwise it
  falls to the last component. This can be solved using NotFound component.
```
 <Route component={NotFound} />
```

## Nesting Routing
* It is possible to have nesting routes.
```
const Challenges = (props) => {
  const path = props.location.pathname
  const slug = path.split('/').slice(path.split('/').length - 1)[0]
  const challenge = challenges.find((challenge) => challenge.slug === slug)

  return (
    <div>
      <h1>30 Days Of React Challenge</h1>
      <ul>
        {challenges.map(({ name, slug }) => (
          <li>
            <NavLink to={`/challenges/${slug}`}>{name}</NavLink>
          </li>
        ))}
      </ul>
      <Switch>
        <Route
          exact
          path={'/challenges'}
          component={() => <h1>Choose any of the challenges</h1>}
        />
        <Route
          path={path}
          component={(props) => <Challenge challenge={challenge} />}
        />
      </Switch>
    </div>
  )
}
```
## Redirect
* Redirect to a route to a cetain path based on codition. e.g in case user is
  not logged in, redirect to login.
```
<Route
  path='/challenges'
  component={(props) => {
    return this.state.isLoggedIn ? (
      <Challenges {...props} />
    ) : (
      <Redirect to='/user/asabeneh' />
    )
  }}
/>
```
## Prompt
* prompt component is used ask user to confirm before leaving the page.
```
 <Prompt message='Are you sure you want to leave?' />
```
# Day 18 - Fetch and Axios
[Source](https://github.com/alianjum0/30-Days-Of-React/blob/master/18_Fetch_And_Axios/18_fetch_axios.md)
## Fetch
* It is provided by JavaScript but is not supported by all browsers. So it
  requires additional packages. Whereas axios doesn't require extra packages.
```
componentDidMount() {
    const url = 'https://restcountries.eu/rest/v2/all'
    fetch(url)
      .then((response) => {
        return response.json()
      })
      .then((data) => {
        console.log(data)
        this.setState({
          data,
        })
      })
      .catch((error) => {
        console.log(error)
      })
  }
```
* We can use it with async and await.
```
fetchCountryData = async () => {
    const url = 'https://restcountries.eu/rest/v2/all'
    try {
      const response = await fetch(url)
      const data = await response.json()
      this.setState({
        data,
      })
    } catch (error) {
      console.log(error)
    }
  }
```
## Axios
* It needs to be installed using npm.
````
 componentDidMount() {
    const url = 'https://restcountries.eu/rest/v2/all'
    axios
      .get(url)
      .then((response) => {
        this.setState({
          data: response.data,
        })
      })
      .catch((error) => {
        console.log(error)
      })
  }
````
* with awaint and async
````
fetchCountryData = async () => {
    const url = 'https://restcountries.eu/rest/v2/all'
    try {
      const response = await axios.get(url)
      const data = await response.data
      this.setState({
        data,
      })
    } catch (error) {
      console.log(error)
    }
  }
````
# Day 21 - Introducing React Hooks
[Source](https://github.com/alianjum0/30-Days-Of-React/blob/master/21_Introducing_Hooks/21_introducing_hooks.md)
*  hooks are introduced in react 16.8
## Basic Hooks
* useState, useEffect, useContext
* useState allow to access state without a class based component.
```
 const [count, setCount] = useState(0)
```

* then update using setCount
```
 <button onClick={() => setCount(count + 1)}>Add One</button>
```
* we can use multiple variable in useState as follow
```
const [count, setCount] = useState(0)
const [backgroundColor, setBackgroundColor] = useState('')
```
# From Video
* In JavaScript ES2015 syntax can be written as
```
let name = 'King'
let age = 55
let data = { name, age }
or 
let data = {
  name: name,
  age: age
}
```
 
