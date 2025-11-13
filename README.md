# EX02 Developing a Django Application using ORM

### Date: 13/11/25  

---

## AIM:
To develop a Django application to store and retrieve data from a Movies Database using Object Relational Mapping (ORM).


## DESIGN STEPS:

### Step 1:
Create a new Django project named `movies_project`.

### Step 2:
Create a new Django app named `movies_app`.

### Step 3:
Add the app to the `INSTALLED_APPS` section in the project’s `settings.py`.

### Step 4:
Define a model class `Movie` with fields —  `movie_id`, `title`, `director`, `release_year`, `genre`, and `rating`.

### Step 5:
Make and apply migrations using:
```bash
python manage.py makemigrations
python manage.py migrate
```

### Step 6:
Use the Django shell to populate the database with at least ten movie records.

### Step 7:
Use Django ORM queries to retrieve:
- All movies  
- Movies filtered by director  
- Movies released after a certain year  

### Step 8:
Optionally, register the `Movie` model in `admin.py` and view data in the admin panel.

### Step 9:
Run the development server using:
```bash
python manage.py runserver
```

### Step 10:
Verify the results in the terminal or browser.


## PROGRAM:

```
Developed By : Krishna Prasad S  
Register No. : 212223230108  
```

```py
# models.py

from django.db import models

class Movie(models.Model):
    movie_id = models.AutoField(primary_key=True)
    title = models.CharField(max_length=100)
    director = models.CharField(max_length=100)
    release_year = models.IntegerField()
    genre = models.CharField(max_length=50)
    rating = models.FloatField()

    def __str__(self):
        return f"{self.title} ({self.release_year})"
```

```py
# Adding sample data in Django shell

from movies_app.models import Movie

movies = [
    Movie(title="Inception", director="Christopher Nolan", release_year=2010, genre="Sci-Fi", rating=8.8),
    Movie(title="The Dark Knight", director="Christopher Nolan", release_year=2008, genre="Action", rating=9.0),
    Movie(title="Interstellar", director="Christopher Nolan", release_year=2014, genre="Sci-Fi", rating=8.6),
    Movie(title="Titanic", director="James Cameron", release_year=1997, genre="Romance", rating=7.9),
    Movie(title="Avatar", director="James Cameron", release_year=2009, genre="Sci-Fi", rating=7.8),
    Movie(title="The Godfather", director="Francis Ford Coppola", release_year=1972, genre="Crime", rating=9.2),
    Movie(title="Gladiator", director="Ridley Scott", release_year=2000, genre="Action", rating=8.5),
    Movie(title="Parasite", director="Bong Joon-ho", release_year=2019, genre="Thriller", rating=8.6),
    Movie(title="Forrest Gump", director="Robert Zemeckis", release_year=1994, genre="Drama", rating=8.8),
    Movie(title="Joker", director="Todd Phillips", release_year=2019, genre="Crime", rating=8.4),
]

Movie.objects.bulk_create(movies)

```

---

## OUTPUT:

### **All Movies**
<img width="835" height="297" alt="cmd" src="https://github.com/user-attachments/assets/83d4018c-c68b-43c2-8eda-c90d930b586d" />


### **Filtered Query**
<img width="638" height="137" alt="fltered1" src="https://github.com/user-attachments/assets/8bec52db-08fd-4ca7-9c6e-e5f78eacfbdd" />

<img width="778" height="186" alt="fltered2" src="https://github.com/user-attachments/assets/af0b7ecd-6efe-46ea-ab09-7d634404da05" />



## RESULT:
The Django application was successfully developed to store and retrieve movie data using Object Relational Mapping (ORM).
