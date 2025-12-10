


# Build and Run Instructions

This project is a microservices-based Django application. You must run the backend services and the frontend website simultaneously for the full application to work.


## 🛠 Prerequisites

Before you begin, ensure you have the following installed:
- **Python 3.9+**
- **Git**
- **Pip** (Python package installer)

---


## 🚀 Quick Start (Manual)

To run the system, you will need to open **multiple terminal windows** (one for each service).


### 1. Backend Services (Django)
Start each backend Django service in its own terminal window:


#### **Courses Service**
1.  Open a terminal.
2.  Clone and enter the directory:
    ```bash
    git clone https://github.com/UMASS-CICS520-ProjectGroup9/courses-service.git
    cd courses-service/coursesService
    ```
3.  Install dependencies (choose one):
    ```bash
    # If you are inside the app folder (e.g., coursesService, professorsService, etc.)
    pip install -r ../requirements.txt

    # If you are in the service root directory
    pip install -r requirements.txt
    ```
4.  Apply migrations and load initial data (if needed):
    ```bash
    python manage.py migrate
    ```
5.  (Optional) Load initial data:
    ```bash
    # Only run if fixtures/initial_data.json exists
    python manage.py loaddata fixtures/initial_data.json
    ```
5.  Run the service:
    ```bash
    python manage.py runserver 5001
    ```


#### **Discussions Service**
1.  Open a **new** terminal.
2.  Clone and enter the directory:
    ```bash
    git clone https://github.com/UMASS-CICS520-ProjectGroup9/discussions-service.git
    cd discussions-service/discussionsService
    ```
3.  Install dependencies:
    ```bash
    pip install -r ../requirements.txt
    ```
4.  Apply migrations and load initial data (if needed):
    ```bash
    python manage.py migrate
    python manage.py loaddata fixtures/initial_data.json
    ```
5.  Run the service:
    ```bash
    python manage.py runserver 5002
    ```


#### **Professors Service**
1.  Open a **new** terminal.
2.  Clone and enter the directory:
    ```bash
    git clone https://github.com/UMASS-CICS520-ProjectGroup9/professors-service.git
    cd professors-service/professorsService
    ```
3.  Install dependencies:
    ```bash
    pip install -r ../requirements.txt
    ```
4.  Apply migrations and load initial data (if needed):
    ```bash
    python manage.py migrate
    python manage.py loaddata fixtures/initial_data.json
    ```
5.  Run the service:
    ```bash
    python manage.py runserver 5003
    ```



#### **Events Service**
1.  Open a **new** terminal.
2.  Clone and enter the directory:
    ```bash
    git clone https://github.com/UMASS-CICS520-ProjectGroup9/events-service.git
    cd events-service/eventsService
    ```
3.  Install dependencies:
    ```bash
    pip install -r ../requirements.txt
    ```
4.  Apply migrations and load initial data (if needed):
    ```bash
    python manage.py migrate
    python manage.py loaddata fixtures/initial_data.json
    ```
5.  Run the service:
    ```bash
    python manage.py runserver 5006
    ```

#### **Account Service**
1.  Open a **new** terminal.
2.  Clone and enter the directory:
    ```bash
    git clone https://github.com/UMASS-CICS520-ProjectGroup9/account-service.git
    cd account-service/accountService
    ```
3.  Install dependencies:
    ```bash
    pip install -r ../requirements.txt
    ```
4.  Apply migrations and load initial data (if needed):
    ```bash
    python manage.py migrate
    python manage.py loaddata fixtures/initial_data.json
    ```
5.  Run the service:
    ```bash
    python manage.py runserver 5005
    ```

---


### 2. Website Service (Frontend)

1.  Open a **new** terminal.
2.  Clone the frontend:
    ```bash
    git clone https://github.com/UMASS-CICS520-ProjectGroup9/website-service.git
    cd website-service/website
    ```
3.  Install dependencies:
    ```bash
    pip install -r ../requirements.txt
    ```
4.  Apply migrations and load initial data (if needed):
    ```bash
    python manage.py migrate
    python manage.py loaddata fixtures/initial_data.json
    ```
5.  Run the website:
    ```bash
    python manage.py runserver 8000
    ```
6.  Open `http://localhost:8000` in your browser.

---


## ⚙️ Configuration & Ports

The services are expected to run on specific ports to communicate. Ensure your `manage.py` or `app.py` files are configured to match these defaults:

| Service | Recommended Port |
| :--- | :--- |
| **Website (Frontend)** | `8000` |
| **Courses Service** | `5001` |
| **Discussions Service** | `5002` |
| **Professors Service** | `5003` |
| **User/Auth Service** | `5004` |
| **Account Service** | `5005` |
| **Events Service** | `5006` |

*If you encounter "Address already in use" errors, change the port number in the specific service's `manage.py` or `app.py` file.*



## 🧪 Testing & Documentation

To verify the system is working:
1.  Navigate to the `website-service` URL in your browser.
2.  Try to load the "Courses" page. If the list populates, the **Courses Service** is connected correctly.
3.  Try to view a discussion. If it loads, the **Discussions Service** is connected.

### Run Tests and Generate HTML Reports
For each service, from its root directory:
```bash
pip install pytest pytest-django pytest-html sphinx
pytest --html=docs/build/html/test_report.html --self-contained-html
```

### Build Sphinx Documentation
For each service, from its `docs` directory:
```bash
cd docs
make html
```
Open `docs/build/html/index.html` in your browser to view the documentation and test report.

## 🛠 Troubleshooting

- If you see "ModuleNotFoundError", check your PYTHONPATH and that all dependencies are installed.
- If you see "Address already in use", change the port in the runserver command.
- If migrations fail, check your database setup and migration files.
- If Sphinx docs do not build, ensure `conf.py` exists in `docs/source/`.
- If tests are not discovered, check `pytest.ini` and test file naming.