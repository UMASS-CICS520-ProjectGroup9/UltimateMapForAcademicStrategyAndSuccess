# Ultimate Map for Academic Strategy & Success (UMASS)

## Overview

Ultimate Map for Academic Strategy & Success (UMASS) is a comprehensive web platform designed to help university students thrive academically and prepare for their future careers. Students may share resources, access course information, evaluate professors, collaborate with peers, and strategize their academic journey.

## Features

*   Professor and course ratings and reviews
*   Crawl school course listing for data integration
*   Shared resources (past exams and homeworks)
*   Community discussion board
*   Course builder with calendar


## Microservices

This project is composed of multiple microservices (with current deployment URLs):

- `account-service`: Manages user accounts. *(URL: configurable/local only)*
- `courses-service`: Manages courses. [https://sgtangsweb.pythonanywhere.com/api/courses/](https://sgtangsweb.pythonanywhere.com/api/courses/)
- `professors-service`: Professor data. [https://georgesweb.pythonanywhere.com/api/professors/](https://georgesweb.pythonanywhere.com/api/professors/)
- `discussions-service`: Discussions. [https://isoulweb.pythonanywhere.com/api/discussions/](https://isoulweb.pythonanywhere.com/api/discussions/)
- `events-service`: Events. [https://ping4learn1.pythonanywhere.com](https://ping4learn1.pythonanywhere.com)
- `userauthen-service`: User authentication. [https://ping4learn0.pythonanywhere.com](https://ping4learn0.pythonanywhere.com)
- `website-service`: The main web interface. [https://cics520umass.pythonanywhere.com](https://cics520umass.pythonanywhere.com)

## Running the Project

To get the full application running, you need to run each microservice. Here is a guide to run the main `website-service` and the `courses-service` to see the course listing functionality.

**Prerequisites:**
*   Python 3.x installed
*   `pip` for package installation

### Step 1: Run the Courses Service

The `courses-service` provides the data for university courses.

1.  Open a terminal and navigate to the `courses-service` directory:
    ```bash
    cd courses-service/coursesService
    ```
2.  Install the required Python packages:
    ```bash
    pip install -r ../requirements.txt
    ```
3.  Apply database migrations and load initial data:
    ```bash
    python manage.py migrate
    python manage.py loaddata fixtures/initial_data.json
    ```
4.  Start the service (it will run on `http://127.0.0.1:8000/` by default):
    ```bash
    python manage.py runserver
    ```
    Keep this terminal running.


### Step 2: Run the Website Service

The `website-service` provides the main user interface.

1.  Open a **new** terminal and navigate to the `website-service` directory:
    ```bash
    cd website-service/website
    pip install -r ../requirements.txt
    python manage.py runserver 8001
    ```
    Keep this terminal running.

### Step 3: View the Website

Now you can access the website in your browser:

*   **Homepage:** [http://127.0.0.1:8001/](http://127.0.0.1:8001/)
*   **Courses Page:** [http://127.0.0.1:8001/courses/](http://127.0.0.1:8001/courses/)


### Running Other Services

To enable all features (like discussions, events, etc.), you need to run the other microservices as well. The process is similar for each service: navigate to its directory, install requirements, and run the server on a unique port. For production, the services are deployed at the URLs listed above.

## Documentation & Testing

- Each service has its own README and test suite (pytest/Django)
- The `website-service` includes Sphinx documentation:
    - Source: `website-service/docs/source/`
    - Build: `website-service/docs/build/html/`
    - To build docs:
        ```bash
        cd website-service/docs
        make html
        ```
    - Open `website-service/docs/build/html/index.html` in your browser
- HTML test reports are generated and included in the Sphinx docs


## URLs

*   https://www.canva.com/design/DAG1I4Z0Czo/8nQoNM2eyZNPwHklDBVLHw/edit

*   https://docs.google.com/document/d/1JwpzXqgHDF3L94ZqDkt1eLmVOWDtZ1287fCrDswk0aw/edit?tab=t.0
