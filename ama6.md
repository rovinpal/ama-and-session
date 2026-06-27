# Django Interview Questions & Answers

## Arpit Yadav

### What is `commit` in Django Forms?

The `commit` parameter is used with the `save()` method of a `ModelForm`.

* `commit=True` (default): Saves the object to the database immediately.
* `commit=False`: Creates the object but does **not** save it to the database. This allows you to modify the object before saving.

**Example:**

```python
form = StudentForm(request.POST)

if form.is_valid():
    student = form.save(commit=False)
    student.created_by = request.user
    student.save()
```

---

## Boorle Sowmya Sri Lakshmi

### What is a QuerySet in Django?

A **QuerySet** is a collection of database objects retrieved using Django's ORM.

It allows you to:

* Retrieve records
* Filter data
* Order results
* Update or delete records

**Example:**

```python
students = Student.objects.all()
active_students = Student.objects.filter(is_active=True)
```

A QuerySet is **lazy**, meaning the database query is executed only when the data is actually needed.

---

## M Harivardhan Reddy

### What is a Custom Manager in Django?

A **Custom Manager** is used to add custom database query methods to a model.

**Example:**

```python
from django.db import models

class StudentManager(models.Manager):
    def active_students(self):
        return self.filter(is_active=True)

class Student(models.Model):
    name = models.CharField(max_length=100)
    is_active = models.BooleanField(default=True)

    objects = StudentManager()
```

Usage:

```python
Student.objects.active_students()
```

Custom managers help keep query logic organized and reusable.

---

## Md Musharaf

### What is the difference between `Form` and `ModelForm`?

| Form                            | ModelForm                                       |
| ------------------------------- | ----------------------------------------------- |
| Used for general forms          | Directly connected to a Django model            |
| Fields must be defined manually | Fields are automatically created from the model |
| Data is not saved automatically | Can save data directly using `save()`           |
| Used when no model is involved  | Used for CRUD operations with models            |

**Example:**

**Form**

```python
class ContactForm(forms.Form):
    name = forms.CharField()
    email = forms.EmailField()
```

**ModelForm**

```python
class StudentForm(forms.ModelForm):
    class Meta:
        model = Student
        fields = "__all__"
```

---

## Naman Sharma

### What fields do we use when dealing with images in Django?

Django provides the following field:

### `ImageField`

Used to upload and store image files.

**Example:**

```python
class Profile(models.Model):
    image = models.ImageField(upload_to='profiles/')
```

**Requirements:**

* Install Pillow:

```bash
pip install Pillow
```

Common options:

* `upload_to` – specifies the upload folder
* `blank=True` – field is optional
* `null=True` – database can store NULL

---

## Nayunipatruni Harsha Vardhan

### What is the `login_required` decorator?

`login_required` is a Django decorator that restricts access to authenticated users.

If a user is not logged in, they are redirected to the login page.

**Example:**

```python
from django.contrib.auth.decorators import login_required

@login_required
def dashboard(request):
    return render(request, "dashboard.html")
```

---

## Parlapalli Sulochana

### How do you check if a form is valid?

Use the `is_valid()` method.

**Example:**

```python
form = StudentForm(request.POST)

if form.is_valid():
    form.save()
else:
    print(form.errors)
```

`is_valid()`:

* Checks all validations
* Cleans the data
* Returns `True` if the form is valid, otherwise `False`

---

## Rongala Vasu

### What is a query parameter in a URL?

A **query parameter** is data sent in the URL after a `?`.

**Example URL**

```
/products/?category=mobile&page=2
```

Here:

* `category=mobile`
* `page=2`

Access them in Django:

```python
category = request.GET.get("category")
page = request.GET.get("page")
```

Query parameters are commonly used for:

* Searching
* Filtering
* Pagination
* Sorting

---

## Vikas Mehta

### What is a dynamic URL?

A **dynamic URL** contains variable values that are captured from the URL and passed to a view.

**URL Pattern**

```python
path("student/<int:id>/", views.student_detail)
```

**View**

```python
def student_detail(request, id):
    return HttpResponse(f"Student ID: {id}")
```

If the user visits:

```
/student/10/
```

The value `10` is passed to the view as the `id` parameter.

Dynamic URLs are useful for displaying details of specific objects such as users, products, or blog posts.

