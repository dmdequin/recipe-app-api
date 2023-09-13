# recipe-app-api
Recipe API project.

Code developed while following the course: Build a Backend REST API with Python &amp; Django - Advanced.

The course can be found on the Udemy platform: [https://www.udemy.com/course/django-python-advanced/](https://www.udemy.com/course/django-python-advanced/)

## Running the Project

For run a local development version you will need Docker Desktop, and a cloned version of the repository. While in the main directory, run the following on the command line:
```
docker-compose build
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

## Testing Deployment without Deploying

- From the main directory, on the command line enter:
```
cd proxy
docker build .
```
- Copy the contents of ```.env.sample``` in the main directory into a new file named ```.env```
- In **docker-compose-deploy.yml** change line **37** from 80:8000 to 8000:8000.
- Run:
```docker-compose -f docker-compose-deploy.yml down```
- Then:
```docker-compose -f docker-compose-deploy.yml up```

From here you can test out deployment of the API using the documentation page as listed above.

## Deployment

This project was deployed using an EC2 instance on AWS. To avoid any potential costs the EC2 instance has been deleted and the project is no longer deployed. You can follow the steps used to deploy this yourself by cloning this project and following the instructions (here)[https://github.com/LondonAppDeveloper/build-a-backend-rest-api-with-python-django-advanced-resources/blob/main/deployment.md#install-and-configure-depdencies].
