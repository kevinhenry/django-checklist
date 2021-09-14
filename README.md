CREATE A DJANGO APPLICATION
1. create a new repo on github
2. make a new directory/folder in terminal (mkdir folder_name) and cd into that directory
3. poetry init -n (this initializes a new directory)
4. peotry add django
5. poetry shell
6. django-admin startproject name-of-project . (make sure to add the period at the end)
7. code .
8. python manage.py runserver (starts the backend server... you'll probably see some migration errors. use control + C to stop server)
9. python manage.py migrate (with server closed)
10. python manage.py startapp app_name (creates a new application)
The rest of the order doesn't really matter but needs to get done (add app, update views, urls and templates)
Update Views and add Application
11. install newly created app (folder name) in the settings.py inside of project folder under INSTALLED_APP = ['app_name' or 'app_name.apps.App_nameConfig']
12. update views, urls and templates inside the app_name/views.py
13. from django.vies.generic import TemplateView
14. create a class for each html webpage that you want to render.
class HomePageView(TemplateView):
    template_name = 'home.html'
Update URLs (both in application and main project foler)
15. create a urls.py inside of application folder. Either use vscode or 'touch urls.py' in terminal
16. imports inside urls.py: from django.urls import path, from .views import HomePageView & AboutPageView (these are the templates)
17. create a urlpatterns = [
path('', HomePageView.as_view(), name = 'home'),
path('about', AboutPageView.as_view(), name = 'about'),
]
18. add another path inside the urls.py inside of the project folder. urlpatterns = [path ('', include('app_name.url')),]
Update Tempplates
19. create a template folder inside main project directory
20. cteate two files inside templates folder (home.html & base.html)
21.





Swiching to postgres on docer allway update requirements.txt
After update req.txt do docer compes build 
once done close and run in detach mode
whil in detach run docker - compose run web python manage py migrate
use same docer compse web python maagae py createsuperuser
is use docker copse down                -- all database info will be lost
to not lose db docer compse stop  and   docker compse start.    --- will work and not dest db  but will eat resourse.
