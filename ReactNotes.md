# React and Redux
[Udemy](https://www.udemy.com/course/react-redux/)

## Lets dive in
### Our first app
* App to translate from English to any language using API.
* codesandbox.io online editor for this app.
* In return we have html which will be displayed.
### Critical questions
* app function is a react component. Plain java script function which return some JSX.
* Component has two jobs. Produce JSX and handle user events.
* JSX is set of instruction tell react what we want show at any given time.
Self closing tag
> <hr />
* JSX can have a HTML element or another component.
JSX example
```
    <div>
        <Field label="Enter English" onChange={setText} value={text} />
        <Languages language={language} onLanguageChange={setLanguage} />
        <hr />
        <Translate text={text} language={language}/>
    </div>
```
* React check if dom element or component. If DOM element show other wise go to component and repeat.
* React loading
1. load index.html
2. executes index.js file automatically. 
3. ReactDOM.render is called on root element and load html from APP component.
* React/reconsiler knows how to work with components 
* ReactDOM/renderer knows how to take instructions on what we want to show and turn it into HTML.
* useState is for managing data that needs to be changed over time and updates the HTML on screen.
### Installing NodeJS
* npx is a command line tool which is present with npm with version greater than 5.0.
> npx create-react-app my-app
### Why create react app
* Java script has varios version ES5 and every year after 2015 to 2019 it has newer version with new features.
* Almost all browsers have ES5 support but not many have latest JavaScript support.
* Many packages were installed to create react app, one is babel.
* Babel changes latest version of JS code to previous version to make it compatible.
* Babel is internally dependent on various other packages.
### Exploring a Create-React-App project
* src: source code
* public: static files
* node_modules: dependencies
* package.json: project dependencies and configurations
* package-lock.json: version of dependencies installed
* .gitignore: ignore files
### Starting and Stopping a React App
> npm start
* ctrl-c to stop
### JavaScript module system
* import is used for loading form files or dependencies.
* import is used by ES2015 module system where as require is used by CommonJS module system.
### Displaying Content with Functional Components
* function based component
```
const App = () => {
	return <div> Hey </div>
};
ReactDOM.render(
	<App />,
	document.querySeletor('#root')
);
```
# JSX
* JSX is converted into function calls by react so Babel can convert it to JavaScript.
* can test it at babeljs.io
* JSX is easy to read and understand.
### Converting HTML to JSX
opening line of JSX is on same line as JSX otherwise it will return empty.
* normal convension is to close it in parenthesis.
### JSX vs HTML
1. adding custom styling to an element.
> style="background-color:red" => style={{backgroundColor: 'red'}} javascript object
* non-JSX properties use " quotes for JSX properties and single quotes everywhere else.
2. Adding a class to an element
> class="label" => className="label"
* To avoid confusion with component class
3. JSX can reference javascript variable
> {buttonText} javascript variable
* javascipt valiable can be string, variable or array but not javacript object
> const buttonText= {text: 'click me'} error
* can reference object in properties but not to print
> const style= {backgroundColor: 'blue', color:'white'};
> style ={style} OK
* other warnings can be seen in console
* semantics-ui css file for styles from cdnjs
* faker package for fake images
### Creating a reusable, configurable component
1. identify JSX that appears to be duplicate
2. create new file and component with the name of the component e.g CommentDetail
3. make it configurable by using react's 'props' system.

* export and import a component
> export default CommentDetail

> import CommentDetail from './CommentDetail'
* it will automatically add .js at the end to search
### React props system
* props(properties) is a system to pass data from a parent component to a child component.
* Goal is to compile and configure a child component.

* props.children get what's inside JSX component.

* Two types of components in React
1. Functional: Can produce JSX to show content
2. Class: Can produce JSX to show content, Can use life cycle method system to run code at different point in time, Can use state to update 



[reactnotes_github](https://github.com/fpereiro/reactnotes)

It is crucial to understand that this.props and this.state are distinct objects, despite both being objects that hold state and affect the components. this.props is used to pass data from a component to its children, whereas this.state is used to hold state that changes over time and belongs to the component itself.

Internally, when this.setState is invoked, the component (and its children) are updated automatically.

To share state between a parent component and its child, or among child components at the same level, said state must be created and held by the parent component. The parent component can then pass this state to the children.

If a child element must modify the state of the parent, this is done by passing a function to modify the parent's state. This function is passed from the parent to the child element, so it must be defined on the parent element.

Notice how Square now defines a function handleClick. We then pass handleClick as an attribute to Square (also named handleClick). Then, in Square, we associate the onClick property with a function invocation that calls this.props.handleClick; effectively invoking the function passed by Board to Square.

React recommends to create copies of the state, instead of modifying it directly. This is why we created a copy of squares before updating the Board's state.

Since Square no longer holds state, we can rewrite it as a functional component. A functional component only takes props as input and returns what should be rendered.

Notice how we changed this.props to props and how we got rid of the render method, instead directly returning JSX. The component can be further simplified as regards onClick/handleClick:


