# The Hindu

## Table of Contents

1. [Description](#description)
2. [Screenshots](#screenshots)
3. [Architecture Overview](#architecture-overview)
4. [API Documentation](#api-documentation)
5. [Frontend Component Tree](#component-tree)
6. [ERD](#erd-vis)
7. [Installation and Usage](#installation-usage)

## Description <a name="description"></a>

**The Hindu** is a full-stack blog application with a React frontend and Django/DRF backend, integrated with AWS-S3 & AWS-RDS.

**Features:**
- JWT authentication
- Responsive design
- User management: sign up, log in, log out, update profile, delete account
- Blog management: create, edit, delete, like, comment, save
- Category filtering, pagination, search, rich text editor

## Screenshots <a name="screenshots"></a>

![](readme-res/screenshots.png)

## Architecture Overview <a name="architecture-overview"></a>

![](readme-res/architecture.png)

## API Documentation <a name="api-documentation"></a>

Endpoints: [API Docs](https://documenter.getpostman.com/view/25138891/2s935oL3mZ)

- **Users**: 
  - `POST api/users/user/signup/`
  - `POST api/users/user/login/token/`
  - `GET api/users/all/`
  - `GET, PUT, DELETE api/users/user/`

- **Blogs**: 
  - `POST api/blogs/blogpost/`
  - `GET api/blogs/all/`
  - `GET, PUT, DELETE api/blogs/blog/{blogId}/`
  - `GET api/blogs/userblogs/`

- **Comments**: 
  - `POST api/blogs/blog/{blogId}/commentpost/`
  - `GET api/blogs/blog/{blogId}/comments/all/`
  - `PUT, DELETE api/blogs/blog/{blogId}/comment/{commentId}/`
  - `GET api/blogs/blog/{blogId}/totalcomments/`

- **Applauds**: 
  - `POST api/blogs/blog/{blogId}/applaud/`
  - `GET api/blogs/blog/{blogId}/applauder/exists/`

- **Reading List**: 
  - `POST api/blogs/blog/{blogId}/readinglist/save/`
  - `GET api/blogs/readinglist/all/`
  - `GET api/blogs/blog/{blogId}/reader/exists/`

## Frontend Component Tree <a name="component-tree"></a>

![](readme-res/component-tree-vis.png)

## ERD <a name="erd-vis"></a>

![](readme-res/erd-vis.png)

## Installation and Usage <a name="installation-usage"></a>

**Frontend:**
- `cd frontend`
- `npm install` & `npm start`

**Backend:**
- `cd backend`
- `py -m venv venv`
- `venv\Scripts\activate.bat`
- `pip install -r requirements.txt`
- `python manage.py makemigrations`
- `python manage.py migrate`
- `python manage.py createsuperuser`
- `python manage.py runserver`

**Makefile:**
- `make build-backend`
- `make build-frontend`
- `make run-backend`
- `make run-frontend`

**Docker:**
- `docker-compose build`
- `docker-compose up`

> NOTE: For local image uploads, update `backend/core/settings.py` and `backend/core/urls.py`.

