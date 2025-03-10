
### Inicilizar proyectos in Springboot | JAVA
```bash
curl https://start.spring.io/starter.zip -d dependencies=web,data-jpa,actuator,validation,lombok,mariadb -d type=gradle-project -d javaVersion=17 -d bootVersion=3.4.2 -o sv-ms-social-get-like.zip

unzip sv-ms-social-get-like -d sv-ms-social-get-like

cd  sv-ms-social-get-like

git init
```
### Inicilizar proyectos in Django | Python
```bash
python3 -m ensurepip --default-pip
export PATH=$HOME/Library/Python/3.12/bin:$PATH

# init project in Django
pip install django boto3

django-admin startproject sv_ms_social_report_comment
cd sv_ms_social_report_comment
django-admin startapp ms


# Activate the environment
python3 -m venv env
source env/bin/activate

# create a requirements.txt and push dependencies
pip freeze > requirements.txt
echo django >> requirements.txt
echo boto3 >> requirements.txt
pip install -r requirements.txt


# run project
python manage.py runserver
```



