# 1️⃣ Models
- Models define the structure of your database.
- Each Model represents a table in the database.
- They are defined in the models.py file of your Django app.

**✨ Example: Defining a Product Model for an E-commerce App**

```python
from django.db import models

class Product(models.Model):
    name = models.CharField(max_length=255)
    description = models.TextField()
    price = models.DecimalField(max_digits=10, decimal_places=2)
    created_at = models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return self.name
```

## Commands for Working with Models

1. Apply database migrations after defining models:

```bash
python manage.py makemigrations
python manage.py migrate
```

2. Register the model in the admin panel:

Add this to admin.py:
```python
from django.contrib import admin
from .models import Product

admin.site.register(Product)
```

# 2️⃣ Views
- Views handle the logic of your application.
- They process requests and return responses.
- Views are defined in views.py.

**✨ Example: Displaying a List of Products**

```python
from django.shortcuts import render
from .models import Product

def product_list(request):
    products = Product.objects.all()
    return render(request, 'products/product_list.html', {'products': products})
```

# 3️⃣ URLs

- URLs map requests to views.
- They are defined in urls.py.

**✨ Example: Mapping a View to a URL**

```python 
from django.urls import path
from .views import product_list

urlpatterns = [
    path('products/', product_list, name='product-list'),
]
```

# 4️⃣ Templates
- Templates are used to display data dynamically.
- They are stored inside the templates/ directory.

**✨ Example: HTML File to Display Products**
-  Create a file at templates/products/product_list.html:
```python 
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Product List</title>
</head>
<body>
    <h1>Product List</h1>
    <ul>
        {% for product in products %}
            <li>{{ product.name }} - ${{ product.price }}</li>
        {% endfor %}
    </ul>
</body>
</html>
```

## How These Components Work Together ??

- The user visits`/products/`.
- Django finds the matching `product_list` view in `urls.py`.
- The `product_list` view fetches data from the `Product` model.
- The data is passed to the `product_list.html` template and displayed.

## 🚀 Summary
- Models: Define database tables.
- Views: Handle business logic.
- URLs: Map views to specific routes.
- Templates: Display data to users.


## 📚 Resources
### 🔗 Official Documentation
- [🔗 Django Documentation](https://docs.djangoproject.com/en/5.1/)
- [🔗 Django Models](https://docs.djangoproject.com/en/5.1/topics/db/models/)
- [🔗 Django Views](https://docs.djangoproject.com/en/5.1/topics/http/views/)
- [🔗 Django URL Dispatcher](https://docs.djangoproject.com/en/5.1/topics/http/urls/)
- [🔗 Django Templates](https://docs.djangoproject.com/en/5.1/topics/templates/)
- [🔗 MDN Documentation for Django](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Server-side/Django)
### 🎥 Video Tutorials
- [Complete Django Playlist (English)](https://youtube.com/playlist?list=PL4cUxeGkcC9iqfAag3a_BKEX1N43uJutw&si=UVUi7OR0kd1dvKct)
- [Complete Django Playlist (Arabic)](https://youtube.com/playlist?list=PLknwEmKsW8OtK_n48UOuYGxJPbSFrICxm&si=NK1jDGcWGWb76TWL)  