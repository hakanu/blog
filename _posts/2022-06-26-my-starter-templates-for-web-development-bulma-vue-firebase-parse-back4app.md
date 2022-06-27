---
published: true
layout: post
category: webdev
title: >-
  My starter templates for web development (Bulma, vue, firebase, parse,
  back4app)
---
This post is purely note to myself, I keep doing the same copy pasting every time I start a new project.

## Bulma Starter Template HTML

Source: https://bulma.io/documentation/overview/start/

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Hello Bulma!</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css">
  </head>
  <body>
  <section class="section">
    <div class="container">
      <h1 class="title">
        Hello World
      </h1>
      <p class="subtitle">
        My first website with <strong>Bulma</strong>!
      </p>
    </div>
  </section>
  </body>
</html>
```

## Bootstrap Template HTML

Source: https://getbootstrap.com/docs/5.2/examples/navbar-fixed/

```html

<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="description" content="">
    <meta name="author" content="Hakanu.net">
    <title>Fixed top navbar example · Bootstrap v5.2</title>
    <link href="/docs/5.2/dist/css/bootstrap.min.css" rel="stylesheet" crossorigin="anonymous">

        <!-- Favicons -->
    <link rel="apple-touch-icon" href="/docs/5.2/assets/img/favicons/apple-touch-icon.png" sizes="180x180">
    <link rel="icon" href="/docs/5.2/assets/img/favicons/favicon-32x32.png" sizes="32x32" type="image/png">
    <link rel="icon" href="/docs/5.2/assets/img/favicons/favicon-16x16.png" sizes="16x16" type="image/png">
    <link rel="manifest" href="/docs/5.2/assets/img/favicons/manifest.json">
    <link rel="mask-icon" href="/docs/5.2/assets/img/favicons/safari-pinned-tab.svg" color="#712cf9">
    <link rel="icon" href="/docs/5.2/assets/img/favicons/favicon.ico">
    <meta name="theme-color" content="#712cf9">
    
    <!-- Custom styles for this template -->
    <link href="navbar-top-fixed.css" rel="stylesheet">
  </head>
  <body>
    
    <nav class="navbar navbar-expand-md navbar-dark fixed-top bg-dark">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Fixed navbar</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarCollapse" aria-controls="navbarCollapse" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarCollapse">
          <ul class="navbar-nav me-auto mb-2 mb-md-0">
            <li class="nav-item">
              <a class="nav-link active" aria-current="page" href="#">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Link</a>
            </li>
            <li class="nav-item">
              <a class="nav-link disabled">Disabled</a>
            </li>
          </ul>
          <form class="d-flex" role="search">
            <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
            <button class="btn btn-outline-success" type="submit">Search</button>
          </form>
        </div>
      </div>
    </nav>

    <main class="container">
      <div class="bg-light p-5 rounded">
        <h1>Navbar example</h1>
        <p class="lead">This example is a quick exercise to illustrate how fixed to top navbar works. As you scroll, it will remain fixed to the top of your browser’s viewport.</p>
        <a class="btn btn-lg btn-primary" href="/docs/5.2/components/navbar/" role="button">View navbar docs &raquo;</a>
      </div>
    </main>
    <script src="/docs/5.2/dist/js/bootstrap.bundle.min.js" crossorigin="anonymous"></script>      
  </body>
</html>

```

## Vue.js wit bulma.css

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Hello Bulma!</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css">
  </head>
  <body>
  <section class="section">
    <div class="container">
      <h1 class="title">
        Hello World
      </h1>
      <p class="subtitle">
        My first website with <strong>Bulma</strong>!
      </p>

      <div id="app">
        <h1>{{ message }}</h1>
        <button @click="reverseMessage">Reverse Message</button>
        <button @click="message += '!'">Append "!"</button>
        <a href="https://vuejs.org" @click.prevent="notify">
          A link with e.preventDefault()
        </a>
      </div>
    </div>
  </section>

  <script src="https://unpkg.com/vue@3"></script>
  <script type="module">
    const { createApp } = Vue
    createApp({
      data() {
        return {
          message: 'Hello Vue!'
        }
      },
      methods: {
        reverseMessage() {
          this.message = this.message.split('').reverse().join('')
        },
        notify() {
          alert('navigation was prevented.')
        }
      }
    }).mount('#app')
  </script>
  </body>
</html>
```


