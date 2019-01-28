https://medium.com/google-cloud/deploying-django-postgres-redis-containers-to-kubernetes-9ee28e7a146

Clone django project
```bash
git clone https://github.com/waprin/kubernetes_django_postgres_redis
cp django/Dockerfile kubernetes_django_postgres_redis/guestbook
cd kubernetes_django_postgres_redis/guestbook
virtualenv env
source env/bin/activate
pip install -r requirements.txt
```


```bash
docker login
docker build -t your-dockerhub-username/my-guestbook-app .
docker push your-dockerhub-username/my-guestbook-app
docker apply -f django/frontend.yml
```

https://medium.com/google-cloud/deploying-django-postgres-and-redis-containers-to-kubernetes-part-2-b287f7970a33