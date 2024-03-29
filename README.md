# Elevator-App-MongoDB

An application managing a fleet of elevators. The app is built using Node.js and utilizes MongoDB for data storage. It allows tracking elevator movements, handling elevator calls, and maintaining the state of each elevator.


## Installation and Setup
Information regarding installation and launching application.

### Requirements
- Access to a terminal
- Node.js and Node Package Manager installed
- MongoDB installed on your system
- Required libraries will be installed

### Installations and start app
To install the required dependencies for each section of the app start by navigating to the root folder of the app in your terminal.  
Run the following command in your terminal.

```bash
# Install project dependencies
npm install

```

#### Install MongoDB
To install MongdoDB on your system navigate to this page: `https://www.mongodb.com/try/download/community`.  
Pick the version matching your operating system and pick version 7.0.1 

All other interactions with the database is handled through mongoose library.

#### Starting the application
After installation is complete. Start the application by running the following command in the root folder of the project in your terminal.

```bash
# Start the application. Launches both the frontend and the backend.
npm start
```


## Backend - API Endpoints

### Get All Elevators

- **Endpoint:** `/elevator/`
- **Method:** GET
- **Description:** Retrieves all elevators from the system. 
- **Response:**
  - Returns a array of elevators in the system.
  - Sends a status code of 200.

### Call Elevator

- **Endpoint:** `/elevator/call`
- **Method:** PUT
- **Description:** Call elevator
- **Request Body:** JSON with desired floor.
- **Response:**
  - 200 Successful: Sends status code 200 and the elevator that is called or queued.
  - Sends status code 200 and the message "Elevator already there" if an elevator is already at the desired floor 
  - Returns a status code of 500, internal server error if something goes wrong in the backend. 


## Frontend

<img src="Images/frontend-overview.png" alt="Frontend Screenshot" width="850" height="400">

The frontend consists of two components:
- A display of the current status of the elevators in the system
- A input field for the user to call for an elevator to a specified floor.

### Usage
- The user can call for an elevator to a certain floor by providing a floor number and pressing "Call Elevator". The frontend makes sure the request is valid before passing the request to the backend and processing it. 
- The status of the elevators are updated and displayed. Here the user can monitor the behaviour of each elevator and see how the call they placed is being processed and performed.

## Project Structure
The project is located in two different folders: backend and elevator-frontend. These folders contain the code used to operate the respective parts of the application. 

### Project folder 
The root folder of the project has the following structure:

```
backend/
elevator-frontend/
Images/
node_modules/
.gitignore
package-lock.json
package.json
README.md
```
- `backend/` folder containing the backend part of the application.
- `elevator-frontend/` folder containing the frontend part of the application.
- `Images/` contains images used in the README.

### Backend
The structure in the backend is as follows:

```
backend/
node_modules
src/
  database.js
  databaseSetup.js
  elevator.js
  elevatorManager.js
  elevatorModel.js
  elevatorMovement.js
  routes.js
.gitignore
app.js
package-lock.json
package.json
```

- `app.js` sets up the Express application and serves as the entry point to the application.
- `elevatorManager.js` is responsible for operating the backend, the brains of the backend. This module uses the other modules. 
- `database.js` is a module responsible for database interactions. 
- `elevatorMovement.js` simulates elevator movements in the system.
- `databaseSetup.js` is used when the system is launched to initialize the database and populate it with elevator data if needed. 
- `routes.js` configures my API routes

### Frontend

The file structure in the frontend of the application is as follows:

```
swapi-frontend/
  node_modules
  public/
    ...
  src/
    components/
      CallElevator
      ElevatorStatus
      Heading
    App.css
    App.js
    index.css
    index.js
  .gitignore
  package-lock.json
  package.json
```

- `public` folder contains code related to a production build. This applicaton is running in development mode so the files in this folder are not used.  
  Placeholder for when the app is build for production.

- `src` folder contains all the source code for the frontend.
- `index.js` is the entrypoint to the application. In this file the react application is started and the App component is mounted. 
- `Components` folder contains all the different components used to build the frontend.  
  Each components has a folder used to store the source code and the css code for that particular component.
- `App.js` is the file that assembles the frontend. Here each component is mounted and the structure of the page is created.  
 This file or module is considered the main component in the frontend and holds it all together.

## Technologies Used

### Languages
- JavaScript

### Libraries and Frameworks
- React
- Express
- Mongoose (MongoDB)
- Axios for making API requests
- Bootstrap for styling

