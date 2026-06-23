# Django Interview Questions & Answers

## 1. Adhikya Edammala: What is CSRF?

**CSRF (Cross-Site Request Forgery)** is a web security attack where a malicious website tricks a user into performing unwanted actions on another website where they are already authenticated.

---

## 2. Allanki VV Manikanta Sai: What is `settings.py`?

`settings.py` is the main configuration file of a Django project. It contains all project settings and configurations.

---

## 3. Arpit Yadav: How to create a new app in Django?

Use the following command inside your Django project directory:

```bash
python manage.py startapp app_name
```

---

## 4. Boorle Sowmya Sri Lakshmi: Difference between `render()` and `redirect()`

| Feature            | render()                 | redirect()               |
| ------------------ | ------------------------ | ------------------------ |
| Purpose            | Returns an HTML template | Redirects to another URL |
| URL Changes        | No                       | Yes                      |
| HTTP Status        | 200 OK                   | 302 Redirect             |
| Template Rendering | Yes                      | No                       |

### Example of `render()`:

```python
return render(request, 'home.html')
```

### Example of `redirect()`:

```python
return redirect('home')
```

---

## 6. M Harivardhan Reddy: What is Clickjacking?

**Clickjacking** is a malicious technique where a user is tricked into clicking something different from what they perceive.

### Prevention:

* X-Frame-Options header
* Content Security Policy (CSP)

---

## 7. Md Musharaf: What is the use of `F()` class in Django?

The `F()` class allows referencing model field values directly in database queries without loading them into Python memory.

### Example:

```python
from django.db.models import F

Product.objects.filter(id=1).update(
    quantity=F('quantity') - 1
)
```

---

## 8. Naman Sharma: What is X-Frame-Options to prevent clickjacking?

`X-Frame-Options` is an HTTP response header used to control whether a webpage can be displayed inside an iframe.

---

## 9. Nayunipatruni Harsha Vardhan: What is `ForeignKey()` in Django?

`ForeignKey()` is used to create a **many-to-one relationship** between models.

### Example:

```python
class Author(models.Model):
    name = models.CharField(max_length=100)

class Book(models.Model):
    title = models.CharField(max_length=100)
    author = models.ForeignKey(
        Author,
        on_delete=models.CASCADE
    )
```

---

## 10. Parlapalli Sulochana: Why do we create a Superuser?

A superuser is an administrator account with all permissions.

### Uses:

* Access Django Admin Panel
* Manage users
* Add, edit, delete records
* Assign permissions

---

## 11. Rongala Vasu: Difference between `HttpResponse` and `render`

| Feature          | HttpResponse                 | render                    |
| ---------------- | ---------------------------- | ------------------------- |
| Purpose          | Returns raw response content | Returns rendered template |
| Template Support | No                           | Yes                       |
| Ease of Use      | Less convenient              | More convenient           |

### HttpResponse Example:

```python
from django.http import HttpResponse

def home(request):
    return HttpResponse("Hello World")
```

### render Example:

```python
from django.shortcuts import render

def home(request):
    return render(request, 'home.html')
```

---

## 12. Vikas Mehta: What is a QuerySet?

A **QuerySet** is a collection of database queries used to retrieve data from Django models.

### Example:

```python
students = Student.objects.all()
```

This returns all student records.
