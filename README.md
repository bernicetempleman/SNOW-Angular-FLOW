# SNOW-Angular-FLOW
By flow, we mean how the files are called and in which sequence of files the app gets executed when we are developing it.

## 1. ANGULAR.JSON 
- ANGULAR.JSON is the file which has various properties and configuration of your Angular project. 
- This is the file which is first referred by the builder to look for all the paths and configurations and to check which is the main file. 
- I have generated an angular hello-world app by the CLI. 
- Inside the angular.json file of this project, under the build section, you can see the options object as follows
- It has a reference to the main.ts file which tells the builder to start the app from there.

![image](https://user-images.githubusercontent.com/12488769/148704574-3b4a33b0-05ce-4cee-820e-dc996ae0e54b.png)

## 2. MAIN.TS
- This file acts as the entry point of the application. 
- This entry point is defined in the internals of webpack that is used by Angular to support the modular functionality. 
- The path/name of the main file can be changed but it should also be changed in angular.json file. 
- Main.ts helps in creating the browser environment for the application to run. 
- This is done by
- This file acts as the entry point of the application. 
- This entry point is defined in the internals of webpack that is used by Angular to support the modular functionality. 
- The path/name of the main file can be changed but it should also be changed in angular.json file. 
- Main.ts helps in creating the browser environment for the application to run. 
- This is done by
![image](https://user-images.githubusercontent.com/12488769/148704626-ff0bd151-34bb-44f5-9ea4-2bead0f674b2.png)
- After this, main.ts file calls the function bootstrapModule(AppModule) which tells the builder to bootstrap the app
- After this, main.ts file calls the function bootstrapModule(AppModule) which tells the builder to bootstrap the app![image](https://user-images.githubusercontent.com/12488769/148704638-0534fc4b-0c72-44cb-ac81-609ddeffe909.png)

## 3. APP.MODULE.TS
- From the main.ts file, it is very clear that we are bootstrapping the app with AppModule. 
- This AppModule is defined in APP.MODULE.TS file which is found in
![image](https://user-images.githubusercontent.com/12488769/148704662-b37d9ff6-2672-469f-a78a-ef32f50560ef.png)

- This is the module, created with the @NgModule decorator, which has declarations of all the components we are creating within the app module so that angular is aware of them.
- Here, we also have imports array where we can import other modules and use in our app. 
- Below is an example of app.module.ts file with a test component declared and two modules imported.
![image](https://user-images.githubusercontent.com/12488769/148704696-77b95acc-f96b-48db-88fe-baf7ffeedd41.png)

## 4. APP.COMPONENT.TS
- From the app.module.ts file above, we can clearly see that the module asks to bootstrap the app component. 
- This app component is in app.component.ts file. 
- This is the file which interacts with the html of the webpage and serves it with the data. 
- The component is made by using @Component decorator which is imported from @angular/core. 
- The component has a selector, which is like a custom html tag which we can use to call that component!
- It then has template or templateUrl which contains the html of the page to be displayed. 
- It also has the styleUrls array where component specific style sheets can be placed. 
- This is how a component file looks
![image](https://user-images.githubusercontent.com/12488769/148704779-e4edde92-d4dc-47d1-a13d-2b32fa6b3c77.png)
- By this time, compiler has all the details about the components of the app and now they are ready to be used.

## 5. index.html
- Now, since angular is well aware of the modules, components, styles, scripts etc. which are required to display the page, it’s show time!
- Here, the index.html file is called. 
- It is found in the src folder of the app. 
- Compiler dynamically adds all the javascript files at the end of this file. Since all the components are now known, the html file calls the root component that is app-root. 
- The root component is defined in app.components.ts which targets app.component.html.
- This is how index.html file looks like in the coding environment
![image](https://user-images.githubusercontent.com/12488769/148704834-985d7337-631e-46c1-b5c2-68cb17908ac4.png)
- In the body tag, you can see that a html like element <app-root></app-root> is present. 
- Well, this is our component selector for the AppComponent which is defined in app.component.ts file. 
- It asks angular to load that component.

## APP.COMPONENT.HTML
- This is the file which contains all the html elements and their binding which are to be displayed when the app loads. 
- Contents of this file are the first things to be displayed.













