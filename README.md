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



## Quick Start (Local Demo)

This section is for quickly trying out the main features on your local machine. For a full, production-ready setup (all microservices, ports, troubleshooting, and advanced options), see the detailed [Build and Run Instructions](./build.md).

**Prerequisites:**
- Python 3.x installed
- `pip` for package installation

### Minimal Local Demo

1. **Run Courses Service**
    ```bash
    cd courses-service/coursesService
    pip install -r ../requirements.txt
    python manage.py migrate
    # (Optional) Only if fixtures/initial_data.json exists:
    python manage.py loaddata fixtures/initial_data.json
    python manage.py runserver 8000
    ```
    Leave this terminal open.

2. **Run Website Service** (in a new terminal)
    ```bash
    cd website-service/website
    pip install -r ../requirements.txt
    python manage.py migrate
    python manage.py runserver 8001
    ```
    Leave this terminal open.

3. **View in Browser:**
    - Homepage: [http://127.0.0.1:8001/](http://127.0.0.1:8001/)
    - Courses Page: [http://127.0.0.1:8001/courses/](http://127.0.0.1:8001/courses/)

---

## Full Setup & Advanced Usage (Recommended for Contributors)

To enable all features (discussions, events, authentication, etc.), or for production/deployment, follow the comprehensive [Build and Run Instructions](./build.md). That guide covers:
- Running all microservices (with recommended ports)
- Installing dependencies for each service
- Database migrations and initial data
- Testing and documentation
- Troubleshooting common issues

---



## Documentation & Testing

- Each service has its own README and test suite (pytest/Django).
- Sphinx documentation and HTML test reports are available for most services. See each service's `docs/` folder for details.
- For full testing and documentation instructions, see [Build and Run Instructions](./build.md).


## Project Resources

- [Project Design (Canva)](https://www.canva.com/design/DAG1I4Z0Czo/8nQoNM2eyZNPwHklDBVLHw/edit)
- [Project Document (Google Docs)](https://docs.google.com/document/d/1JwpzXqgHDF3L94ZqDkt1eLmVOWDtZ1287fCrDswk0aw/edit?tab=t.0)