## Parse SDK (Back4App)

Source: https://www.back4app.com/docs/javascript/parse-javascript-sdk

```html
<html>
  <head>
  </head>
  <body>
    <h1>Javascript Parse and Firebase based app</h1>
	<script type="text/javascript" src="https://npmcdn.com/parse/dist/parse.min.js"></script>
    
    <script>
      // Initialize Parse
      Parse.initialize("YOUR_PARSE_APP_ID", "YOUR_PARSE_JS_KEY");
      Parse.serverURL = "https://parseapi.back4app.com/";

      function create() {
          mypet = new Pet();
          mypet.set("name", textName);
          mypet.set("agePet", textAge);

          mypet.save().then(function(pet){
               console.log('Pet created successful with name: ' + pet.get("name") + ' and age: ' + pet.get("agePet"));
          }).catch(function(error){
               console.log('Error: ' + error.message);
          });
      }
      
      function read() {
          query = new Parse.Query(Pet);
          query.equalTo("name", textName);
          query.first().then(function(pet){
              if(pet){
                 console.log('Pet found successful with name: ' + pet.get("name") + ' and age: ' + pet.get("agePet"));
              } else {
                 console.log("Nothing found, please try again");
              }
          }).catch(function(error){
              console.log("Error: " + error.code + " " + error.message);       
          });
      }
      
      function readThenUpdate() {
          query = new Parse.Query(Pet);
          query.equalTo("name", textName);
          query.first().then(function (pet) {
            if (pet) {
              console.log('Pet found with name: ' + pet.get("name") + ' and age: ' + pet.get("agePet"));
              update(pet);
            } else {
              console.log("Nothing found, please try again");
            }
          }).catch(function (error) {
            console.log("Error: " + error.code + " " + error.message);
          });
      }
      
      create();
      read();
      readThenUpdate();
    </script>
  </body>
</html>
```

## Firebase Web & Javascript SDK


```html
<html>
  <head>
  </head>
  <body>
    <h1>Javascript Parse and Firebase based app</h1>
    
    <script type="module">
      // Import the functions you need from the SDKs you need
      import { initializeApp } from "https://www.gstatic.com/firebasejs/9.8.4/firebase-app.js";
	  import { getDatabase } from "https://www.gstatic.com/firebasejs/9.8.4/firebase-database.js";
      import { getAuth } from "https://www.gstatic.com/firebasejs/9.8.4/firebase-auth.js";
      
      // TODO: Add SDKs for Firebase products that you want to use
      // https://firebase.google.com/docs/web/setup#available-libraries

      // Find below in Project settings @ https://console.firebase.google.com/project
      // Your web app's Firebase configuration
      const firebaseConfig = {
        apiKey: "",
        authDomain: "",
        databaseURL: "",
        projectId: "",
        storageBucket: "",
        messagingSenderId: "",
        appId: ""
      };

      // Initialize Firebase
      const app = initializeApp(firebaseConfig);

      // Initialize Realtime Database and get a reference to the service
      const database = getDatabase(app);
      
      function writeUserData(userId, name, email, imageUrl) {
        const db = getDatabase();
        set(ref(db, 'users/' + userId), {
          username: name,
          email: email,
          profile_picture : imageUrl
        });
      }
      
      function readDataOnce() {
        const dbRef = ref(getDatabase());
        get(child(dbRef, `users/${userId}`)).then((snapshot) => {
          if (snapshot.exists()) {
            console.log(snapshot.val());
          } else {
            console.log("No data available");
          }
        }).catch((error) => {
          console.error(error);
        }); 
      }
      
      writeUserData('test', 'name', 'email@mail.com', 'example.jpg');
      readDataOnce();

    </script>
  </body>
</html>
```
