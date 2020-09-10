# NodeReactPOC
Setup Architecture: 

We follow a complete MVC setup architecture where the NodeJS will serve as the Controller and Model.
And React will serve as the View. React will be installed in the folder called as Client. Internally, React will have it's own controller which is at componenet level.

Steps for the setup->
1)create a folder where you place your project. Open the folder in VS code. 

2)create a file called .gitignore and edit the file. Write node_modules/ and save the file. 

3)in the command line of the vs code or in the in terminal navigate to the created folder and use command -> git init. This is just to initialise the git repos locally(version controlling) 

4)lets initiate the project with the first step to create package.json. package.json is the installer for any project. So, do npm init .  Give a meaningful package name(preferably project name), version-> let it be same, description should be meaningful, entrypoint-> server.js ,test command->skip, git repos->skip, key words->skip, author-> name yourself :),licence->MIT. Press Enter to complete. 

5) do npm i express express-validator request. 
         express is used to serve the web applications in Node JS.Find more on docs here-> http://expressjs.com/
         express-validator is used for validations regarding data . Find more on docs here-> https://express-validator.github.io/docs/
         request -> HTTP client used to call API form Node JS. Find more on docs here-> https://github.com/request/request 
         All these are added as direct dependecies 
         
6)do  npm i -D nodemon concurrently
         nodemon constantly watches the development changes  and reloads the page without us being able to do manually.
         concurrently is a dev dependency which lets us run 2 parallel servers at the same time with one single command.
         This is added as development dependency. 
         
7)Create a Main Entry file called Server.js . Write the following Code->
------->
    const express = require('express');
    const app = express();
     app.get('/',(req,res) => res.send('API running'));
    const PORT = process.env.PORT || 5000;
app.listen(PORT,() => console.log(`server started on port ${PORT}`));
<------ 

8)Go to package.json. Add 2 lines in "scripts" object->
------->
"start" : "node server",
"server" : "nodemon server"
<------ 

9) Save and Run the application using npm run start in the command line. go to browser and hit http://localhost:5000. It should be up and running.
Till here was the basic setup of Node JS .  

10)Lets commit our work. do 1) git add  2) git commit -m "added server" 

11)Now we have to install react. We can install using 2 ways-> a)create-react-app by facebook b) create-react-app-rewired. the latter one gives us more control to change webpack /babel configs without ejecting the project. 

12)But for now, We would go with the first approach .Create a folder called client  

