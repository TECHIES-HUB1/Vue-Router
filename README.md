# Vue-Router
How to use vue router tutorial

How to use vue-router is today’s our most important topic. VueJS is frontend Library which can be used with any backend Languages. If you do not know, how to set up VueJS development environment, then please check out my this tutorial on Vuejs Tutorial With Example

If we want to create fully functional front end application, then vue-router and vue-resource are two great pillars in VueJS. So today we will deep dive on vue-router. Routing is the way to manage the components in a Single Page Applications. All the Famous Front End Frameworks utilizes the concept of Routing.

## How to use vue-router?
    First, we need to create one project to understand the routing concepts in VueJS. We are going to see vue-router with an example.

### Step: 1 Create one project.
    Create one project. 

### mkdir VueRoute
    Go to that project and create one file called package.json. Copy the following code into the package.json file.

    {
      "name": "vuerouter",
      "version": "1.0.0",
      "description": "",
      "main": "index.js",
      "scripts": {
      "start": "webpack-dev-server"
    },
      "author": "",
      "license": "ISC",
      "devDependencies": {
      "babel-core": "^6.25.0",
      "babel-loader": "^7.1.1",
      "babel-plugin-transform-runtime": "^6.23.0",
      "babel-preset-es2015": "^6.24.1",
      "babel-preset-stage-3": "^6.24.1",
      "babel-runtime": "^6.25.0",
      "vue-loader": "^13.0.2",
      "vue-template-compiler": "^2.4.2",
      "webpack": "^3.4.1",
      "webpack-dev-server": "^2.6.1"
    },
      "dependencies": {
      "vue": "^2.4.2",
      "vue-router": "^2.7.0"
     }
    }



### Now, you need to install Node.js to work with this project. So after copying the code. Type in terminal following command.

### npm install
    It will install all the dependencies regarding Vue.js, vue-router, Webpack, ES6, Babel.

### Step 2: Make webpack.config.js file.
    Next step would be to configure our webpack.config.js file. Create one file in a root called webpack.config.js. Put the following code in that file.

    // webpack.config.js

     module.exports = {
    // This is the "main" file which should include all other modules
     entry: './src/main.js',
    // Where should the compiled file go?
     output: {
    filename: 'bundle.js'
    },
    resolve: {
     alias: {
    vue: 'vue/dist/vue.js'
    }
    },
    module: {
    // Special compilation rules
    loaders: [
      {
        // Ask webpack to check: If this file ends with .js, then apply some transforms
        test: /\.js$/,
        // Transform it with babel
        loader: 'babel-loader',
        // don't transform node_modules folder (which don't need to be compiled)
        exclude: /node_modules/
      },
      {
        // Ask webpack to check: If this file ends with .vue, then apply some transforms
        test: /\.vue$/,
        // don't transform node_modules folder (which don't need to be compiled)
        exclude: /(node_modules|bower_components)/,
        // Transform it with vue
      use: {
        loader: 'vue-loader'
        }
       }
      ]
     },
    devServer: {
       port: 3000
      }
    }
### Create one src folder and in that create one file called main.js. This file would be compiled, and with webpack, it becomes bundle.js. 

### Now create one file called in a root called index.html and put the following code in it.

    <!DOCTYPE html>
      <html>
    <head>
    <meta charset="utf-8">
    <title>VueJS Routes</title>
    </head>
    <body>
      <div id="app"></div>
      <script src="bundle.js"></script>
    </body>
    </html>
### Here, I have included final JavaScript file called bundle.js.

## Step 3: Make components directory.
    In src folder, create one another directory called components. We are saving all of our components files in here. Our main.js file will register all of our components, and then we compile this file via webpack.

### The first component would be Home.vue. So create Home.vue inside components.

    <template>
      <h1>Home</h1>
    </template>

    <script>
      export default {

     }
    </script>

### Then second would be About.vue

    // About.vue

    <template>
       <h1>About us</h1>
    </template>

    <script>
     export default {

     }
    </script>

### A third will be Contact.vue

    // Contact.vue
    <template>
      <h1>Contact us</h1>
    </template>

    <script>
      export default {

      }
    </script>

### Step 4: Config vue-router module.
    In main.js file first, we need to import a vue-router module from a node_modules folder because we have installed all of our dependencies in this project. Copy the following code into our main.js file.

    // main.js

    import Vue from 'vue'
    import VueRouter from 'vue-router'

    Vue.use(VueRouter)

    import Home from './components/Home.vue'
    import About from './components/About.vue'
    import Contact from './components/Contact.vue'

    const router = new VueRouter({
      mode: 'history',
      base: __dirname,
      routes: [
        { path: '/', component: Home },
        { path: '/about', component: About },
        { path: '/contact', component: Contact }
          ]
        })

    new Vue({
        router,
      template: `
        <div id="app">
          <ul>
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/about">About</router-link></li>
          <li><router-link to="/contact">Contact</router-link></li>
          </ul>
      <router-view></router-view>
    </div>
    `
      }).$mount('#app')

### I will describe each and every step in this file.

    1. First I have imported the vue-router and other required components to run this application.
    2. Created one vue-router instance and pass the configurable object in it.
    3. Created routes array to define URI pattern and also its related components.
    4. Also, create a router-view element to show the data related to specific routes.
    5. Finally created VueJS instance and pass the router object, main template and this will mount in our app id.

### Now, run the following command in your terminal.

    npm start
    It will start the webpack server. Generally, the port is 8080 but I have changed it to 3000 in the webpack.config.js file. Go to the following URL.

    http://localhost:3000
    
    If you click the about then the underlying component will be called and it will render via <router-view><router-view> elements.

    And your URL will be: http://localhost:3000/about

    There are so many other examples you can follow in this URL.

    https://github.com/vuejs/vue-router/tree/dev/examples

    You can find this how to use vue-router in VueJS project in the following Github URL

    https://github.com/TECHIES-HUB1/Vue-Router/blob/master/VueRouter-master.zip

    Clone the repository Go to the project folder and install the dependencies via "npm install" Start the webpack server by "npm start" Go to the URL: http://localhost:3000




