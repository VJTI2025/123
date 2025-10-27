Exp2
<html>
<head></head>
<body></body>
<script>
function norm1(){ console.log("normal function without return without parametter");}
function norm2(a,b){ console.log("normal function without return with parametter:"+a+b);}
function norm3(){ return "normal function with return without parametter";}
function norm4(a,b){ return "normal function with return with parametter:"+a+b;}
norm1();
norm2(2,3);
console.log(norm3());
console.log(norm4(4,5));
let anoy1= function(){ console.log("anonymous function without return without parametter")}
let anoy2= function(a,b){ console.log("anonymous function without return with
parametter:"+(a-b))}
let anoy3= function(){ return "anonymous function with return without parametter"}
let anoy4= function(a,b){ return "anonymous function with return with parametter:"+(a*b)}
anoy1();
anoy2(2,3);
console.log(anoy3());
console.log(anoy4(4,5));
let a1= ()=>{ console.log("arrow function without return without parametter")}
let a2= (a,b)=>{ console.log("arrow function without return with parametter:"+(a+b))}
let a3= ()=>{ return "arrow function with return without parametter"}
let a4= (a,b)=>{ return "arrow function with return with parametter:"+(a-b)}
a1();
a2(2,3);
console.log(a3());
console.log(a4(4,5));
</script>
</html>
Exp3
With constructor
<script>
class Student{
constructor(n,a){
this.name=n;
this.age=a;
}
details(){
return ("Your Name is "+ this.name+" of Age " +this.age);
}
}
class IT extends Student{
constructor(n,a,m){
super(n,a);
this.marks=m;
}
Marksheet(){
if(this.marks>32 && this.marks<100 ){
console.log(${super.details()} is ELIGIBLE FOR PLACEMENT); }
else{
console.log(${super.details()} is NOT ELIGIBLE FOR PLACEMENT);}
}
}
var T1 = new IT("Rajiv"
,20,35)
T1.Marksheet();
</script>
Without constructor
<script>
class Student {
setDetails(n, a) {
this.name = n;
this.age = a;
}
details() {
return "Your Name is " + this.name + " of Age " + this.age;
}
}
class IT extends Student {
setMarks(m) {
this.marks = m;
}
Marksheet() {
if (this.marks > 32 && this.marks < 100) {
console.log(${super.details()} is ELIGIBLE FOR PLACEMENT);
} else {
console.log(${super.details()} is NOT ELIGIBLE FOR PLACEMENT);
}
}
}
var T1 = new IT();
T1.setDetails("Rajiv"
, 20);
T1.setMarks(35);
</script>
Exp4 promise
<html>
<head>
<title>
Promise
</title>
</head>
<body>
<script>
let p=80
var pro=new Promise((res, rej)=>{
if(p>60)
{
res("it is resolved");
}else{
rej("it is not resolved");
}
});
pro.then((result)=>{
console.log(result);
});
pro.catch((error)=>{
console.log(error);
});
</script>
</html>
Exp 5 fetch
<script>
fetch("https://dummyjson.com/users")
.then((respond)=>{
return respond.json();
})
.then((result)=>{
console.log(`${result.users[2].firstName}`);
})
.catch((error)=>{
console.log(error);
})
</script>
<script>
var name = prompt('Your first name');
var last = prompt('Your last name');
fetch('https://dummyjson.com/posts/add'
,{
method: 'POST'
,
headers: { 'Content-Type': 'application/json' },
body: JSON.stringify({ userId:1, firstName: name, lastName: last })
})
.then(response => response.json())
.then(data => console.log("Posted:"
, data))
.catch(error => console.error("Error:"
, error));
</script>
fetch("data.txt")
.then(response => {
if (!response.ok) {
throw new Error("File not found");
}
return response.text();
})
.then(data => {
console.log("Local file content:"
, data);
})
.catch(error => {
console.error("Error fetching local file:"
, error);
});
Exp6
Exp6.jsx
import React from 'react';
export default function HelloWorld() {
return (
<div>
<h1>Hello, World!</h1>
<p>This is a simple JSX component made by Prachi.
</p>
</div>
);
}
index.js
import React from 'react';
import ReactDOM from 'react-dom/client';
import '
./index.css';
import App from '
./App';
import reportWebVitals from '
./reportWebVitals';
import HelloWorld from '
./exp7';
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
<div>
<HelloWorld>
</HelloWorld>
</div>
);
// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();
Exp7
Newclass.jsx
import React from "react";
class Newclass extends
React.Component{
render(){
return(
<div>
<h1> This is Class
Component</h1>
</div>
)
}
}
export default Newclass
Newfun.jsx
import React from "react";
function Newfun() {
return(
<div>
<h1> This is function
Component</h1>
</div>
)
}
export default Newfun
index.js
import React from 'react';
import ReactDOM from 'react-dom/client';
import '
./index.css';
import App from '
./App';
import reportWebVitals from '
./reportWebVitals';
import HelloWorld from '
./exp7';
import Newclass from '
./Newclass';
import Newfun from '
./Newfun';
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
<div>
<Newclass></Newclass>
<Newfun></Newfun>
</div>
);
Exp8
import React, { Component } from "react";
export default class State extends Component {
constructor(props) {
super(props);
this.state = {
count: 0
};
}
Increment = () => {
this.setState({ count: this.state.count + 1 });
};
render() {
return (
<div>
<h1>
</h1>
</div>
{this.props.name} has clicked this Button {this.state.count} Times
<button onClick={this.Increment}>Click Here</button>
);
}
}
index.js
import React from 'react';
import ReactDOM from 'react-dom/client';
import '
./index.css';
import App from '
./App';
import reportWebVitals from '
./reportWebVitals';
import State from '
./State';
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
<div>
<State name="Prachi">
</State>
</div>
);
Exp9
import React from "react";
import {BrowserRouter as Router,Link,Routes,Route } from "react-router-dom"
import State from "
./State";
export default class Exp9 extends React.Component{
render(){
return(
<Router>
<ul>
<li><Link to='/'>Home</Link></li>
<li><Link to='/about'>About Us</Link></li>
</ul>
<Routes>
<Route path='/about' element={<State />} />
</Routes>
</Router>)}}
index.js
import React from 'react';
import ReactDOM from 'react-dom/client';
import '
./index.css';
import App from '
./App';
import reportWebVitals from '
./reportWebVitals';
import Exp9 from '
./exp9';
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
<div>
<Exp9>
</Exp9>
</div>
);
