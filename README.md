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

This project is composed of multiple microservices:

*   `account-service`: Manages user accounts.
*   `courses-service`: Manages courses.
*   `discussions-service`: Manages discussions.
*   `events-service`: Manages events.
*   `userauthen-service`: Handles user authentication.
*   `website-service`: The main web interface.

## Running the services

Each service is a Django project and can be run individually.

For example, to run the `website-service`:

```bash
cd website-service/website
python manage.py runserver
```

## URLs

*   https://www.canva.com/design/DAG1I4Z0Czo/8nQoNM2eyZNPwHklDBVLHw/edit

*   https://docs.google.com/document/d/1JwpzXqgHDF3L94ZqDkt1eLmVOWDtZ1287fCrDswk0aw/edit?tab=t.0
