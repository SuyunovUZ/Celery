# CeleryBasic

# Django Celery

1. Yangi papka yaratib uni ichida virtual muhit yartamiz va active qilamiz
```shell
mkdir django_celery
cd django_celery
virtualenv venv
source venv/bin/activate
```
2. Kerakli packagelarni o'rnatib olamiz
```shell
pip install django
pip install celery
```
3. Rabbitmq serverini o'rnatamiz
```shell
sudo apt-get install rabbitmq-server
sudo systemctl enable rabbitmq-server
sudo systemctl start rabbitmq-server
systemctl status rabbitmq-server
```
4. Djangoda project va app yaratamiz
```shell
dajngo-admin startproject config .
django-admin startapp app1
```
5. Python consolga kirib app1.ni ichidagi tasks.py dagi taskni ishga tushuramiz
```shell
from app1.tasks import add
add.delay(4, 8)
add.apply_async((3, 9), countdown=5)
```
Celeryni ishga tushurish
```shell
celery -A config worker -l info
```
