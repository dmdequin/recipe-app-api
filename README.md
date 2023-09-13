# recipe-app-api
Recipe API project.

Code developed while following the course: Build a Backend REST API with Python &amp; Django - Advanced.

The course can be found on the Udemy platform: [https://www.udemy.com/course/django-python-advanced/](https://www.udemy.com/course/django-python-advanced/)

## Running the Project

For run a local development version, switch to the **development** branch. You will need Docker Desktop, and a cloned version of the repository. While in the main directory, run the following on the command line:
```
docker-compose up
```
There is no front-end developed for this project. To test the API's endpoints, see the note below on documentation.

## Documentation
The documentation is created using Swagger and contains all of the API endpoints developed for this project along with available actions on each endpoint. Each type of request can be tested directly on the API on the documentation page. To access this:

From the terminal in the project main directory run:
```
docker-compose up
```

Then visit
Visit (http://127.0.0.1:8000/api/docs/)[http://127.0.0.1:8000/api/docs/]

Some endpoints require authentication (a user that is logged in). First create a user at ```/api/user/create```.

To authenticate (log in):
- Go to the ```/api/uer/token``` **POST** method
- Click "Try it out"
- Select "multipart/form-data"
- Fill in the form with your email and password
- Click "Execute"
- Copy the authentication token given in the response
- At the top of the page click "Authorize"
- Under tokenAuth (apiKey) enter "Token <token>" and click "Authorize"

Now you will be authorized and can test out functionality that requires a user to be logged in.
