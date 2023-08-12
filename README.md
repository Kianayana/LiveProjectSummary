# LiveProjectSummary
This is my code summary for the final live project I did for The Tech Academy!

## Introduction
I have spent the first 8 months of 2023 learning the bascis of front-end development. With this live project, I was able to put all of my skills and learnings to the test. The live project was two weeks and a minimum of four stories needed to be completed for the project. The project simulated a two week sprint where myself and my other "team members" did stand-ups Monday through Friday and retropesctive discussions. Through this project, I was able to utilize HTML, CSS, SQL and Python. I am happy ot report that I was able to successfully build an app/website from nothing. It was a difficult, but ultimately fulfilling challenge. Some of the skills I learned along the way are highlighted below. 

## Home/Base

For the first portion of my project, I had to generate my app and create a base template for all of my pages. The home template acted as as the landing page for anyone that used my app. 

#### I had to generate a views file where I learned to create functions that rendered all of my pages and their methods properly. 

```
from django.shortcuts import render, redirect, get_object_or_404
from .forms import HorrorMoviesForm
from .models import HorrorMovies
import requests
import datetime
              
              
              
# Create your views here.
#This renders the home page
def smt_newrel(request):
      return render(request, 'SMT_App/smt_home.html')

```

#### I created this base to be the base template for all of the pages. This template includes a navigation bar and all of the linked stylesheets. 
```
<title>{% block title%}Morer Horror Movies{% endblock %}</title>
</head>

<div>
<header>
    <div class="NavBar">
        <nav class="navbar navbar-expand-xl navbar-light bg-danger">
             <div class="container-fluid">
                <a class="navbar-brand" href="{% url 'smt_newrel' %}">MHM</a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
                  <span class="navbar-toggler-icon"></span>
                </button>

                <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
                    <div class="navbar-nav">
                        <a href="{% url 'smt_newrel' %}" class="nav-link active" aria-current="page">Home</a>
                        <a href="{% url 'smt_hottakes' %}" class="nav-link">Hot Takes</a>
                        <a href="{% url 'smt_rev' %}" class="nav-link">Reviews</a>
                    </div>
                </div>
             </div>
        </nav>
    </div>
</header>
```

## Create
For the second portion of my project, I needed to create a page that held a form and allowed users to submit reviews for scary moves they have seen. This was probably the most important portion of the project because I needed to create functioing model that generated a table to display conent on the rest of the pages. 

#### This is the model I wrote to generate the form and tables that hold all moview review submissions.
```
class HorrorMovies(models.Model):
    movie_name = models.CharField('Movie Name', max_length=140, default="", blank=True, null=False)
    release_year = models.IntegerField ('Release Year', default="", blank=True, null=True)
    rating = models.FloatField('Rating', null=True, blank=True, default=None)
    smt_rev = models.TextField('Review', max_length=1000, default="", blank=True, null=False)
    smt_username = models.CharField('Username', max_length=60, default="", blank=True, null=False)


    # This creates the model manager
    smovies = models.Manager()

    def __str__(self):
        return self.movie_name
```


## Reviews/Database
For the third portion of my project, I created a reviews page where you can see some of the contents of my database. This page allows users to see what movies have been been review by which user and based on that information, they can choose which review to read.

####  I had to write a function that generated the page and linked the database's content to the same page.
```
def smt_rev(request):
    s_htakes = HorrorMovies.smovies.all()
    content = {"s_htakes": s_htakes }
    return render(request, "SMT_App/smt_reviews.html", content)
```

## Details/Submissions
To complete my project, I created a details page that holds the actual reviews for users to read once they have selected a review. I also did little styling up to this point. Once I was able to properly render the details page, I spent a few hours having fun adding some details to all fives templates through the use of bootstrap and my stylesheet.

#### I did not add as much styling as I would like, but was able to create a few simple style changes to the original templates I had while I worked on the functionality of my app.

```
/*styling based on tags */

html {
    font-family: sans-serif;
    background: transparent;
}


h1 {
    font-family: 'Copperplate Gothic Light', sans-serif;
    color: white;
    font-weight: 950;
}

h2 {
    font-family: 'MV Boli';
    color: #49fb35;
    text-align: center;
    padding-top: 10px;
    padding-bottom: 20px;
    text-decoration: underline;
}

/*styling based on classes */

.home-1 {
    background: url(/static/images/forest.jpg) no-repeat center fixed;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    z-index: -1;
    display: block;
    padding-bottom: 200px;
    color: white;

}

.home-2 {
background: transparent
}

.logo {
    padding-top: 50px;
    padding-bottom: 75px;
}
```

Thank you for taking a look at my live project. It was ana amazing experience that made me proud of what I can accomplish!





