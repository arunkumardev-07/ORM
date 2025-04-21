# Ex02 Django ORM Web Application
## Reg no: 212222040016
## Date: 16.04.2025

## AIM
To develop a Django application to store and retrieve data from a Movies Database using Object Relational Mapping(ORM).

## Entity Relationship Diagram

![alt text](<Screenshot 2025-04-17 105444.png>)


## DESIGN STEPS

### STEP 1:
Clone the problem from GitHub

### STEP 2:
Create a new app in Django project

### STEP 3:
Enter the code for admin.py and models.py

### STEP 4:
Execute Django admin and create details for 10 books

## PROGRAM
```
admin.py

from django.contrib import admin
from .models import Movie

@admin.register(Movie)
class MovieAdmin(admin.ModelAdmin):
    list_display = ('title', 'genre', 'director', 'release_date', 'rating')
    list_filter = ('genre', 'release_date', 'rating')
    search_fields = ('title', 'director', 'genre')
    ordering = ('-release_date',)

models.py

from django.db import models

class Movie(models.Model):
    title = models.CharField(max_length=200)
    genre = models.CharField(max_length=100)
    director = models.CharField(max_length=100)
    release_date = models.DateField()
    duration_minutes = models.PositiveIntegerField()
    rating = models.DecimalField(max_digits=3, decimal_places=1)  # e.g., 8.5
    description = models.TextField(blank=True, null=True)

    def _str_(self):
        return f"{self.title} ({self.release_date.year})"
```


## OUTPUT

![alt text](<Screenshot 2025-04-16 143908.png>)


## RESULT
Thus the program for creating movies database using ORM hass been executed successfully
