# Ex.08 Design of Interactive Image Gallery
# Date:
4/10/2025
# AIM:
To design a web application for an inteactive image gallery with minimum five images.

# DESIGN STEPS:
## Step 1:
Clone the github repository and create Django admin interface.

## Step 2:
Change settings.py file to allow request from all hosts.

## Step 3:
Use CSS for positioning and styling.

## Step 4:
Write JavaScript program for implementing interactivity.

## Step 5:
Validate the HTML and CSS code.

## Step 6:
Publish the website in the given URL.

# PROGRAM :

```
{% load static %}
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Image Gallery with onclick</title>
  <style>
    img{
      object-fit: cover;
      background-color: rgb(118, 137, 131);
      padding:13px;
      object-position: top;
    }
    .img2{
      position:absolute;
      top:23%;
      left:33%;
      height:220px;
      width:340px;
      object-position: bottom;
    }
    .img5{
      position: absolute;
      top:8%;
      left:19%;
      height:340px;
      width:220px;
    }
    .img7{
      position:absolute;
      top:16%;
      left:54%;
      height:340px;
      width:220px;
    }
    .img1{
      position:absolute;
      top:59%;
      left:47%;
      width:340px;
      height:220px;
      object-position: top;
    }
    .img4{
      position:absolute;
      top:51%;
      left:12%;
      width:340px;
      height:220px;
    }
    .img8{
      position:absolute;
      top:51.5%;
      left:33%;
      height:340px;
      width:220px;
    }
    .img6{
      position:absolute;
      top:9%;
      left:68%;
      width:340px;
      height:220px;
    }
    .img3{
      height:340px;
      width:220px;
      position:absolute;
      top:37%;
      left:68%;
    }
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background: #2e2929;
      padding: 20px;
    }

    .gallery {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      justify-content: center;
    }

    .gallery img {
      /*width: 300px;
      height: 170px;*/
      cursor: pointer;
      border-radius: 6px;
      transition: transform 0.3s;
      margin:20px;
    }

    .gallery img:hover {
      transform: scale(1.5);
    }

    .lightbox {
      display: none;
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(0, 0, 0, 0.8);
      justify-content: center;
      align-items: center;
    }

    .lightbox img {
      max-width: 90%;
      max-height: 80%;
      border-radius: 10px;
    }

    .close {
      position: absolute;
      top: 20px;
      right: 30px;
      font-size: 2rem;
      color: white;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <h2 style="font-family: arial;font-size:18;color:aquamarine;">GALLERY PAGE</h2>

  <!-- Thumbnails with onclick -->
  <div class="gallery">
    <img src="{% static 'img1.jpg' %}" alt="img1" onclick="openLightbox(this)" class="img1">
    <img src="{% static 'img2.jpg' %}" alt="img2" onclick="openLightbox(this)" class="img2">
    <img src="{% static 'img3.jpg' %}" alt="img3" onclick="openLightbox(this)" class="img3">
    <img src="{% static 'img4.jpg' %}" alt="img4" onclick="openLightbox(this)" class="img4">
    <img src="{% static 'img5.jpg' %}" alt="img5" onclick="openLightbox(this)" class="img5">
    <img src="{% static 'img6.jpg' %}" alt="img6" onclick="openLightbox(this)" class="img6">
    <img src="{% static 'img7.jpg' %}" alt="img7 onclick="openLightbox(this)" class="img7">
    <img src="{% static 'img8.jpg' %}" alt="img8 onclick="openLightbox(this)" class="img8">
  </div>

  <!-- Lightbox -->
  <div class="lightbox" id="lightbox">
    <span class="close" onclick="closeLightbox()">&times;</span>
    <img id="lightbox-img" src="">
  </div>

  <script>
    var lightbox = document.getElementById("lightbox");
    var lightboxImg = document.getElementById("lightbox-img");
    function openLightbox(image) {
      lightbox.style.display = "flex";
      lightboxImg.src = image.src;
    }

    function closeLightbox() {
      document.getElementById("lightbox").style.display = "none";
    }
  </script>
</body>
</html>

views:

from django.shortcuts import render

def gal(request):
    return render(request,"gallery.html")

urls:

"""
URL configuration for pname project.

The `urlpatterns` list routes URLs to views. For more information please see:
    https://docs.djangoproject.com/en/5.2/topics/http/urls/
Examples:
Function views
    1. Add an import:  from my_app import views
    2. Add a URL to urlpatterns:  path('', views.home, name='home')
Class-based views
    1. Add an import:  from other_app.views import Home
    2. Add a URL to urlpatterns:  path('', Home.as_view(), name='home')
Including another URLconf
    1. Import the include() function: from django.urls import include, path
    2. Add a URL to urlpatterns:  path('blog/', include('blog.urls'))
"""
from django.contrib import admin
from django.urls import path
from app import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('',views.gal),
]

```
# OUTPUT:
![alt text](<Image Gallery with onclick and 2 more pages - Personal - Microsoft​ Edge 04-10-2025 11_48_49.png>)
![alt text](<Image Gallery with onclick - Personal - Microsoft​ Edge 04-10-2025 12_17_26.png>)
![alt text](<Image Gallery with onclick - Personal - Microsoft​ Edge 04-10-2025 12_17_31.png>)



# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
