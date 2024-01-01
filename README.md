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
  
