# Simplified Django Project Structure Notes

## What is a Django Project?
A **Django project** is a web application made up of configurations and apps. It includes settings, URL routing, and app logic.

## What is a Django App?
A **Django app** is a self-contained module within a project, handling specific features like authentication or blog posts.

---

## Default Django Project Structure
Run `django-admin startproject project_name` to create a project with this structure:

```
project_name/
│   manage.py
│
├── project_name/  # Main project folder
│   │   __init__.py
│   │   settings.py
│   │   urls.py
│   │   asgi.py
│   │   wsgi.py
│
└── app_name/  # Apps are created separately
```

### Key Files:

1. **`manage.py`**
    - Command-line tool for managing the project (e.g., `python manage.py runserver`).

2. **`project_name/`** *(Main Project Folder)*
    - **`__init__.py`**: Marks the folder as a Python package.
    - **`settings.py`**: Project configuration (database, apps, templates, etc.).
    - **`urls.py`**: Main URL routing.
    - **`asgi.py`**: For asynchronous deployment.
    - **`wsgi.py`**: For production deployment.

---

## Default Django App Structure
Run `python manage.py startapp app_name` to create an app with this structure:

```
app_name/
│   __init__.py
│   admin.py
│   apps.py
│   models.py
│   views.py
│   tests.py
│   urls.py
│   migrations/
```

### Key Files:

1. **`__init__.py`**: Marks the folder as a Python package.
2. **`admin.py`**: Registers models in the Django admin panel.
3. **`apps.py`**: App configuration.
4. **`models.py`**: Defines database models.
5. **`views.py`**: Handles HTTP requests and responses.
6. **`urls.py`**: App-specific URL routing.
7. **`tests.py`**: For writing automated tests.
8. **`migrations/`**: Stores database migration files.

---

## Summary
- A **Django Project** is the entire web application.
- A **Django App** is a modular component within the project.
- Each file has a specific role (e.g., `settings.py` for config, `models.py` for database structure).

This structure keeps Django projects clean and scalable. 🚀
___

## Resources 📚
### 📖 Articles & Documentation
1. **Structure tutorial from documentation:** [Django Docs](https://docs.djangoproject.com/en/5.1/intro/tutorial01/)
2. **Project structure article:** [Medium Guide](https://medium.com/django-unleashed/django-project-structure-a-comprehensive-guide-4b2ddbf2b6b8)
3. **Comprehensive guide to structuring Django projects:** [Another Medium Article](https://medium.com/@akshatgadodia/a-comprehensive-guide-to-structuring-django-projects-best-practices-and-example-afb77d8497d5)

### 🎥 Video Tutorials
- [Complete Django Playlist (English)](https://youtube.com/playlist?list=PL4cUxeGkcC9iqfAag3a_BKEX1N43uJutw&si=UVUi7OR0kd1dvKct)
- [Complete Django Playlist (Arabic)](https://youtube.com/playlist?list=PLknwEmKsW8OtK_n48UOuYGxJPbSFrICxm&si=NK1jDGcWGWb76TWL)

---