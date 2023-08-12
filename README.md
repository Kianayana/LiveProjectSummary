# LiveProjectSummary
This is my code summary for the final live project I did for The Tech Academy!

## Introduction
I have spent the first 8 months of 2023 learning the bascis of front-end development. With this live project, I was able to put all of my skills and learnings to the test. The live project was two weeks and a minimum of four stories needed to be completed for the project. The project simulated a two week sprint where myself and my other "team members" did stand-ups Monday through Friday and retropesctive discussions.  I am happy ot report that I was able to successfully build an app/website from nothing. It was a difficult, but ultimately fulfilling challenge. Some of the skills I learned along the way are highlighted below.

## Home/Base

First the first portion of my project, I had to generate my app and create a base template for all of my pages. The home template acted as as the landing page for anyone that used my app. 

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



## Create

## Reviews/Database

## Details/Submissions


