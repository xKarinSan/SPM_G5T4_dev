# Learning Journey Portal

<a name="readme-top"></a>
<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#frontend">Frontend</a>
      <ul>
        <li><a href="#frontend-folder-structure">Frontend Folder Structure</a></li>
        <li><a href="#frontend-prerequisites">Frontend Prerequisites</a></li>
        <li><a href="#running-frontend">Running Frontend</a></li>
      </ul>
    </li>
    <li>
    <a href="#backend">Backend</a>
    <ul>
        <li><a href="#backend-folder-structure">Backend Folder Structure</a></li>
        <li><a href="#backend-prerequisites">Backend Prerequisites</a></li>
        <li><a href="#running-backend">Running Backend</a></li>
      </ul>
    </li>
    <li><a href="#database">Database</a></li>
    <li><a href="#continuous-integration">Continuous Integration</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project
LJP system to have a personal learning journey tracker that could guide them on the courses they could take either from the LMS or in physical classes to prepare them for the next position or in a different area within the organisation.
The system would allow staff to set their learning goal by setting on a position that they are working towards. The system will then list out the skills required for those positions and the courses (internal/external) that correspond to those skills. They are then able to view the details of those courses. They are then able to register for those courses. Upon completion of the courses, HR would be able to update the skillset of the staff. The Learning Journey of the staff would also then reflect so.

