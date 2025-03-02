# Django Introduction and Setup

---

## **What is Django?**
- High-level Python web framework.
- Encourages rapid development and clean design "structure".
- Handles web development tasks, allowing developers to focus on applications.

---

## **Why Use Django?**
- **Fast Development**: Built-in features speed up development.
- **Security**: Protects against common vulnerabilities (SQL injection, CSRF, etc.).
- **Scalability**: Handles high traffic loads efficiently.
- **Versatile**: Suitable for CMS, e-commerce, scientific computing, etc.
- **Batteries Included**: Comes with an admin panel, ORM, authentication, and more.

---

## **What Does Django Code Look Like?**
- **URLs**: Defines routes and directs HTTP requests to views.
- **Views**: Handles requests and returns responses.
- **Models**: Defines database structure and manages data.
- **Templates**: HTML files with placeholders for dynamic content.
- **Follows MVT Architecture** (Model-View-Template), similar to MVC.
  ![How Django Works](img/overview.png)

---

## **Model-View-Template Architecture (MVT)**

### **What is MVT?**
MVT is a software design pattern within Django that utilizes:

#### 1. **Models**: Handle data logic and structure of your database.
#### 2. **Views**: Handle the application's logic and functionality.
#### 3. **Templates**: Handle the layout and structure of the user-facing application.

---

## **What is MVC and What Does Django Use?**

### **Model-View-Controller (MVC)**
MVC is a software architectural pattern where:
#### 1. **Model**: Manages the data.
#### 2. **View**: Displays the data.
#### 3. **Controller**: Handles user input and updates the model/view accordingly.

### **Django Uses MVT**
Django uses MVT, which is similar to MVC:
#### - **Model**: Same as MVC.
#### - **View**: Combines both controller logic and view rendering.
#### - **Template**: Handles presentation (equivalent to View in MVC).

---

# **Setup First Django Project**

---

## **1. PyCharm**

### **1. Check if Python is Installed**
Open the terminal in PyCharm or your system’s terminal and run:
```bash
python --version
```
- If Python is not installed, download and install it from [python.org](https://www.python.org/).

---

### **2. Install PyCharm**
Download and install **PyCharm** from [JetBrains' official site](https://www.jetbrains.com/pycharm/download/).

- Use **PyCharm Community (Free)** or **Professional (Paid, with extra features)**.
- Once installed, open PyCharm and create a new project.

---

### **3. Create a New Django Project**
- Open PyCharm → **Create New Project**.
- **Choose Django** as the project type (if using PyCharm Professional).
- **For Community Edition**:
    - Select **"Pure Python"** and create a virtual environment manually.
    - Open the terminal and install Django:
      ```bash
      pip install django
      ```
    - Then, create a Django project:
      ```bash
      django-admin startproject project_name
      ```

PyCharm **automatically creates a virtual environment** (`.venv`) by default unless disabled.
- How to create a virtual environment manually (if not created):
```bash
python -m venv .venv
```
- This creates a `.venv` folder for the project’s virtual environment.
- Activate the virtual environment:
    - **Windows (cmd/PowerShell)**:
      ```bash
      .venv\Scripts\activate
      ```
    - **Mac/Linux**:
      ```bash
      source .venv/bin/activate
      ```

---

### **4. Run the Development Server**
Navigate to the project folder:
```bash
cd project_name
```
Run the Django server:
```bash
python manage.py runserver
```
Visit `http://127.0.0.1:8000/` to see the **Django welcome page**.

---

### **5. Create a Django App**
Inside your project directory, run:
```bash
python manage.py startapp app_name
```
This creates a new app inside your project.

---

### **6. Register the App in `settings.py`**
- Open `project_name/settings.py`.
- Add your app to the `INSTALLED_APPS` list:
  ```python
  INSTALLED_APPS = [
      ...
      'app_name',
  ]
  ```

---

### **7. Run the Server Again**
Restart the server if needed:
```bash
python manage.py runserver
```  
Visit `http://127.0.0.1:8000/app/` to see your **Django app running**.

Now, your Django project is successfully set up in **PyCharm**! 🎉

---

## **2. VS Code**

### **1. Check if Python is Installed**
Run the following command in the terminal:
```bash
python --version
```
If Python is not installed, download and install it from [python.org](https://www.python.org/).

---

### **2. Install VS Code and Python Extension**
- Install [VS Code](https://code.visualstudio.com/).
- Install the **Python extension** from the Extensions Marketplace.

---

### **3. Create a Virtual Environment**
It’s recommended to use a virtual environment to manage dependencies:
```bash
python -m venv venv
```
- This creates a `venv` folder for the project’s virtual environment.
- Activate the virtual environment:
    - **Windows (cmd/PowerShell)**:
      ```bash
      venv\Scripts\activate
      ```
    - **Mac/Linux**:
      ```bash
      source venv/bin/activate
      ```

---

### **4. Install Django**
Once the virtual environment is activated, install Django:
```bash
pip install django
```

---

### **5. Create a Django Project**
Run the following command to create a new Django project:
```bash
django-admin startproject project_name
```  
This generates the necessary project files.

---

### **6. Open the Project in VS Code**
- Open **VS Code** and select **File → Open Folder**.
- Open the newly created `project_name` folder.

---

### **7. Run the Development Server**
Navigate to the project folder:
```bash
cd project_name
```
Run the server:
```bash
python manage.py runserver
```
Visit `http://127.0.0.1:8000/` to see the **Django welcome page**.

---

### **8. Create a Django App**
Inside your project directory, run:
```bash
python manage.py startapp app_name
```
This creates a new app inside your project.

---

### **9. Register the App in `settings.py`**
- Open `project_name/settings.py`.
- Add your app to the `INSTALLED_APPS` list:
  ```python
  INSTALLED_APPS = [
      ...
      'app_name',
  ]
  ```

---

### **10. Run the Server Again**
Restart the server if needed:
```bash
python manage.py runserver
```  
Visit `http://127.0.0.1:8000/app/` to see your **Django app running**.


Now, your Django project is successfully set up in **VS Code**! 🚀

---
## 📚 Resources

### 🔗 Official Documentation
- [Django Documentation](https://docs.djangoproject.com/en/5.1/)

### 📖 Articles
- [What is MVT?](https://www.geeksforgeeks.org/django-project-mvt-structure/)
- [Django Introduction (MDN)](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Server-side/Django/Introduction)

### 🛠️ Setup Django
- [Setup Django Project in VS Code](https://code.visualstudio.com/docs/python/tutorial-django)
- [Setup Django Project in PyCharm](https://www.jetbrains.com/help/pycharm/creating-and-running-your-first-django-project.html)
- [VS Code Setup (Video)](https://www.youtube.com/watch?v=qN_0EZ8M20Q)

### 🎥 Video Tutorials
- [Complete Django Playlist (English)](https://youtube.com/playlist?list=PL4cUxeGkcC9iqfAag3a_BKEX1N43uJutw&si=UVUi7OR0kd1dvKct)
- [Complete Django Playlist (Arabic)](https://youtube.com/playlist?list=PLknwEmKsW8OtK_n48UOuYGxJPbSFrICxm&si=NK1jDGcWGWb76TWL)  
