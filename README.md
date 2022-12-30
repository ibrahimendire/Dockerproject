# Welcome to CloudSheger <br>
## This is an interactive Docker project.<br>
## To create a Docker image, you will need to follow these steps:<br>

### 1, Install Docker on your machine. You can download Docker from the official website at here<br>
### 2, Create a new directory for your project and navigate to it in your terminal.<br>
Example:<br>

<code> mkdir DockerProject </code>

<code> cd DockerProject</code>

### 3, Generate, develop or clone an application in your project directory<br>
Example:<br>

 clone app from gitHub by running the following command in your terminal: <br>
<code> git clone https://github.com/ibrahimendire/docker-nodejs-app-sample.git </code>

generate a Node.js app using the Express generator,<br>
Install the Express generator by running the following command in your terminal:<br>
<code> npm install -g express-generator</code>

Next, we scaffold our application using the following command:<br>
<code> express [appName] </code>

 Next install package dependencies:<br>
 <code> npm install </code>

 Start the app by running the following command:<br>
<code> npm start </code>

 This will start the app and it will be available at http://localhost:3000/<br>
 If you point your browser to http://localhost:3000/ , you should see the application default page, with the text “Welcome to Express.”<br>
 That's it! You have now generated a Node.js app using the Express generator. You can find more detailed information in the Express documentation at Here.<br>
Now we have our working application<br>
### 4, Create a file called Dockerfile in the project directory. This file will contain the instructions for building the Docker image.<br>
 <code> touch Dockerfile </code>

Next, add the instructions for building your image in the Dockerfile. These instructions can include commands to install dependencies, copy files, and run scripts.<br>
Example:<br>
For the Node.js App we can put the following instruction in the Dockerfile<br>
<code>
 FROM node:10-alpine <br>
WORKDIR /usr/src/app<br>
COPY package*.json ./<br>
RUN npm install<br>
COPY . .<br>
EXPOSE 3000<br>
CMD ["npm", "start"]<br>
</code> <br>
Next <br>
### 5, Build the Docker image by running the docker build command in your terminal, followed by the path to the Dockerfile and a name for your image.<br>
example:<br>
<code> docker build -t my-image .</code>

This will build the Docker image and give it the name "my-image".<br>
To run the image, use the docker run command, followed by the name of the image and any necessary options or arguments. For example:<br>
<code> docker run my-image </code>

### 6, If you want to push your image to a registry, such as Docker Hub, you will need to first create an account on the registry and then use the docker push command to push the image to the registry.<br>
For example: To push to Docker Hub<br>
Create tag using the following command<br>
<code> docker tag [ImageID] [dockerhub repository name:tage name] </code>
<code>docker tag 15b9c76fadee ibrahimawol/test1:myfirstimage </code>

Push to docker hub using the following command<br>
<code> docker push [dockerhub repository name:tage name] </code>
 <code>docker push ibrahimawol/test1:myfirstimage </code>

That's the basic process for creating and running a Docker image. You can find more detailed information in the Docker documentation at https://docs.docker.com/.
