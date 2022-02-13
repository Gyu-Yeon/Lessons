# Lessons 

## 1. How to make server in Node.js

- write npm install express in your terminal( ` + ctrl)
- make a new js file name server.js and write this on the top of file.
  <br> const express = require("express");
  <br> const app = express();
- and write app.listen to connect to port you want.
  <br> ex)
  <br> app.listen("8080", function () {
  <br> console.log("listening on 8080");
  <br> });
- write node server.js in your terminal.
- open any browser and go to localhost:8080
- if the page says cannot get / you are ready to start.

  2022.01.15

## 2. How to send delete request to server from HTML.

- first you need jquery cdn or jqeury script file.
- write the ajax method between script tag.
  <br> ex)
  <br> < script >
  <br> $.ajax({
  <br> method: "DELET",
  <br> url: '/delete',
  <br> data; { \_id: e.target.dataset.id}  
  <br> }).done(function() {
  <br> $( this ).addClass( "done" );
  <br> });
  <br> < script >
- for data write down what you want to send to server with ajax request.
- for url write down the path that this request will run.
- for method choose the kind of request you want to send.

  2022.01.16

## 3. How to make Login function.

- npm install passport passport-local express-session
- const passport = require('passport');
  <br> const LocalStrategy = require('passport-local').Strategy;
  <br> const session = require('express-session');
  <br> app.use(session({secret : 'secretCode', resave : true, saveUninitialized: false}));
  <br> app.use(passport.initialize());
  <br> app.use(passport.session());
- app.get('/login', function(req, res){
  <br> req.render('login.ejs')
  <br>});

  2022.01.17

## 4. import / export in JSX

- when you want to use important valialbe in another file.
- write 'export default' next to variable that you want to use it in another file.
  <br> ex) let data = [1,2,3]
  <br> export default data
- more than 2 or more valiables to use in another file.
- write export next to variables with { }
  <br> ex) let data1 = 1 , let data2 = 2
  <br> export {data1, data2}
- on import file, write 'import ()' from './(route of the file) on the top of the file,
  <br> ex) import (name it whatever you want) from './data.js';
  <br> ex) import {data1, data2 } from './data.js

## 5. How to use for loop in JSX

- Using for loop in JSX it is complicate, so we use 'map' method
- if you like to use 'map' method first, you need any useState that stores array.
- write 'map' inside of { },
  <br> ex) { title.map(()=>{return( hello World)})
- if it works properly, you'll get title.length of hello worlds.
- same as JS map method, you can put any letter as a parameter.
  <br> ex) title.map((a)=>{ return ( ) })
- In JSX you need 'i' for increasing number.
  <br> ex) title.map((a,i)=>{ return ( key={ i } ) })

  2022.01.20

## 6. How to Routing in JSX

- npm install react-router-dom@5 write this in your terminal and download router library
- go to your index.js file and write import { BrowserRouter } from "react-router-dom" top of the file and,
  <br> cover < App /> components with < BrowserRouter >
  <br> ex)
  <br> < BrowserRouter >
  <br> < App />
  <br> </ BrowserRouter >
- Next, go to App.js file and write import { Link, Route, Switch } from "react-router-dom" top of the file.
- Cover any components that you want to make as a route with < Route > tag.
  <br> ex)
  <br> < Route >
  <br> < div > hello World </ div >
  <br> </ Route >
- write the path inside of tag
  <br> ex)
  <br> < Route path = { " / " >
  <br> < div > hello World </ div >
  <br> </ Route >

  2022.01.25

## 7. How to make 1000's of pages by using URL parmeter

- write ' import { useParams } from "react-router-dom" ' on the top of the file that you are going to use URL parameter.
- write ex) inside of return ( )
  <br> ex) let id =useParams();
- wherever you write id, { id' num } will remain after 'id'
  <br> ex) if the URL is localhost:3000/detail/1
  <br> props.shoes[id].title =>
  <br> props.shoes[1].title

  2022.01.27

## 8. How to use ajax in JSX

- write 'npm install axios in your terminal.
- write import axios from "axios" on the top of the file that you are going to use axios.
- choose when to use, ex) onClick, useEffect.
- how to send get request to sever by using axois
  <br> ex)
  <br> onClick={() => {
  <br> axios
  <br> .get(" https://codingapple1.github.io/shop/data2.json")
  <br> .then(result => {
  <br> console.log(result.data);
  <br> shoes변경([...shoes, ...result.data]);
  <br> })
  <br> .catch(() => {
  <br> console.log("fail");
  <br> });
  <br> }}

## 10. useEffect

- useEffect is activate when the page is loaded.
- If you use this function with useState, useEffect will activate whenever useState is changing.
- First write import React, { useEffect, useState } from "react"; on the top of relevant file.
- How to make useEffect
  <br>ex)
  <br> let [show, showChange] = useState(true);
  <br> useEffect(() => {
  <br> let timer = setTimeout(() => {
  <br> showChange(false);
  <br> }, 2000);
  <br> return () => {
  <br> clearTimeout(timer);
  <br> };
  <br> });
- after load this page, 2secs later 'show' will turn in to false and the div that display it by
  <br> changing status of show, will disappear.

  2022.01.28

## 11. how to send data from main component to nested component

- first you need 3 or more components.
- inside of main components, make a components that has another components inside of it.
  <br> ex)
  <br>-----------Component1
  <br>---------Component2
  <br> ------Component3
- send data from Component1 to Component2 by using props.
  <br> ex)
  <br> < Detail shoes={shoes} /> 
  <br> function Detail(props) {
  <br> return (
  <br> < h2 > {props.shoes} </ h2 >
  <br> < Info />
  <br> )}
- send data from Component2 to Component3 by using same method.
  <br> ex)
  <br> function Info(props) {
  <br> return < p > 재고: {props.left[0]} </ p >
  <br> }
  <br> < Info left={props.left} />
  
  
    2022.02.02
