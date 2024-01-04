# Deploy-a-Django-web-app-to-Vercel-

**1) Settings.py :**

`ALLOWED_HOSTS=['.vercel.app']`

=>I do not want to allow all hosts, so I just allow `vercel`

![image](https://github.com/ThuNganPythonista/Deploy-a-Django-web-app-to-Vercel-/blob/main/Screenshot%202024-01-01%20at%202.03.16%20PM.png)


**2) Moving requirements.txt:**

Using the command `pip freeze > requirements.txt` in your terminal to install requirements.txt file

![image](https://github.com/ThuNganPythonista/Deploy-a-Django-web-app-to-Vercel-/blob/main/Screenshot%202024-01-01%20at%202.12.08%20PM.png)

**3) Vercel Json File:**

+ Create a file json under the big project folder

![image](https://github.com/ThuNganPythonista/Deploy-a-Django-web-app-to-Vercel-/blob/main/Screenshot%202024-01-01%20at%202.15.30%20PM.png)

![image](https://github.com/ThuNganPythonista/Deploy-a-Django-web-app-to-Vercel-/blob/main/Screenshot%202024-01-01%20at%202.15.59%20PM.png)

Here, this is the code for vercel.json :

```python
{
    "builds": [{
        "src": " djangLofi/wsgi.py",
        "use": "@vercel/python",
        "config": { "maxLambdaSize": "15mb", "runtime": "python3.9" }
    }],
    "routes": [
        {
            "src": "/(.*)",
            "dest": " djangLofi/wsgi.py"
        }
    ]
}

```

**Take note:** You change the name of project correct with your own project

![image](https://github.com/ThuNganPythonista/Deploy-a-Django-web-app-to-Vercel-/blob/main/Screenshot%202024-01-01%20at%202.21.59%20PM.png)

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
Vercel is designed suitable for JS or .NET.

If you use Django, you need to config in your settings and database so much.

In my case, I use DataGrip to manage database, so I link my db on DataGrip with MySQL

[Link MySQL](https://railway.app/project/ffd53e0c-c3e9-4fcd-bd82-d7b121d24640/service/acf89e27-ac31-4bfc-a060-95877b1e308d/variables)

In settings.py, you change your db following this server

**RESULT OUT !!!**
![image](https://github.com/ThuNganPythonista/Deploy-a-Django-web-app-to-Vercel-/blob/main/Screenshot%202024-01-01%20at%202.50.21%20PM.png)

Tadaaaaa =))))))

![image](https://github.com/ThuNganPythonista/Deploy-a-Django-web-app-to-Vercel-/blob/main/Screenshot%202024-01-04%20at%203.27.07%20PM.png)

