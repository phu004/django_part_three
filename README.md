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
