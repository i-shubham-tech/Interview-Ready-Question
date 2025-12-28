what is reactjs

React js is javascript library that used to build fast and interactive UI especially on single page application 
It uses component based architecture where ui divided into small, reusable component 
It internal uses virtual dom to improve performance by update on changes part in real dom
what is spa

single page application is a web application where only one html page is loaded intially
After that application dynamically update content without loading page
It provide fast and smooth experience 

what is virtual dom 

Virtual dom is a light weight copy of Real DOM.
when application state change then it first update virtual dom instead of real dom.Then compare update virtual dom with previous one and find difference.Then  only update changes part in real dom which improve performance 

what is jsx

JSX stand for javascript XML
IT allows to write html code inside javascript 
JSX code is not understand by browser so is transpilled into regular javascript using tool babel

what is component 
Component is a self contained, reusable piece of code in React .it represents ui like button,form or section.
IT received data through props and each component has own state to manage data dynamically 6

what is props

props used to pass data from parents component to child component 
props data is read-only that is child component cannot modify it

what is props drilling 

Props drilling is a condition in react where data is pass through multiple level of component even they do required . so that it reach to  deeply nested child component 
this problem is solve using context api or state management such as redux 

what is context api 

context api is the feature in react that used to make data avaliable globally so it can access across all component .It prevent from prop drilling

what is Class component and functions component 

class component is created using ES6 class and extend a react component 
It has this keyword and manage state using this.state and this.setState()
It has didcomponentmount() lifecycle method

Function component is created using simple javascript function 
It doesn't have this, State and life cycle manage using react hook use state for state and useeffect for life cycle 

what is lifecycle 

Life cycle is a different state of react component from creation to removal

It includes stages mount, update,unmount

Mount - when component create and show on the ui

update - when component re-render as state or prop changes

unmount - when component is remove from the ui 
it happens when navigate to another page or conditionallt hide

what is didComponentMount

Didcomponentmount is the lifecycle method of class . It call only once after component is mounted or render on the ui

what is state

State is the object that contain dynamic value of react compent

it represents information that frequently change such user input,form value,count,fetch data

what Happened when state change 

when state change component get re-render 
react compare update ui with previous ui using virtual and update changes part in real dom 


what happened if we directly update state value 

if we directly update state value Then component will not re-render and react will never know state has changed.Hence ui will not updated correctly 
Therefore we should use react provide setState in class component and useState in function component for state change to keep ui sync

what is difference between props and state 

props used to pass data from parents to child 
and they are readOnly

State manage data inside a component 
they are mutable can change using useState and setState 


what is condition rendering 

condition rendering is the technique used to render different ui based on condition 


What is React hook

A React Hook is a special function that allows us to use React features like state and lifecycle behavior in functional components.
Commonly used hooks include useState, useEffect, and useContext.

what is useState

useState is a React Hook used to add and manage state in functional components.
It store dynamic data of component and update the UI when that data changes.

useState returns an array which contain current state value and a function that update the state.

what is side Effect
Side effects are tasks that happen outside normal UI rendering,such as fetching data, updating the DOM, setting timers

what is useEffect

UseEffect is a react hook that used to handle side effect in function component
side effect task include api call,data fetching,timers and dom update
It run imediately after ui render
We can control it when to run using dependency array
If dependency arrray is not define that it run on each render
If empty dependency arrray is define thaan only run on first render
If dependency array contain state then run on when ever that state change

Difference between useEffect and lifecycle methods
lifeCycle method used in clas compoen   useEffect used function compo
each phase have diff method             useEffect handle all phase
For mount->CompoundDidMount()           For useEffect with empty dep array
For update compoundDidUpdate()          For useEffect with dep array contain state
for unMount compundwillUnMound()        for return () => {};

what is key

Keys in React are special attributes used to uniquely identify elements in a list so React can efficiently update only the changed items during re-rendering.

What is lifting state up?

Lifting state up means moving state from a child component to its closest common parent so that multiple components can share and stay in sync with the same data.

What is controlled vs uncontrolled component?

🔹 Controlled Component

A controlled component is a form element whose value is fully managed by React state.
React controls the input value through state and updates it using event handlers, making the state the single source of truth.

🔹 Uncontrolled Component

An uncontrolled component is a form element that manages its own state in the DOM.
React accesses the value only when needed using refs instead of controlling it through state.