Our project is hosted live at:
* [Frontend Web Application](http://spm-smallbucket.s3-website-us-east-1.amazonaws.com/)
* [Backend API Documentations](https://01p0cxotkg.execute-api.us-east-1.amazonaws.com/dev/docs)
* [C4 Diagram](https://www.figma.com/file/6mlZ08E8T49QoVSF3Op89G/SPM-Group-2?node-id=0%3A1)
* [ERD Diagram](https://lucid.app/lucidchart/4d0a5710-dff1-4924-a95c-e0c342fc66af/edit?viewport_loc=-239%2C51%2C1125%2C1031%2C0_0&invitationId=inv_3dafcc49-9a87-4aa9-afd1-25f656fc8152#)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



### Built With

[![Vue][Vue.js]][Vue-url] [![FastAPI][FastAPI]][FastAPI-url] [![MYSQL][MYSQL]][MYSQL-url]

## Frontend
Our Vue development/production application is hosted in Amazon S3 buckets.

#### Frontend Folder structure
```bash 
frontend
|   
├── public
|   ├── index.html
|   
├── src
|   ├── assets
|   | 
|   ├── components
|   |   ├── <component_name>Component.vue
|   | 
|   ├── plugins
|   | 
|   ├── router
|   |   ├── index.js
|   | 
|   ├── router
|   |   ├── index.js
|   |   ├── auth.js
|   |   ├── subscriber.js
|   | 
|   ├── views
|   |   ├── Dashboard
|   |   |   ├── Layout
|   |   |   |   ├── DashboardLayout.vue
|   |   |   ├── Dashboard.vue
|   |   ├── <feature_name>.vue
|   |
|   ├── App.vue
|   |
|   ├── main.js
|   
├── tests
|   ├── driverutil
|   |   ├── __init__.py
|   |   ├── Browser.py
|   
|   ├── pageobjects
|   |   ├── __init__.py
|   |   ├── <TestFunctionsName>.py
|   
|   ├── tests
|   |   ├── RunTest.py
|
├── .gitignore
|
├── babel.config.js
|
├── package-lock.json
|
├── App.vue

```
### Frontend Prerequisites
* Node.JS installed on your computer


### Running frontend
To run the frontend UI, type the following in your terminal:
```
cd frontend
npm i 
npm run serve
```
Note: 
- Make sure you are in the Frontend folder before you do any of the above in the CLI
- npm i installs all the required dependencies 

### To run the test cases, type the following in your terminal
```
cd Tests
python3 RunTest.py
```
Note: 
- Make sure you are inside the Frontend folder and you've run "npm run serve" before the test scripts
- cd Tests: you go to the path of the Tests folder
- IMPORTANT: before you run your test file inside the 'Tests' folder

## Backend 
Our FastAPI backend development/production application is hosted in Amazon Lambda services.

#### Backend Folder structure

```bash 
Backend
├── Routes (the various routes are stored; relevant functions from ApiFunctions are imported)
|   ├── <api_name>Routes.py
|
├── Models (Entity models are found here; this is solely for table creation for SQL)
|   ├── <model_name>.py
|
├── Tests (This is where you test the individual APIs)
|   ├── TestScripts (this is where the test cases of each entity is at)
|   |   ├── <api_name>Test.py
|   |
|   ├── HelperFunctionForTest.py (they provide helper functions for the test cases)
|   ├── MainTest.py (they run all the unit tests together)
|
├── Schema (This is to facilitate CRUD operations in FastAPI especially for SQL)
|   ├── <api_name>Schema.py
|
├── HelperFunctions.py (For helper functions that are usable for the API)
|
├── .gitignore (this lists the type of files that will NOT be tracked by GitHub)
|
├── TableInfo.py (this stores the information of the columns of each entity)
|
├── config.py (all the setup will happen there; SQLAlchemy and App initialisation)
|
├── main.py (where you actually run the code; you import the routes from the Routes folder)
|
├── database.py (this is where the database tables are created)
|
├── ErrorHandler.py (this is where the custom error handlers are at)
|
├── requirments.txt (this lists the dependencies required to run the project)
```

**NOTE: the naming convention of <model_name> and <api_name> should be consistent.**

Eg: If your model name is 'Entity', your naming convention should be like:
- Routes: EntityRoutes.py
- ApiFunctions: EntityFunctions.py
- Models: Entity.py
- Tests: EntityTest.py

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Backend Prerequisites 
Python 3.7+

FastAPI stands on the shoulders of giants:

* <a href="https://www.starlette.io/" class="external-link" target="_blank">Starlette</a> for the web parts.
* <a href="https://pydantic-docs.helpmanual.io/" class="external-link" target="_blank">Pydantic</a> for the data parts.

### Setup (for testing):
1. Clone this repo
2. Open the project in VSC 
3. In your terminal, type this in CLI: 
```
pip install pipreqs
pipreqs Backend
pip install -r requirements.txt
```

NOTE: 
- pip install pipreqs installs the 'pipreqs' library, which allows you to get the dependencies from ONLY this project.
- this downloads the dependencies stated in the requirements.txt


### Running backend
To run the main API, type the following in your terminal:
```console
$ uvicorn main:app --reload

INFO:     Uvicorn running on http://127.0.0.1:8000 (Press CTRL+C to quit)
INFO:     Started reloader process [28720]
INFO:     Started server process [28722]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
```

<details markdown="1">
<summary>About the command <code>uvicorn main:app --reload</code>...</summary>

The command `uvicorn main:app` refers to:

* `main`: the file `main.py` (the Python "module").
* `app`: the object created inside of `main.py` with the line `app = FastAPI()`.
* `--reload`: make the server restart after code changes. Only do this for development.

</details>

### To run the test cases, type the following in your terminal
```
cd Tests
python MainTest.py
```
Note: 
- Make sure you are inside the Backend folder before running the backend API and its test scripts
- cd Tests: you go to the path of the Tests folder
- IMPORTANT: before you run your test file inside the 'Tests' folder, ensure your main.py is running


## Database
Development/Production database is a hosted MySQL AWS RDS instance. 

## Continuous Integration
Continuous Integration is enabled for this repository via CircleCI. Deployment to the development server is handled when a PR merge to main is successful.

Refer the CI pipeline scripts in `/.circleci/config.yml`.


<p align="right">(<a href="#readme-top">back to top</a>)</p>

[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/
[FastAPI]: https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi
[FastAPI-url]: https://fastapi.tiangolo.com/
[MYSQL]: https://img.shields.io/badge/mysql-205571.svg?style=for-the-badge&logo=mysql&logoColor=white
[MYSQL-url]: https://www.sqlalchemy.org/