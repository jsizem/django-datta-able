# [Datta Able Django](https://appseed.us/product/datta-able/django/)

Open-source **[Django Dashboard](https://appseed.us/admin-dashboards/django/)** provided by `AppSeed` on top of a modern design. **[Datta Able](https://appseed.us/product/datta-able/django/)** Bootstrap Lite is the most stylized Bootstrap 4 Template, among all other Lite/Free admin templates in the market. It comes with high feature-rich pages and components with fully developer-centric code - design from `CodedThemes`.

<br />

## Django Framework

Django is a high-level Python web framework designed for rapid development of secure and maintainable websites. Here are the core features:

- Model-View-Template (MVT) architecture:
  - Models define your data structure
  - Views handle the logic and processing
  - Templates manage the presentation
- Built-in admin interface for easy content management
- Object-Relational Mapping (ORM) for database interactions without writing SQL
- URL routing system to map URLs to views
- Form handling and validation
- Built-in security features (e.g., protection against SQL injection, cross-site scripting)
- Scalable and suitable for both small and large projects

To get started, you'll need Python installed. Then you can install Django, create a project, define models, set up views and templates, and run your development server.

<br />

## Project Requirement // needs updating

Here are the core features:

- Django - v 5.1.1
- pipx install Django==5.1.1

To get started, you'll need Python installed. Then you can install Django, create a project, define models, set up views and templates, and run your development server.

<br />

## Manual Build

### 👉 Set Up  

> Install modules via `VENV`  

```bash
$ virtualenv env
$ source env/bin/activate
$ pip3 install -r requirements.txt
```

<br />

> Set Up Database

```bash
$ python manage.py makemigrations
$ python manage.py migrate
```

<br />

> Generate API

```bash
$ python manage.py generate-api -f
```

<br />

> Start the APP

```bash
$ python manage.py createsuperuser # create the admin
$ python manage.py runserver       # start the project
```

At this point, the app runs at `http://127.0.0.1:8000/`. 


## Codebase Structure

The project is coded using a simple and intuitive structure presented below:

```bash
< PROJECT ROOT >
   |
   |-- core/                            
   |    |-- settings.py                   # Project Configuration  
   |    |-- urls.py                       # Project Routing
   |
   |-- home/
   |    |-- views.py                      # APP Views 
   |    |-- urls.py                       # APP Routing
   |    |-- models.py                     # APP Models 
   |    |-- tests.py                      # Tests  
   |    |-- templates/                    # Theme Customisation 
   |         |-- pages                    # 
   |              |-- custom-index.py     # Custom Dashboard      
   |
   |-- requirements.txt                   # Project Dependencies
   |
   |-- env.sample                         # ENV Configuration (default values)
   |-- manage.py                          # Start the app - Django default start script
   |
   |-- ************************************************************************
```

<br />

## How to Customize 

When a template file is loaded in the controller, `Django` scans all template directories starting from the ones defined by the user, and returns the first match or an error in case the template is not found. 
The theme used to style this starter provides the following files: 

```bash
# This exists in ENV: LIB/admin_datta
< UI_LIBRARY_ROOT >                      
   |
   |-- templates/                     # Root Templates Folder 
   |    |          
   |    |-- accounts/       
   |    |    |-- auth-signin.html     # Sign IN Page
   |    |    |-- auth-signup.html     # Sign UP Page
   |    |
   |    |-- includes/       
   |    |    |-- footer.html          # Footer component
   |    |    |-- sidebar.html         # Sidebar component
   |    |    |-- navigation.html      # Navigation Bar
   |    |    |-- scripts.html         # Scripts Component
   |    |
   |    |-- layouts/       
   |    |    |-- base.html            # Masterpage
   |    |    |-- base-auth.html       # Masterpage for Auth Pages
   |    |
   |    |-- pages/       
   |         |-- index.html           # Dashboard Page
   |         |-- profile.html         # Profile Page
   |         |-- *.html               # All other pages
   |    
   |-- ************************************************************************
```

When the project requires customization, we need to copy the original file that needs an update (from the virtual environment) and place it in the template folder using the same path. 

> For instance, if we want to **customize the index.html** these are the steps:

- `Step 1`: create the `templates` DIRECTORY inside the `home` app
- `Step 2`: configure the project to use this new template directory
  - `core/settings.py` TEMPLATES section
- `Step 3`: copy the `index.html` from the original location (inside your ENV) and save it to the `home/templates` DIR
  - Source PATH: `<YOUR_ENV>/LIB/admin_black_pro/pages/index.html`
  - Destination PATH: `<PROJECT_ROOT>home/templates/pages/index.html`

> To speed up all these steps, the **codebase is already configured** (`Steps 1, and 2`) and a `custom dashboard` can be found at this location:

`home/templates/pages/custom-index.html` 

By default, this file is unused because the `theme` expects `index.html` (without the `custom-` prefix). 

In order to use it, simply rename it to `index.html`. Like this, the default version shipped in the library is ignored by Django. 

In a similar way, all other files and components can be customized easily.

<br />

[Datta Able Django](https://appseed.us/product/datta-able/django/) - Open-source starter provided by **[AppSeed](https://appseed.us/)**.
