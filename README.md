apiVersion: apps/v1
kind: Deployment
metadata:
  name: django-app-deployment
  labels:
   app: django-app
  namespace: react-django-app

spec:
 replicas: 4
 selector:
  matchLabels:
   app: django-app
 template:
  metadata:
   labels:
     app: django-app
  spec:
    containers:
      - name: django-todo-ctr
        image: safiakhatoon/react-django-app:latest
        ports:
          - containerPort: 8001
