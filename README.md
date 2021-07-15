# Django Workshop Exercise 3

In this exercise we will use Django admin dashboard to populate some data in the built in SQLight database. Then we will use Django template to create a webpage.
<br/><br/>
## 1. Prepare for the coding environment  

SSH into the test machine. The password is 123456.
```sh
ssh your_upi@130.216.39.213
```
Once you are in, activate the python virtual environment and cd into the project folder
```sh
workon dj && cd mysite
```
<br/><br/>

## 2. Register the model "Item" to admin dash board

Modify "main/admin.py" to register the model "Item"
<details>
  <summary>Click for solution</summary>
  
```sh
from django.contrib import admin
from .models import ToDoList, Item

# Register your models here.
admin.site.register(ToDoList)
admin.site.register(Item)
```
</details>  

Start the server
```sh
./runproject
```

Copy the url from the output to your browsr, and navigate to "/admin". It should bring up the dash board login window, use "your_upi/123456" to authenticate. Once you are in the dash board, create a few items for the ToDoLists. Also feel free to delete some ToDoLists, notice that the items that are associated with the deleted ToDoList are deleted as well.

<br/><br/>
## 3. Create a webpage using template 
Objectives:
- The webpage should be reached by using the path "/aboutme"
- Create a template for the webpage under the name "aboutme.html", it should extend the base template "base.html"
- The body of the webpage should display the text "I like learning Django", the footer should display the text "Copyright 2021 FT3"

<b>Step one</b>: modify "main/url.py" to specify the path that would match the pattern "/aboutme", and then redirect the traffic to a view function "views.aboutme"
<details>
  <summary>Click for solution</summary>
  
```sh
from django.urls import path
from . import views

urlpatterns = [
    path('<int:id>', views.index),
    path('', views.home),
    path('aboutme', views.aboutme)
]
```
</details>

<b>Step two</b>: Add a view function called "aboutme" in "main.views.py", this view function should use a template "aboutme.html"
<details>
  <summary>Click for solution</summary>
  
```sh
def aboutme(response):
    return render(response, "main/aboutme.html", {})
```
</details>

<b>Step three</b>: Create the template file "aboutme.html" under "/mysite/main/templates/main/". This template file should extend "base.html", and look similarly to home.html with different block content.  

<details>
  <summary>Click for solution</summary>
  
```sh
{% extends 'main/base.html' %}
{% block content %}
        <p>I like learning Django</p>
{% endblock %}
{% block footer %}
        <p>Copyright 2021 FT3</p>
{% endblock %}
```
</details>
  
Once you finish the steps above, restart the server and go to the path "/aboutme", you should get something similar to the following:
![alt text](https://github.com/phu004/django_part_three/blob/main/exercise3.png)
  
