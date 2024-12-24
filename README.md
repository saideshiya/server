# Ex.05 Design a Website for Server Side Processing
# Date:
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
!DOCTYPE html>
<html>
<head>
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=edge'>
<title>Power Calculation (P = I²R)</title>
<meta name='viewport' content='width=device-width, initial-scale=1'>
<style type="text/css">
body {
    background-color:rgb(138, 86, 184);
}
.edge {
    width: 100%;
    padding-top: 250px;
    text-align: center;
}
.box {
    display: inline-block;
    border: thick double rgb(140, 93, 194);
    width: 500px;
    min-height: 300px;
    font-size: 20px;
    background-color: navajowhite;
}
.formelt {
    color: black;
    text-align: center;
    margin-top: 7px;
    margin-bottom: 6px;
}
h1 {
    color: black;
    padding-top: 20px;
}
</style>
</head>
<body>
<div class="edge">
    <div class="box">
        <h1>Power Calculation</h1>
        <h3>sai deshiya (24005381)</h3>
        <form method="POST">
            
            <div class="formelt">
                Current (I): <input type="text" name="current" value={{current}}> A<br/>
            </div>
            <div class="formelt">
                Resistance (R): <input type="text" name="resistance" value={{value}}> Ω<br/>
            </div>
            <div class="formelt">
                <input type="submit" value="Calculate"><br/>
            </div>
            <div class="formelt">
                Power (P): <input type="text" name="power" value={{value}}> W<br/>
            </div>
        </form>
    </div>
</div>
</body>
</html>
```
views.py
```
def powerlamp(request):
    context={}
    context['Power'] = ""
    context['I'] = ""
    context['R'] = ""
    if request.method == 'POST':
        print("POST method is used")
        I = request.POST.get('Intensity','')
        R = request.POST.get('Resistence','')
        print('request=',request)
        print('Intensity=',I)
        print('Resistence=',R)
        Power = int(I) * int(I) * int(R)
        context['Power'] = Power
        context['I'] = I
        context['R'] = R
        print('Power=',Power)
    return render(request,'mathapp/math.html',context)
```
urls.py
```
from django.contrib import admin
from django.urls import path
from mathapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('PowerOfLampFilamentInAnIncandescentBulb/',views.powerlamp,name="PowerOfLampFilamentInAnIncandescentBulb"),
    path('',views.powerlamp,name="PowerOfLampFilamentInAnIncandescentBulb"),
]
```
# SERVER SIDE PROCESSING:

![Screenshot 2024-12-22 224413](https://github.com/user-attachments/assets/3172fc90-b7b5-424b-8484-0a78f4403250)


# HOMEPAGE:

![Screenshot (130)](https://github.com/user-attachments/assets/aaede69c-067a-4c0b-a767-25b72aaa60fa)

# views.py:


![Screenshot 2024-12-23 141734](https://github.com/user-attachments/assets/a995d39a-c096-4691-b026-a4c8d82c4717)

# urls.py:


![Screenshot 2024-12-23 141752](https://github.com/user-attachments/assets/e00eac45-b573-480b-b9f8-80fd4c147671)


# RESULT:
The program for performing server side processing is completed successfully.
