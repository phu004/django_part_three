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
from .model import ToDoList, Item

# Register your models here.
admin.site.register(ToDoList)
admin.site.register(Item)
```
</details>  
<br/><br/>
Start the server
```sh
./runproject
```

