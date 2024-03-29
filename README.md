# Deploy-a-Django-web-app-to-Vercel-

**1) Settings.py :**

`ALLOWED_HOSTS=['.vercel.app']`

=>I do not want to allow all hosts, so I just allow `vercel`

![image](https://github.com/ThuNganPythonista/Deploy-a-Django-web-app-to-Vercel-/blob/main/Screenshot%202024-01-01%20at%202.03.16%20PM.png)


**2) Moving requirements.txt:**

Using the command `pip freeze > requirements.txt` in your terminal to install requirements.txt file

```python
asgiref==3.7.2
backports.zoneinfo==0.2.1
Django==4.0.0
sqlparse==0.4.4
typing_extensions==4.8.0
PyMySQL==1.0.3

```

*It is not suitable for everyone, please make it follow your database and your version*

**3) Vercel Json File:**

+ Create a file json under the big project folder

![image](https://github.com/ThuNganPythonista/Deploy-a-Django-web-app-to-Vercel-/blob/main/Screenshot%202024-01-01%20at%202.15.30%20PM.png)

![image](https://github.com/ThuNganPythonista/Deploy-a-Django-web-app-to-Vercel-/blob/main/Screenshot%202024-01-01%20at%202.15.59%20PM.png)

Here, this is the code for vercel.json :

```python
{
    "builds": [{
        "src": "djangLofi/wsgi.py",
        "use": "@vercel/python",
        "config": { "maxLambdaSize": "15mb", "runtime": "python3.9" }
    },
    {
        "src": "build.sh",
        "use": "@vercel/static-build",
        "config": { "distDir": "staticfiles_build" }
    }],
    "routes": [
        {
            "src": "/static/(.*)",
            "dest": "/static/$1"
        },
        {
            "src": "/(.*)",
            "dest": "djangLofi/wsgi.py"
        }
    ]
}

```

**Take note:** You change the name of project correct with your own project and change python version following your current python.

**4) Set app=application:**

State this line of code in `wsgi.py` file

`app = application`

**5) Push the code to Github:**

My project has an existing repository, so I gonna commit and push again.

![image](https://github.com/ThuNganPythonista/Deploy-a-Django-web-app-to-Vercel-/blob/main/Screenshot%202024-01-01%20at%202.42.55%20PM.png)

**6) Import your repository to Vercel:**

Access to vercel.com and sign up your Github account :


![image](https://github.com/ThuNganPythonista/Deploy-a-Django-web-app-to-Vercel-/blob/main/Screenshot%202024-01-01%20at%202.46.10%20PM.png)


We go ahead to config it, and then we will click the button `Deploy`

**7) Config Database**

If you use Django, you need to config in your settings and database so much.

In my case, I use DataGrip to manage database, so I link my db on DataGrip with MySQL

[Link MySQL](https://railway.app/project/ffd53e0c-c3e9-4fcd-bd82-d7b121d24640/service/acf89e27-ac31-4bfc-a060-95877b1e308d/variables)

In settings.py, you change your db following this server

With my own case, there are some steps :

    + Step 1 : Login MySQL with Github 

![Image](https://github.com/ThuNganPythonista/Deploy-a-Django-web-app-to-Vercel-/blob/main/Screenshot%202024-01-05%20at%206.34.32%20PM.png)

Config your database in your local settings correct with MySQL | Railway 

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'railway',
        'USER': 'root',

        'PASSWORD': 'xxxxx',

        'HOST': 'xxxx',
        'PORT': 'xxx'
    }
}

```


**RESULT OUT !!!**
![image](https://github.com/ThuNganPythonista/Deploy-a-Django-web-app-to-Vercel-/blob/main/Screenshot%202024-01-01%20at%202.50.21%20PM.png)

Tadaaaaa =))))))

![image](https://github.com/ThuNganPythonista/Deploy-a-Django-web-app-to-Vercel-/blob/main/Screenshot%202024-01-04%20at%203.27.07%20PM.png)

