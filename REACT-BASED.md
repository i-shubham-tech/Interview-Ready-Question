what is reactjs

React js is javascript library that used to build fast and interactive UI especially on single page application 
It uses component based architecture where ui divided into small, reusable component 
It internal uses virtual dom to improve performance by update content that actually changes

what is spa

single page application is a web application where only one html page is loaded intially
After that application dynamically update content without loading page
It provide fast and smooth experience 

what is virtual dom 

virtual dom is a light weight copy of real dom.when application state change then it first update virtual dom instead of real dom.Then compare update virtual dom with previous one and find difference.Then  only changes part are update in real dom which improve performance 

what is jsx

JSX stand for javascript XML
IT allows to write html code inside javascript 
JSX code is not understand by browser so is transpilled into regular javascript using tool babel

what is component 
Component is a self contained, reusable piece of code in React .it represents ui like button,form or section.
IT received data through props and each component has own state to manage data dynamically 

what is props

props used to pass data from parents component to child component 
props data is read-only that is child component cannot modify it

what is props drilling 

Props drilling is a condition in react where data is pass through multiple level of component even they do required . so that deeply nested child component can receive data

this problem is solve using context api or state management such as redux 

what is context api 

context api is the feature in react that used to share data globally across all components without passing prop manually at each level 

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
react compare update virtual dom with previous and update changes part in real dom 


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

